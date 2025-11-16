---
layout: post
title: "Why We Rarely Use Z-tests and Almost Always Use t-tests"
date: 2025-11-16 +0900
---
# Z-test vs t-test: Why We Usually Use the t-test 📏

When we compare **means** in statistics, we often hear about the **t-test**.  
But originally, there is another test called the **Z-test**.  
Understanding the difference helps you see **why the t-test is so important in real data analysis**.

---

## 1. Z-test: The Ideal Case (Almost Never in Real Life)

A **Z-test** is used when we know *almost everything* about the population.

### When Is a Z-test Used?
We want to compare a **sample mean** to a **known population mean**, or the mean of another group.

We assume we know the **true population standard deviation (σ)**.

In that situation, we can compute a **Z-score**:

\[
Z = \frac{\bar{X} - \mu_0}{\sigma / \sqrt{n}}
\]

- \(\bar{X}\): sample mean  
- \(\mu_0\): hypothesized population mean  
- \(\sigma\): **known** population standard deviation  
- \(n\): sample size  

Then we use the **standard normal distribution** (N(0, 1)) to find a **p-value**.

### Problem

In real life, we **almost never** know the true population standard deviation σ.  
That’s why the **pure Z-test is rare** outside of textbooks and some theoretical examples.

So what do we do when σ is unknown?  
**We estimate it using the sample.** That leads us to the **t-test**!

---

## 2. t-test: The Practical Tool for Comparing Means

The **t-test** is designed for the more realistic situation.

We **do not know** the population standard deviation,  and we only have a **sample** to estimate it.

### Main Idea

Instead of using the true σ, we use the **sample standard deviation (s)**.  
This introduces extra uncertainty, so the sampling distribution is no longer exactly normal.  

To handle this, we use the **t-distribution**:

- Looks similar to the normal distribution  
- Has **heavier tails** (more probability in the extremes)  
- Depends on **degrees of freedom (df)**, related to sample size

The basic **t-statistic** looks like this:

\[
t = \frac{\bar{X} - \mu_0}{s / \sqrt{n}}
\]

- \(\bar{X}\): sample mean  
- \(\mu_0\): value under the null hypothesis  
- \(s\): sample standard deviation (estimate of σ)  
- \(n\): sample size  

We then compare this t-value to the **t-distribution** with \(n - 1\) degrees of freedom and compute a **p-value**.

---

## 3. When Do We Use a t-test?

- The outcome variable is **continuous** (e.g., height, score, time)
- We want to compare **means**
- We **don’t know** the population standard deviation (almost always the case)
- The sample is not extremely small, and the data is approximately **normally distributed**

---

## 4. Assumptions of the t-test

To interpret a t-test correctly, we usually assume:

1. **Independence**  
   Each observation is independent of the others (no duplicates, no strong dependencies).

2. **Approximate normality**  
   The data is **approximately normally distributed**,  especially important for small samples.  
   For larger samples, the t-test is quite robust.

3. **Homogeneity of variance (for some versions)**  
   For the classic independent t-test, we assume both groups have **similar variances**.  
   If not, we use Welch’s t-test.

---

## 5. Relationship Between Z-test and t-test

You can think of the t-test as a **realistic version** of the Z-test.

As the **sample size grows** (n → large),  
the t-distribution becomes very close to the normal distribution,  
so **t-test and Z-test give almost the same result** for large samples.

---

## Summary

- The **Z-test** is like a test for a world where we know everything about the population.  
  → Great for theory, rare in practice.

- The **t-test** is what we actually use.
  - We **don’t know the population standard deviation**, so we estimate it with our data.  
  - We compare means using the **t-distribution**, which accounts for this extra uncertainty.

> In data analysis, when you think “I want to compare means,”  
> you can almost always think “**t-test**,” not “Z-test.”
