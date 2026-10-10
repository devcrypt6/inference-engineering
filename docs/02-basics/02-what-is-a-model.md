# 2. What Is a Model?

## Programming with Explicit Rules

A calculator:

```text
10 + 10  ──►  Returns 20
(input)
```

Programming → fixed rules for arithmetic.
The computer executes the instructions needed to **calculate the result**.

```text
Input                Programmed rules              Output
10 + 20   ──►   perform addition()   ──►   30
                └────────┬─────────┘
                Explicitly designed rules
                for performing calculation
```

---

## Where Rules Break Down

Build software that recognizes **cats in photographs**:

- A few rules → but these rules overlap with dogs.

> [!WARNING]
> Writing every possible rule becomes **extremely difficult**.

→ Researchers developed a different approach.

---

## Learning from Examples

Instead of manually writing every rule:

- We give a machine learning system **examples**
- & let it **learn useful patterns from data**

For example → provide thousands of photographs labeled **"cat"** (or) **"dog"**.

The learning algorithm adjusts the model based on how well its predictions match the examples.

```text
┌──────────────────┐     ┌──────────────────────┐     ┌──────────────────────────┐
│      Input       │     │  Learning algorithm  │     │         Result           │
│                  │ ──► │                      │ ──► │                          │
│ many labeled cat │     │ Adjusts internal     │     │ A trained model that can │
│ & dog photographs│     │ values to learn      │     │ classify new photographs │
│                  │     │ pattern              │     │                          │
└──────────────────┘     └──────────────────────┘     └──────────────────────────┘
```

---

## Machine Learning Model

> A **machine learning model** is a mathematical system whose internal parameters are **learned (or) adjusted during training**, allowing it to make predictions (or) generate outputs from inputs.

> [!IMPORTANT]
> A model **doesn't need a programmer to manually write every possible recognition rule**.
>
> Instead, training adjusts its parameters so it can learn **useful patterns**.

---

## What Exactly Is Inside a Model?

A model → a **huge mathematical machine**.

```text
          ┌── ○ ──┐       ┌── ○ ──┐
          │       │       │       │
Input ──► ○ ── ○ ─┼── ○ ──┼── ○ ──┼──► ○ ──► Output
          │       │       │       │
          └── ○ ──┘       └── ○ ──┘
        (a network of mathematical operations)
```

**Inside:**

- It performs mathematical operations
- Using values that were learned during training
- These operations **transform the input & produce an output**

---

## Parameters

For many modern AI systems → learned values are called **"parameters"**.

- Parameters are **adjusted numerical values** inside the model.
- During training, an **optimization process** adjusts these values.
- After training, the model uses these learned values when **"processing new inputs"**.

→ An LLM may have **billions of parameters**.
These numbers are part of what enables it to learn patterns in language, code & other training data.

> [!IMPORTANT]
> **One important distinction:** parameters are **not** simply a database of stored answers.
>
> They encode learned patterns, & the model uses computations involving these parameters to produce outputs.

---

## Vocabulary

| #   | Concept                                      | Term                |
| --- | -------------------------------------------- | ------------------- |
| 1   | Machine learns from examples                 | **Model training**  |
| 2   | The adjustable internal numbers              | **Model parameters** |
| 3   | The process that adjusts the numbers         | **Optimization**    |
| 4   | The trained mathematical machine             | **Trained model**   |
| 5   | Using the trained machine on new input       | **Inference**       |

> [!NOTE]
> Don't need to understand the mathematics behind parameters yet.

---

## LLM at a High Level

```text
LLM → process input → generate response
```

```text
Prompt
   │
   ▼
Input processing      (text converted to tokens & numerical representations)
   │
   ▼
Model computation     (model uses learned parameters to calculate next token probabilities)
   │
   ▼
Generated response    (tokens are generated → converted into readable text)
```

- LLMs usually generate responses **token by token**.
- **Model** → mathematical system
- **Inference** → process of running that system on input
