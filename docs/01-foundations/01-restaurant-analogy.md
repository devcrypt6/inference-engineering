# 1. Imagine You Own a Restaurant

## The Setup

A customer walks into the restaurant and says:

> **"I want pizza"**

```text
┌───────────────────────────────┐
│ Restaurant           ┌──────┐ │            Customer
│                      │ desk │ │  ◄─────    "I want pizza"
│                      └──────┘ │
└───────────────────────────────┘
            Backend
```

## What the Backend Does

1. Receive → customer's order
2. Send it to kitchen
3. Prepare pizza
4. Serve the pizza to customer

---

## Now Imagine the Restaurant Becomes Popular

> Imagine if the restaurant is **incredibly popular**.

- **10K customers** arrive at the same time.
- How to handle these kinds of situations?

### Problems

| #   | Problem                                         |
| --- | ----------------------------------------------- |
| 1   | Kitchen cannot prepare food fast enough         |
| 2   | Customers have to wait                          |
| 3   | Better equipment, more chefs                    |
| 4   | Decide → how to handle many orders efficiently  |
| 5   | Need to control → cost of running the restaurant |

---

## Key Takeaway

> [!IMPORTANT]
> Knowing how to cook pizza is **not enough** to run a restaurant serving 10K customers.
>
> Need to **engineer** the entire process so it works **efficiently at scale**.
