# 3. If Inference Exists, Why Do We Need Inference Engineers?

## The Starting Point

- ML models were making predictions long back, **before generative AI's boom**.
- The change was **scale + complexity + nature of workload**.

---

## Evolution

### 1) Traditional Software

- Software → write program → computer executes instructions

### 2) Machine Learning Becomes Practical

- Models learn patterns from data & make predictions when applications use them.
- Examples: identify spam mails, fraudulent bank spams …

### 3) Deep Learning Scales Up

- Large neural networks → demand:
  - Substantial computation
  - Memory
  - Specialized hardware
- Examples: image recognition, speech recognition, translation …

### 4) Generative AI → Reaches Millions of Users

- Large language models (LLMs):
  - Generate long responses
  - Handle concurrent users
  - Operate multi-step AI applications
- Examples: `chat assistants`, `coding agents`, `document analysis platform`

```text
Traditional Software  →  Machine Learning  →  Deep Learning  →  Generative AI
   (instructions)         (predictions)        (scale up)       (millions of users)
```

---

## Serving Is No Longer a Small Step

As evolution & development progress → serving a model is **no longer merely a small step inside an application**.

For **large generative models**, it becomes a **major infrastructure & operating-cost challenge**.

Think about it:

- Generate **200+ words**, token by token?
- **1000+ requests**?

---

## The Challenges

| Dimension       | Question it asks                                                      |
| --------------- | --------------------------------------------------------------------- |
| **Latency**     | How long does the user wait?                                          |
| **Throughput**  | How much work can the system complete per second?                     |
| **Memory**      | Can the model & its active requests fit on the available GPUs?        |
| **Cost**        | How much does it cost to serve each request?                          |
| **Reliability** | Can the service keep working during traffic spikes or hardware failures? |

> [!IMPORTANT]
> These challenges helped drive **specialized inference software, infrastructure & engineering practices**.

---

## The Role of the Inference Engineer

The role of an inference engineer is **not defined by a universal job**.

Different companies divide these responsibilities among:

- ML infrastructure engineer
- ML systems engineer
- GPU performance engineer
- Inference engineer
- Optimization engineer

> [!NOTE]
> **The central responsibility is similar** → make AI models serve real-world requests:
>
> - Efficiently
> - Reliably
> - At acceptable cost
