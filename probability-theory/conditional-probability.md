# Conditional Probability

## Framework

- Finite sample space
- Permutation
- Combination
- Principle of inclusion-exclusion

## Finite Sample Space

The simplest experiments in which to determine and derive probabilities are those that involve only finitely many possible outcomes. They are exactly what we learned in high school -- the classical model of probability（古典概型）.

## Permutation and Combination

Before we continue our discussion, all our analysis below is based on the two principles that are very intuitive.

**乘法原理** 若进行 $$A_{1}$$ 过程有 $$n_{1}$$ 种方法, 进行 $$A_{2}$$ 过程有 $$n_{2}$$ 种方法,则进行 $$A_{1}$$ 过程后再接着进行 $$A_{2}$$ 过程共有 $$n_{1} \times n_{2}$$ 种方法.

**加法原理** 若进行 $$A_{1}$$ 过程有 $$n_{1}$$ 种方法,进行 $$A_{2}$$ 过程有 $$n_{2}$$ 种方法,假定 $$A_{1}$$ 过程与 $$A_{2}$$ 过程是并行的,则进行过程 $$A_{1}$$ 或过程 $$A_{2}$$ 的方法共有 $$n_{1}+n_{2}$$种.

Permutation and combination are familiar to most of you. Some differences between them:

- Permutation: without replacement; do care about the order
- Combination: with replacement; don't care about the order

### Tips for Problem Solving

- 不重不漏（which is tricky in some contexts）
- 正难则反：Consider the opposite event (complement of the event) when it's hard to derive the probability

## Principle of Inclusion-Exclusion

For any $$n$$ events $$A_{1}, \ldots, A_{n}$$
$$
\begin{aligned}
\operatorname{Pr}\left(\cup_{i=1}^{n} A_{i}\right)=& \sum_{i=1}^{n} \operatorname{Pr}\left(A_{i}\right)-\sum_{i<j} \operatorname{Pr}\left(A_{i} A_{j}\right)+\sum_{i<j<k} \operatorname{Pr}\left(A_{i} A_{j} A_{k}\right) \\
&-\sum_{i<j<k<l} \operatorname{Pr}\left(A_{i} A_{j} A_{k} A_{l}\right)+\cdots+(-1)^{n+1} \operatorname{Pr}\left(A_{1} A_{2} \cdots A_{n}\right)
\end{aligned}
$$
- How about the intersection of events? Remember that by De Morgan's Law,
$$
A_{1} \cap A_{2} \cap \ldots \cap A_{n}=\left(A_{1}^{C} \cup A_{2}^{C} \cup \ldots \cup A_{n}^{C}\right)
$$
- Usually, here $$P\left(A_{i_{1}} A_{i_{2}} \ldots A_{i_{j}}\right)$$ is an unchanged constant for a fixed $$j$$. So you just have to figure the expression for $$j$$.
