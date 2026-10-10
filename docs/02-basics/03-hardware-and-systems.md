# 3. Hardware and Systems: Why GPUs & Servers?

## Why We Need GPUs & Servers

A trained model's computations must run on **physical hardware**.

- For **small models** → a regular CPU is sufficient.
- **LLMs** often benefit from GPUs → GPUs perform many **"mathematical operations fast"**.

### Key Terms

| Term                   | Meaning                                                                          |
| ---------------------- | -------------------------------------------------------------------------------- |
| **GPU**                | Hardware that performs the computations                                          |
| **Server**             | A computer that provides resources to run applications & models                  |
| **Inference software** | The software that loads the model, processes requests & coordinates computation  |
| **Inference engineer** | The engineer who helps make the complete serving system fast, efficient, reliable, scalable |

### Analogy

| Part      | Kitchen equivalent      |
| --------- | ----------------------- |
| **Model** | Recipe                  |
| **GPU**   | Kitchen appliance / equipment |

### In Production

- The model must **fit into available memory**
- Requests must be **scheduled**
- Hardware capacity must be **monitored**

---

## Traditional Programming vs Machine Learning

| Approach                  | How it works                                                              |
| ------------------------- | ------------------------------------------------------------------------- |
| **Traditional programming** | Developers explicitly write rules                                       |
| **Machine learning**      | Algorithm uses data to learn patterns by adjusting the model's parameters |

### Roles of Hardware and Software

- **Hardware** → to perform computations
- **Software** → coordinates how it is used, the model & hardware

---

## CPU vs GPU

### CPU: Central Processing Unit

- General-purpose processor
- Designed to handle a wide variety of tasks
  - Including complex control logic
  - & tasks with different execution patterns

### GPU: Graphics Processing Unit

- Processor designed to perform **many operations in parallel**
- Useful for **large matrix & vector operations** common in neural networks

### The Workload

Perform **millions of similar multiplication & addition operations**:

- **CPU** → can handle these operations
- **GPU** → has an architecture designed to perform large amounts of suitable work concurrently

### Comparison

| CPU                                       | GPU                                          |
| ----------------------------------------- | -------------------------------------------- |
| General-purpose computing & control       | High parallel numerical computation          |
| Parallel execution exists, **but** →      | Greater parallel throughput for suitable workloads |
| Useful for many models                    | Useful for large neural networks             |
| Excellent for suitable workloads          | Excellent when its capacity is well utilized |

### GPU Cost ↑

GPUs are **economically attractive** when their performance & throughput justify the cost.

> [!IMPORTANT]
> Cores, processor, architecture, memory bandwidth, precision, workload:
> **how efficiently the software uses the hardware all matter.**

---

## A Simple Architecture

```text
User / Application
        │
        ▼
    API Server
        │
        ▼
Inference Server / Engine
        │
        ▼
model + CPU/GPU hardware
        │
        ▼
    Response
```

Others distribute them across **multiple processes (or) servers**.

### Traditional Software Already Handles

- Concurrent API requests
- Scheduling
- Memory, reliability & scaling

> [!NOTE]
> These are **not unique to AI**.

---

## What LLMs Add

LLMs bring:

- Large amounts of numerical computation
- Specialized accelerators & high-bandwidth memory
- Models that may occupy many gigabytes of memory
- Responses generated token by token
- Request scheduling decisions that affect both latency & throughput
- Additional memory requirements for ongoing operations

---

## Inference Engineering Builds On

- **Traditional distributed systems**
- **\+ Backend engineering**

then adds **challenges specific to serving machine-learning models efficiently**.

### Languages in the Stack

| Language       | Common use                                                               |
| -------------- | ------------------------------------------------------------------------ |
| **Python**     | Widely used for model development, integration, orchestration            |
| **C++ & CUDA** | Common in performance-critical inference kernels & GPU computing         |
| **Rust**       | Useful for systems software, services, concurrency + memory-safe components |
| **Go**         | Common in infrastructure services & cloud-native tooling                 |

> [!IMPORTANT]
> The **algorithm, implementation, hardware access, architecture** matter.
