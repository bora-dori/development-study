---
layout: post
title: "What Really Matters in Hypothesis Testing: Errors and p-values"
date: 2025-11-09 +0900
---
# Type I & Type II Errors and the Meaning of p-value ✏️

Understanding statistical hypothesis testing is essential in data analysis.  
When we test a claim using sample data, we don’t get absolute certainty. We make a **decision based on probability**.  
That’s why we must understand **two kinds of possible errors (Type I and Type II)** and the role of the **p-value** in drawing conclusions.

---

## 1. Hypothesis Testing in a Nutshell

Every hypothesis test starts with two opposing statements:
- **Null hypothesis (H₀)**: The current or default assumption.  
  *Example:* “The new drug has no effect.”
- **Alternative hypothesis (H₁)**: The claim we want to support.  
  *Example:* “The new drug has an effect.”

We then collect sample data and calculate a **test statistic** to see how far our data deviate from what would be expected if H₀ were true.  
Based on this, we compute a **p-value** and compare it to a **significance level (α)**, typically set at **0.05** (5%).

---

## 2. Type I and Type II Errors

In hypothesis testing, we never know the “true” state of the world for certain.  
This means two kinds of mistakes can occur.

| Reality | Decision | Outcome |
|----------|-----------|----------|
| H₀ is true | Fail to reject H₀ | Correct |
| H₀ is true | Reject H₀ | **Type I Error (False Positive)** |
| H₀ is false | Reject H₀ | Correct |
| H₀ is false | Fail to reject H₀ | **Type II Error (False Negative)** |

---

### Type I Error (α)

- **Definition:** Rejecting the null hypothesis even though it’s actually true.  
- **Interpretation:** You conclude “there is an effect” when none exists.  
- **Example:** Convicting an innocent person.  
- **Probability of occurrence:** **α (alpha)**, the **significance level** set before the test.  
  - If α = 0.05 → you accept a 5% chance of wrongly rejecting a true H₀.

---

### Type II Error (β)

- **Definition:** Failing to reject the null hypothesis when it’s actually false.  
- **Interpretation:** You miss a real effect.  
- **Example:** Letting a guilty person go free.  
- **Probability of occurrence:** **β (beta)**  
- **Power of the test:** \( 1 - β \)  
  - The probability of correctly detecting a true effect when it exists.

---

### ⚖️ Trade-off Between α and β

There’s a balance between being **too strict** and **too lenient**:
- If you **lower α** (make the test more conservative),  
  → Type I error decreases, but Type II error (β) increases.  
- If you **raise α**,  
  → You’re more likely to detect true effects, but also more likely to make false positives.

Thus, most analyses use α = 0.05 as a compromise between both risks.

---

## 3. The Role of the Significance Level (α)

**Significance level (α)** is the threshold that defines how skeptical we are toward new evidence.

> “How strong must the data be before we reject H₀?”
- Commonly set to **5% (0.05)**.  
- Meaning: “We accept up to a 5% chance of making a Type I error.”  
- In critical fields (e.g., medicine, safety), stricter levels like **1% (0.01)** are often used.

---

## 4. What Is the p-value?

The **p-value** quantifies how compatible your data are with the null hypothesis.

> **p-value:**  
> The probability of obtaining results **as extreme as, or more extreme than** the observed data, **assuming the null hypothesis is true.**

### Interpreting the p-value

| Comparison | Statistical Decision | Interpretation |
|-------------|----------------------|----------------|
| **p ≤ α** | Reject H₀ | There’s statistically significant evidence for H₁. |
| **p > α** | Fail to reject H₀ | Not enough evidence to reject H₀. |

> Important:  
> A large p-value **does not prove H₀ true** — it only means we lack sufficient evidence against it.

---

## 5. Why p-values Can Be Misleading

The p-value depends heavily on **sample size**.

- With **large samples**, even tiny differences can yield a small p-value (statistically significant but practically meaningless).  
- With **small samples**, meaningful differences may fail to reach significance.

Therefore, **Statistical significance ≠ Practical importance.**  
You must consider both the **effect size** and **context** of the data.

Example:  
In a business A/B test, a 0.1% click-through improvement might be statistically significant (small p-value) but irrelevant if it doesn’t increase profit.

---

## 6. Putting It All Together

1. **Set hypotheses (H₀, H₁)**  
2. **Decide α** (your tolerance for Type I error)  
3. **Collect data & calculate test statistic**  
4. **Compute p-value**  
5. **Compare p-value to α**  
6. **Draw conclusions**, keeping in mind the potential for Type I and Type II errors.

---

## Summary

> Type I and Type II errors remind us that no statistical test is perfect.  
> The p-value helps us measure how surprising our results are under the null hypothesis 
> But sound judgment, context, and effect size always matter more than a single number.

| Concept | Definition | Symbol | Interpretation |
|----------|-------------|----------|----------------|
| **Type I Error** | Rejecting a true null hypothesis | α | False positive |
| **Type II Error** | Failing to reject a false null hypothesis | β | False negative |
| **Test Power** | Correctly detecting a true effect | 1 - β | Sensitivity |
| **Significance Level** | Threshold for deciding when to reject H₀ | α | Commonly 0.05 |
| **p-value** | Probability of observing extreme results under H₀ | – | Smaller → stronger evidence against H₀ |
