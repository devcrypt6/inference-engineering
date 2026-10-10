# 5. What Happens When an AI Request Reaches a Server?

## 1. AI Model vs AI Service

Consider a **REST backend for an application** → it exposes an API that lets users submit questions to an **AI assistant** → it already has a trained language model.

*How does the REST backend actually use it?*

### Three Different Things

| Term              | Meaning                                                                                                                         |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| **Model**         | Not the same thing as a running service → learned parameters + model architecture. May exist as files on disk or in a model repository |
| **Running model** | A serving process loads the model & makes its parameters & required execution state available in memory, often GPU memory      |
| **AI service**    | A system that accepts requests, passes them to the model-serving process & returns generated results to applications            |

### Analogy

| Music world           | AI world          | What it means                                    |
| --------------------- | ----------------- | ------------------------------------------------ |
| **Music file**        | **Model**         | File → model                                     |
| **Music player**      | **Running model** | Player can load & play it                        |
| **Streaming service** | **AI service**    | Playback service makes it available to many users |

Similarly:

- The **model** contains learned parameters
- An **inference runtime** executes the model
- & the **AI service** makes it accessible to users

---

## 2. How Do Components Communicate?

### Components

| Component            | Responsibility                                          |
| -------------------- | ------------------------------------------------------- |
| **REST application** | Handles the product's business logic                    |
| **Inference server** | Runs the AI model & processes generation requests       |
| **GPU**              | Performs the model's numerical computation              |

### Request Flow

```text
User
  │  HTTP request
  ▼
REST backend  (auth + logic + request validation)
  │  API call
  ▼
Inference server  (model execution, scheduling, memory management)
  │  model computation
  ▼
GPU + model  (computes the output tokens)
  │
  ▼
travels back with results ──► User
```

---

## 3. Inside the Inference Server

*What happens inside?*

| Step | What happens                                                                                                              | Concept                              |
| ---- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| 1    | **Validate** the request & check relevant limits                                                                          |                                      |
| 2    | **Prompt tokenized** → convert to the numerical inputs the model expects                                                  | Tokenization                         |
| 3    | **Schedule work** → the serving engine determines when this request can use the model & available computing resources      | Request scheduling, Batching         |
| 4    | **Execute model** → runtime performs the model's computations using its parameters and input content to generate output tokens | Model execution, Inference runtime |
| 5    | **Return the response** → the server converts generated tokens into text & sends the response back to the application; it may stream the answer as tokens become available | Detokenization, Streaming response |

---

## 4. In Production

**1000+ users** asking questions at the same time, without having infrastructure → **encounters:**

- Requests competing for GPU resources
- GPU memory running out
- Delays between requests
- Hardware sitting idle when it could be doing useful work
- Requests taking too long (or) failing under heavy traffic

> [!IMPORTANT]
> The **inference engine** helps coordinate the workload.
> Depending on the engine, it can manage:
>
> - Batching
> - Request queues
> - Execution
> - & other optimization

---

## 5. Efficiently Responding to Users on Equivalent Hardware

### Example

| Metric                          | System A | System B |
| ------------------------------- | -------- | -------- |
| **Requests completed per second** | 20       | 60       |
| **Average GPU utilization**     | 35%      | 85%      |
| **Output quality**              | Same model & settings → same | Same model & settings → same |

> [!NOTE]
> These are **not benchmark results**.

- **System B delivers 3 times the throughput.**
- That could reduce the amount of hardware needed to serve a given traffic volume.

> [!WARNING]
> **High GPU utilization does not guarantee good performance.**
>
> We must also measure **response latency, error rates, output quality and operating cost**.

→ These are the **trade-offs inference engineers investigate**.

---

## 6. Model-Serving Tools

| Tool                                | What it is                                                                                           |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **vLLM**                            | Inference & serving engine designed for efficient LLM serving, with features such as **continuous batching** and **KV cache management** |
| **Hugging Face TGI**                | Text Generation Inference is a model-serving project for deploying language models. Its maintenance & deployment status should be checked before using it for a new project |
| **NVIDIA Triton Inference Server**  | A serving platform for deploying models across supported frameworks & hardware backends, including GPU-based deployments |
