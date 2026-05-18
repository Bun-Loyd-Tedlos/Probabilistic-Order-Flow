# Probabilistic Order Flow Trading Model (Conceptual Design)

## 1. System Objective

The objective of this system is to estimate the probability of a profitable trade outcome under current market conditions.

<img width="530" height="187" alt="image" src="https://github.com/user-attachments/assets/fa96284a-b17d-4b50-9c17-3df8de66dd7f" />

---

## 2. Core Idea

This system does not predict price directly.

Instead, it models:

> the probability that a trade will succeed given the current balance of buying and selling pressure in the market.

It is a **trade outcome probability model**, not a price forecasting model.

---

## 3. Market Assumption

Price movement is the result of continuous interaction between two opposing forces:

- Buying pressure (demand for upward execution)
- Selling pressure (demand for downward execution)

At any moment:

> market movement is the net result of competing directional forces

---

## 4. Input Data Concept (Order Flow State)

The model assumes access to or estimation of:

### A. Buying Pressure
Represents aggressive upward participation:
- magnitude of buy-initiated trades
- frequency of buy entries
- intensity of upward price impact

### B. Selling Pressure
Represents aggressive downward participation:
- magnitude of sell-initiated trades
- frequency of sell entries
- intensity of downward price impact

### C. Derived Flow Imbalance
A combined representation of market pressure:
<img width="458" height="53" alt="image" src="https://github.com/user-attachments/assets/3249da33-65dc-4880-b642-691cbf5cd3fb" />

---

## 5. Feature Conceptualization

### Buy-side features
- buy volume intensity
- upward price impact magnitude
- frequency of buy aggression

### Sell-side features
- sell volume intensity
- downward price impact magnitude
- frequency of sell aggression

### Relative features
- buy/sell imbalance ratio
- net directional pressure
- short-term dominance shifts

---

## 6. Model Output

The output is a probability:

\[
P(\text{winning trade})
\]

or equivalently:
- probability that price moves in favor of a given trade direction
- expected success rate conditioned on current flow conditions

---

## 7. Key Modeling Principle

This system is fundamentally:

> a conditional probability model of trade outcome based on market participation imbalance.

It does NOT assume deterministic behavior, but statistical likelihoods derived from observed flow conditions.

---

## 8. Interpretation of the Model

The model answers:

> “Given current buying and selling pressure, what is the likelihood that entering a trade now will result in a positive outcome?”

It does NOT answer:
- what price will be
- who is right (buyers or sellers)
- long-term valuation of the asset

---

## 9. Nature of the System

- Probabilistic model (not deterministic)
- Microstructure-inspired system (not purely technical analysis)
- Trade-expectancy estimator (not a forecasting tool)

---

## 10. Required Data Hierarchy

### Ideal (true order flow model)
- tick trades
- bid/ask classification
- order book depth (Level 2)
- volume at aggressor side

### Approximate (if true order flow is unavailable)
- OHLC-derived proxies
- volume-based estimations
- directional movement decomposition

---

## 11. Key Conceptual Shift

This system is not:
- price prediction ❌
- indicator-based trading ❌

It is:

> a probabilistic evaluation of trade expectancy based on inferred or observed market flow imbalance ✔

---

## 12. Final Core Definition

> The model estimates the probability of a profitable trade outcome by quantifying the relative strength and imbalance of buying and selling pressure in the market at a given time.
