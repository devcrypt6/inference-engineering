# Inference Engineering from First Principles

Structured notes on LLM inference engineering: what inference is, why it became its own engineering discipline, and what inference engineers actually do. Built up from the basics with analogies and examples.

> Core idea: make AI models serve real-world requests **efficiently**, **reliably** and at **acceptable cost**.

## Contents

### 01 · Foundations

| #   | Note                                                                                        | What it covers                                                            |
| --- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| 1   | [Restaurant analogy](docs/01-foundations/01-restaurant-analogy.md)                          | Why cooking well isn't enough once you serve 10K customers                |
| 2   | [AI perspective & what is inference](docs/01-foundations/02-ai-perspective-and-inference.md) | The request lifecycle, millions of users, and the cat/dog analogy         |
| 3   | [Why inference engineers](docs/01-foundations/03-why-inference-engineers.md)                | Evolution from software to generative AI, the 5 challenges, the role      |
| 4   | [What inference engineers do](docs/01-foundations/04-what-inference-engineers-do.md)        | Problems → questions, researcher vs engineer, beyond Docker               |
| 5   | [Why it matters now](docs/01-foundations/05-why-it-matters-now.md)                          | Generative AI's impact, three focuses, key definitions                    |

### 02 · Basics

| #   | Note                                                                                              | What it covers                                                                 |
| --- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| 1   | [Goals and metrics](docs/02-basics/01-goals-and-metrics.md)                                       | What inference engineers optimize, the 4 metrics, cost economics               |
| 2   | [What is a model?](docs/02-basics/02-what-is-a-model.md)                                          | Rules vs learning, parameters, training vs inference                           |
| 3   | [Hardware and systems](docs/02-basics/03-hardware-and-systems.md)                                 | Why GPUs & servers, CPU vs GPU, simple architecture, languages                 |
| 4   | [How an LLM generates an answer](docs/02-basics/04-how-an-llm-generates-an-answer.md)             | Tokens, next-token prediction, auto-regressive generation, prefill vs decode   |
| 5   | [Request lifecycle & serving tools](docs/02-basics/05-request-lifecycle-and-serving-tools.md)     | Model vs service, request flow, inside the inference server, vLLM/TGI/Triton   |

## The Five Dimensions

| Dimension       | Question                                                         |
| --------------- | ---------------------------------------------------------------- |
| **Latency**     | How long does the user wait?                                     |
| **Throughput**  | How much work can the system complete per second?                |
| **Memory**      | Can the model & its active requests fit on the available GPUs?   |
| **Cost**        | How much does it cost to serve each request?                     |
| **Reliability** | Can the service keep working during traffic spikes or failures?  |

## Repository Structure

```text
.
├── docs/
│   ├── 01-foundations/     # Why inference engineering exists
│   └── 02-basics/          # Models, hardware, tokens, serving
└── resources/
    ├── Emerge.pdf          # Original handwritten notes: foundations
    └── Basics.pdf          # Original handwritten notes: basics
```

## How to Read

Go through the folders in order, `01-foundations` → `02-basics`, and the notes inside each from `01` → `05`. Each file builds on the previous one.
