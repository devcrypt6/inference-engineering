# 4. What Does an Inference Engineer Actually Do?

## The Scenario

Imagine a company wants to build an **AI assistant** for **500,000 users**.

- The model already existed.
- The job is to make the service work well.

---

## Problems → Questions

| Problem                         | Question                                                      |
| ------------------------------- | ------------------------------------------------------------- |
| **Slow answers**                | How can we reduce response latency?                           |
| **High GPU bills**              | How can we serve more requests with the same hardware?        |
| **GPU memory exhaustion**       | How do we fit the model & its active requests into memory?    |
| **Too many simultaneous users** | How do we schedule & batch requests efficiently?              |
| **Traffic spikes**              | How do we scale capacity without wasting money?               |
| **Service failure**             | How do we monitor, recover and maintain availability?         |

---

## Model Researcher vs Inference Engineer

| Role                   | Focus                                                  |
| ---------------------- | ------------------------------------------------------ |
| **Model Researcher**   | Developing better models                               |
| **Inference Engineer** | Serving that model to real users **efficiently**       |

- There is **overlap** between these roles.
- Their **primary objectives can differ**.

---

## Inference Engineering ≠ Just Deploying a Model in Docker

> [!WARNING]
> An inference engineer does **not** just deploy a model in Docker.

Docker, Kubernetes, APIs & monitoring → **part of the job**.

### High-Performance Inference Involves Understanding

- Model computation
- GPU architecture
- Memory management
- Request scheduling
