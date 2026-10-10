# 2. In Perspective of Artificial Intelligence

## What Happens When a User Asks a Question

```text
 User asks a question
        │
        ▼
 AI model processes the request
        │
        ▼
 Computers perform the work
        │
        ▼
 Answer reaches the user
```

| Step | What happens                                                                                           |
| ---- | ------------------------------------------------------------------------------------------------------ |
| a)   | **User asks a question**, e.g. *"Explain Round-Robin algorithm"*                                       |
| b)   | **AI model processes the request** → model performs computations to determine what to generate next    |
| c)   | **Computers perform the work** → CPUs, GPUs, memory, software → execute the model's computations      |
| d)   | **Answer reaches the user** → generated output is delivered → often piece by piece as it is produced   |

---

## Now Imagine Millions of People

Millions of people sending requests to AI systems.

### Problems

- Requests take too long
- GPUs become overloaded
- Memory becomes a bottleneck
- Hardware is expensive
- Some users wait while others are being served
- System needs to handle traffic spikes without failing

> [!IMPORTANT]
> **This is where inference engineers are required.**

---

## What Exactly Is Inference?

### The Child Analogy

Teach a child → **1000 examples** of cat, dog.

**Over time, the child learns a pattern:**

- Cats often have particular facial features
- Dogs often have different facial features
- Animals can have different shapes, sizes & appearances

**Later**, you show the child a picture they have never seen before and ask:

> *What animal is this?*

The child uses the pattern → **cat**

### Connecting It to AI

> [!NOTE]
> The process of **using what was learned to make predictions about new input** is analogous to **inference**.
>
> AI models do something similar, although their internal computations are **mathematical** rather than human reasoning.
