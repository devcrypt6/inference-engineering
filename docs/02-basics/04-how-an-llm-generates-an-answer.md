# 4. How Does GPT Actually Generate an Answer?

## The Three Pieces Involved

- The **model** has learned parameters.
- The **GPU** can perform the model's computations.
- **Inference software** manages the process of serving requests.

---

## Step 1: Type a Prompt → Tokenization

```text
Prompt: "What is AI?"
```

- The language model processes a **numerical representation** of that text.
- Text is divided into smaller units called **tokens**.
- Tokens → **token IDs** → numerical identifiers.

A token might be:

- A whole word
- Punctuation
- (or) another text unit

> [!IMPORTANT]
> Each token maps to an **identifier in the model's vocabulary**, and that identifier is used to obtain a **numerical representation**.

**Why?** Because neural networks perform mathematical computations on **numerical data**, not directly on ordinary text characters as humans read them.

### Terms

| Term          | Meaning                                              |
| ------------- | ---------------------------------------------------- |
| **Tokenizer** | Converts text into tokens & token IDs                |
| **Token ID**  | A number identifying a token in the model's vocabulary |
| **Embedding** | A learned numerical representation of a token        |

---

## Step 2: What Next? → Predicting the Next Token

```text
"The sun rises in the ..."
```

The language model processes the **available context** & calculates a **probability distribution over possible next tokens**.

### Next Token Probabilities

| Candidate token | Probability |
| --------------- | ----------- |
| East            | 72%         |
| morning         | 12%         |
| ⋮               | ⋮           |

- The model computes scores for possible next tokens & a **decoding procedure** picks the next one.
- → The model can use the new token along with existing content to predict another token.
- It continues generating tokens until it reaches an appropriate **stopping condition**.

> [!NOTE]
> **Auto-regressive generation** produces a sequence by predicting each next token, **conditioned on the preceding context & previously generated tokens**.

---

## Step 3: Why This Matters to an Inference Engineer

If a model must generate **500 tokens**, the GPU needs to perform **repeated generation steps**.

- These steps consume computation.
- For large models → substantial **memory bandwidth** & GPU resources.

Imagine **5000 users** are generating responses at the same time.

→ The inference engine must **coordinate their work**.

→ It needs to decide:

- How requests **share GPU capacity**
- How to **manage the growing context** of each request
- How to **avoid wasting hardware resources**

---

## Step 4: Two Phases

| Phase       | What happens                                                                                      |
| ----------- | ------------------------------------------------------------------------------------------------- |
| **Prefill** | The model processes the input prompt & builds the initial internal state needed for generation    |
| **Decode**  | The model generates subsequent tokens, generally one token per sequence per generation step       |

> [!IMPORTANT]
> These phases have **different performance characteristics**.
> Understanding that difference is essential for optimizing **"real inference systems"**.
