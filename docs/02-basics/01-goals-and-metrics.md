# 1. Goals and Metrics of Inference Engineering

## The Context

As the adoption of **generative AI ↑**:

- Inference infrastructure must serve a **growing number of concurrent requests**
- While maintaining:
  - Low latency
  - High throughput
  - Reliability
  - Cost efficiency

```text
Adoption of generative AI ↑
          │
          ▼
Growing number of concurrent requests
          │
          ▼
Inference infrastructure must stay:
  low latency · high throughput · reliable · cost-efficient
```

---

## What the Inference Engineer Optimizes

An inference engineer optimizes **model serving**:

- GPU utilization
- Memory management
- Request scheduling

The goal is to **scale workloads**:

- Without compromising service quality
- (or) exceeding infrastructure budgets

---

## Important Metrics

| #   | Metric              | What it tells you                                                   |
| --- | ------------------- | ------------------------------------------------------------------- |
| 1   | **Latency**         | How long a request takes to receive a response                      |
| 2   | **Throughput**      | How much work the system completes in a given period                |
| 3   | **Concurrency**     | How many requests are being handled at the same time                |
| 4   | **GPU utilization** | How effectively the available GPU computing capacity is being used  |

---

## Cost and Economics

Efficient inference can:

- Reduce operating costs
- Improve the economics of a product

> [!NOTE]
> Profitability also depends on **revenue & other expenses**.

---

## Foundations: What We Need to Understand Next

1. What is a model?
2. How does a model learn?
3. Why does a model need computing hardware to answer?
