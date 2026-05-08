# Probability and Bayesian Logic Documentation

## 1. Core Conditional Probability Formula

### The Foundation
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

**Example Calculation:**
* $P(B) = 0.72$
* $P(A \cap B) = 0.41$
* $P(A|B) \approx 0.57$

**Definition:**
$A \cap B$ is the part of $B$ where $A$ also happens.

**Meaning:**
Probability of A GIVEN B occurred = portion of B-space where A also exists.

### Intuition
This is the most important intuition. Conditional probability is basically **shrinking the universe** from all possibilities to only worlds where B is true. 

Then asking: “How often does A happen inside that restricted world?”

---

## 2. Multiplication Rule

### Rearranging the Formula
$$P(A \cap B) = P(A|B)P(B)$$
$$P(A \cap B) = P(B|A)P(A)$$

**Example Calculation:**
* $P(A) = 0.60$
* $P(B|A) = 0.35$
* $P(A \cap B) \approx 0.21$

### Interpretation
Joint probability = conditional probability × base probability.

This formula appears everywhere:
* Bayes
* Machine Learning
* Markov systems
* Trading transitions
* Signal chains

---

## 3. Independence Formula

### Definition
If A and B are independent:
$$P(A|B) = P(A)$$

**Meaning:**
Knowing B changes NOTHING about A.

### Formula
$$P(A \cap B) = P(A)P(B)$$

**Example Calculation:**
* $P(A) = 0.60$
* $P(B) = 0.45$
* $P(A \cap B) \approx 0.27$

**Critical Intuition:**
Most real-world systems are NOT independent, especially markets.

---

## 4. Law of Total Probability

### Framework
$$P(A) = \sum_{i} P(A|B_i)P(B_i)$$

**Meaning:**
Overall probability = weighted sum across all possible states.

### State-Based Thinking
This is huge for state-based thinking. 
**Mental Example:**
$P(\text{market up}) = P(\text{up} | \text{trending}) \cdot P(\text{trending}) + P(\text{up} | \text{ranging}) \cdot P(\text{ranging}) + P(\text{up} | \text{panic}) \cdot P(\text{panic})$

---

## 5. Bayes’ Theorem

### The Formula
$$P(A|B) = \frac{P(B|A)P(A)}{P(B)}$$

**Example Calculation:**
* $P(B) = 0.25$
* $P(B|A)P(A) = 0.17$
* $P(A|B) \approx 0.68$

**Posterior Logic:**
Posterior = useful evidence / total evidence.

### Intuition
It is not magic; it is conditional probability rearranged algebraically.
* **Posterior** = Likelihood × Prior ÷ Evidence
* **Updated Belief** = (How compatible evidence is with hypothesis × initial belief) ÷ overall probability of evidence.

---

## 6. Complement Rule

### Formula
$$P(A^c) = 1 - P(A)$$

**Meaning:**
If event A does not happen, the remainder of probability space belongs to not-A. This is extremely useful in trading and risk systems.

---

## 7. Union Probability

### Formula
$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

**Example Calculation:**
* $P(A \cup B) \approx 0.80$

**Logic:**
The overlap is subtracted because it was counted twice.

---

## 8. Mutually Exclusive Events

### Definition
If A and B cannot occur together:
$$P(A \cap B) = 0$$

### Formula
$$P(A \cup B) = P(A) + P(B)$$

---

## 9. Odds Form of Bayes

### Formula
$$\text{Posterior Odds} = \text{Prior Odds} \times \text{Likelihood Ratio}$$

### Application
Useful for:
* Trading
* Signal updating
* Hypothesis testing
* Decision systems

**Intuition:**
Move from asking "Is this true?" to "How much should this evidence shift belief?"

---

## 10. The Most Important Mental Model

Conditional probability is fundamentally **state restriction**.

**Example:**
* Suppose $P(\text{rain}) = 0.30$.
* You learn the sky is dark.
* The universe changes. You are no longer sampling from all days; you are sampling from dark-sky days only.
* Conditional probability asks: Inside this restricted state-space, how often does rain occur?

---

## 11. Systems Application

Conditional reasoning aligns with a systems-oriented mindset because it deals with **state transitions under uncertainty**.

**Applications:**
* Trading regimes
* Anomaly detection
* System states
* Behavioral transitions
* Validation logic

---

## 12. Best Way To Build Intuition

Do not memorize formulas. For every probability question, ask:
1. What is the current probability space?
2. What information restricted the space?
3. What changed after new evidence?
4. Which states became more likely?
5. Which states became less likely?

---

## 13. The Key Transition

Master this reflex:
$$P(A) \neq P(A|B)$$

This realization permanently changes how you think about uncertainty.
