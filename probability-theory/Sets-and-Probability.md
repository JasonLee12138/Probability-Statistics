---
output:
  pdf_document: default
  html_document: default
---


# (PART) Probability Theory {.unnumbered}

# Definition of Probability

This is an introductory lecture to *Probability and Statistics*.

## Experiment

::: {#obs-exp .definition name="Observation and Experiment"}
<br>

The result we see and record is called an **observation**（观测）, and the process of making an observation is called an **experiment**（试验，注意是"试验"）.
:::

::: {#sample-point .definition name="Sample Point"}
<br>

A basic possible outcome of an experiment is called a **sample point**（样本点）.
:::

::: {#sample-space .definition name="Sample Space"}
<br>

The **sample space** (样本空间) for an experiment is the set of all sample points.
:::

::: {#event .definition name="Event"}
<br>

An **event** (事件) is a specific collection of sample points.
:::

简单来说，观测的每一个可能结果都是一个样本点，而某些样本点放在一起构成的集合是一个事件。

同时，并不是随便找一群样本点放在一起构成的集合都可以称为事件，也就是说不是样本空间的每一个子集都可以称为事件（这是因为有的集合实在是太过于奇怪了，以至于无法定义概率，所以我们规定可以称为事件的集合需要满足一定的技术条件，感兴趣的同学可以了解一下$\sigma$代数的概念）。但我们在本课程中遇到的所有集合都是"常规"的、"正常"的，因此我们现阶段可以直接认为事件就是一些样本点构成的集合/样本空间的子集。

## Basic Set Theory

Based on our above-mentioned definitions, the existence of probability is strongly linked with sets. Sample point is the element in the sample space, an event is a set of sample points (or we can say a subset of the sample space), and the sample space refers to the universal set（全集）. We'll review some basic set theory in the following.

### Relations of Set Theory

-   An outcome $s$ is a member of $S$, written as $\boldsymbol{s} \in \boldsymbol{S}$

-   Event $A$ is contained in event $B$ : every outcome that belongs to the subset defining $A$ also belongs to the subset defining $B$, written as $\boldsymbol{A} \subset \boldsymbol{B}$ $$
    \begin{aligned}
    &A \subset B, B \subset A \quad \Rightarrow \quad A=B \\
    &A \subset B, B \subset C \quad \Rightarrow \quad A \subset C
    \end{aligned}
    $$

    -   Please notice that $A=B$ is *defined* as $A \subset B$ and $B \subset A$. When you are required to prove two sets are equal, please follow such paradigm.

-   Empty set: the subset that contains no outcomes, written as $\emptyset$

### Operations of Set Theory

If you have a hard time figuring out the operations and relations of a number of sets, I strongly recommend you to draw a Venn graph（韦恩图） to help visualize the abstract relations.

#### Unions

::: {#union .definition name="Union"}
<br>

The union of $A$ and $B$ is defined to be the event containing all outcomes that belong to either $A$ or $B$, or the event that either $A$ or $B$ would occur.
:::

e.g. $A=\{2,3\}, B=\{3,4\} \Rightarrow A \cup B=\{2,3,4\}$

Some properties:

-   $A \cup B=B \cup A, \quad A \cup A=A$（交换律）
-   $A \cup \phi=A, \quad A \cup S=S$
-   $A \subset B \Rightarrow A \cup B=B$
-   $A \cup B \cup C=(A \cup B) \cup C=A \cup(B \cup C)$（结合律）

Unions of finite sets/countably infinite sets:

-   $\bigcup_{i=1}^{n} A_{i}=A_{1} \cup A_{2} \cup \cdots \cup A_{n}=\left\{\omega: \exists 1 \leqslant i \leqslant n\right.$ 使得 $\left.\omega \in A_{i}\right\}$

    -   the union of n events is defined to be the event which contains all outcomes that belong to at least one of these n events, or the event that at least one of these n events would occur.

-   $\bigcup_{i=1}^{\infty} A_{i}=\bigcup_{i} A_{i}=A_{1} \cup A_{2} \cup \cdots:=\left\{\omega: \exists i\right.$ 使得 $\left.\omega \in A_{i}\right\}$

    -   the union of an infinite sequence of events.
    -   涉及到集合的无穷并，可以考虑使用无穷并定义进行证明。

-   集合的并$\cup$对应着逻辑语言中的"存在"

#### Intersections

::: {#intersections .definition name="Intersection"}
<br>

The intersection of $A$ and $B$ is defined to be the event containing all outcomes that belong both to $A$ and $B$, or the event that both $A$ and $B$ would occur.
:::

e.g. $A=\{2,3\}, B=\{3,4\} \Rightarrow A \cap B=\{3\}$

Some properties:

-   $A \cap B=B \cap A（交换律）, \quad A \cap A=A$
-   $A \cap \phi=\phi, \quad A \cap S=A$
-   $A \subset B \Rightarrow A \cap B=A$
-   $A \cap B \cap C=(A \cap B) \cap C=A \cap(B \cap C)$（结合律）

Intersections of finite sets/countably infinite sets:

-   $\bigcap_{i=1}^{n} A_{i}=A_{1} \cdots A_{n}=\left\{\omega: \omega \in A_{i}, \forall 1 \leqslant i \leqslant n\right\} .$

    -   the intersection of $n$ events is defined to be the event which contains all outcomes that are common to all these $n$ events, or the event that all these $n$ events would occur.

-   $\bigcap_{i=1}^{\infty} A_{i}=\bigcap_{i} A_{i}=A_{1} A_{2} \cdots:=\left\{\omega: \omega \in A_{i} \forall i\right\}$

    -   the intersection of an infinite sequence of events.
    -   涉及到集合的无穷交，可以考虑使用无穷交定义进行证明。

-   集合的交$\cap$对应着逻辑语言中的"任意"

#### Complements

::: {#complements .definition name="Complements"}
<br>

The complement of $A$ is defined to be the event containing all outcomes in $S$ that do not belong to $A$, or the event that event $A$ would not occur.
:::

e.g. $A=\{2,3\} \Rightarrow A^{c}=\{0,1,4,5\}$

Some properties:

$$
\begin{array}{ll}
\left(A^{c}\right)^{c}=A, & \phi^{c}=S \quad S^{c}=\phi \\
A \cup A^{c}=S, & A \cap A^{c}=\phi
\end{array}
$$

#### Disjoint events

::: {#dis-eve .definition name="Disjoint events"}
<br>

$A$ and $B$ are disjoint, or mutually exclusive, if they have no outcomes in common. $A \cap B=\phi$
:::

e.g. $A=\{0,1\}, B=\{3,4,5\}$

e.g. partition of the sample space into eight disjoint events according to three events $A_{1}, A_{2}, A_{3}$



#### Summary and Supplement{-}

首先补充差运算的概念（了解即可）：

- 差运算：$A \backslash B:=A \bar{B}$，即从$A$中去除属于$B$的元素
  - 当 $B \subseteq A$ 时, 记为 $A-B$.
  
然后，我们用Venn图总结上面提到的几种集合运算：



在上面，我们已经提到集合的运算定律，总结如下：

1. 交换律: $A \cup B=B \cup A, A B=B A$;
2. 结合律: $(A \cup B) \cup C=A \cup(B \cup C),(A B) C=A(B C)$;
3. 分配律: $(A \cup B) \cap C=A C \cup B C$，$(A \cap B) \cup C=(A \cup C) \cap(B \cup C)$。

对于集合的补运算，我们还有De Morgan律，或者叫对偶原理：

$$
\overline{A \cup B}=\bar{A} \cap \bar{B}, \quad \overline{A \cap B}=\bar{A} \cup \bar{B}
$$
上面的$\bar A = A^C$，即补运算的另一种写法。从对偶原理可知, 交与并可以互相表示，差也可以用它们表示:

$$
\begin{aligned}
&A \cup B=\overline{\bar{A} \cap \bar{B}}, \quad A \cap B=\overline{\bar{A} \cup \bar{B}} \\
&A-B=A \cap \bar{B}=\overline{\bar{A} \cup B}
\end{aligned}
$$

此外，对偶原理也可运用到事件的有限交或并：

$$
\overline{\bigcup_{i=1}^{n} A_{i}}=\bigcap_{i=1}^{n} \bar{A}_{i}, \quad \bigcap_{i=1}^{n} A_{i}=\bigcup_{i=1}^{n} A_{i}
$$

上式有很明显的概率意义:至少发生一个的对立面是一个也不发生；全部发生的对立面是至少有一个不发生。对于可列无穷的情况，上述公式仍然成立。

最后，用一个例子来展示事件的集合表示方法。

::: {#example-01-01 .example}
<br>
若 $A, B, C$ 是三个事件,则

(1) 所有这三个事件都发生可以表示为: $A B C$;

(2) 这三个事件恰好发生一个可以表示为: $A \bar{B} \bar{C}+\bar{A} B \bar{C}+\bar{A} \bar{B} C$;

(3) 这三个事件恰好发生两个可以表示为: $A B \bar{C}+A \bar{B} C+\bar{A} B C$;

(4) 这三个事件中至少发生一个可以表示为: $A \cup B \cup C$ 或 $A \bar{B} \bar{C}+\bar{A} B \bar{C}+\bar{A} \bar{B} C+A B \bar{C}+A \bar{B} C+\bar{A} B C+A B C$;

    还有一种看似复杂的表示法: $\overline{\bar{A} \bar{B} \bar{C}}$, 正是对偶公式, 今后很有用.

(5) $A$ 发生而 $B$ 与 $C$ 都不发生可以表示为: $A \bar{B} \bar{C}$ 或 $A-B-C$ 或 $A-(B \cup C)$;

(6) $A$ 与 $B$ 都发生而 $C$ 不发生可以表示为: $A B \bar{C}$ 或 $A B-C$ 或 $A B-A B C$.

:::


## Definition of Probability

### Definition

There are various (at least three) ways to interpret probability, so your understanding or interpretation of a certain probability can be subjective. However, the definition of Probability is given by three axioms, as the cornerstone of probability theory. We first present the three axioms, and we'll see some explanations why we state these axioms.

::: {#axiom-prob .definition name="Axioms of Probability"}

<br>

- Axiom 1. （非负性）For any event $A, \operatorname{Pr}(A) \geq 0$ 

- Axiom 2. （规范性）$\operatorname{Pr}(S)=1$ 

- Axiom 3. （可列可加性）For every infinite sequence of disjoint events $A_{1}, A_{2}, \ldots$ 

$$
\operatorname{Pr}\left(\cup_{i=1}^{\infty} A_{i}\right)=\sum_{i=1}^{\infty} \operatorname{Pr}\left(A_{i}\right)
$$
:::

A probability measure, or a probability on a sample space $S$ is a specification of numbers $\operatorname{Pr}(A)$ which satisfy Axioms 1,2 , and $3 .$ 

In fact, if we want to give a very formal definition of probability, we need to define what is $sigma$-algebra first (we need it because not every event can be measured, in other words, assigned a probability value; therefore we have to specify a range in which we can talk about probability). However since it's not mentioned in class, there's no need to understand this rather abstract concept (if interested, you can refer to some advanced probability books). All we have to do is to understand where the idea of the three axioms comes from.

（以下内容改编自李贤平的《概率论基础》（第三版））

概率应有什么性质呢？因为概率通过频率稳定性与随机试验相联系，因此我们自然想到概率应有与频率类似的性质。关于频率的性质, 我们总结为非负性, 规范性以及有限可加性。

非负性是很自然的要求，而因为我们需要将概率限制在一定范围内，概率不能够任意大，规范性也是很自然的。至于频率的有限可加性乃至于概率的可列可加性，我们可以从我们高中学习过的两个概率模型考虑。

在古典概型中，概率是通过有利场合数（也就是符合条件的样本个数）与可能结果总数之比来定义的，有限可加性是符合直观并且很容易证明的（互斥事件之并的概率就是每个事件所含的样本数相加除以样本空间的样本总数）。在几何概率中, 情况也类似，但有一点不同，就是它要求对可列个不相容事件之和有可加性，即可列可加性，这是因为长度、面积、体积等测度计算需要做涉及到可列无穷个数的加法。在一般场合，处理可列个事件之和是完全必要的，因此保留这种可列可加性要求看来是合理的。

### Properties

Straightly derived from the definition, we have the following properties:

- $\operatorname{Pr}(\phi)=0$

- For any finite sequence of disjoint events $A_{1}, \ldots, A_{n}$
$$
\operatorname{Pr}\left(\cup_{i=1}^{n} A_{i}\right)=\sum_{i=1}^{n} \operatorname{Pr}\left(A_{i}\right)
$$
  （利用概率的可列可加性，将$A_{n+1},A_{n+2},...$取为$\emptyset$即可证明。）

- For any event $A$,
$$
\operatorname{Pr}\left(A^{c}\right)=1-\operatorname{Pr}(A)
$$
- For any event $A$,
$$
0 \leq \operatorname{Pr}(A) \leq 1
$$

- If $A \subset B$, then $\operatorname{Pr}(A) \leq \operatorname{Pr}(B)$

- For any two events $A$ and $B$,
$$
\operatorname{Pr}(A \cup B)=\operatorname{Pr}(A)+\operatorname{Pr}(B)-\operatorname{Pr}(A B)
$$
  - 可推出布尔不等式：$P(A \cup B) \leqslant P(A)+P(B)$
  
  - 进一步有次可列可加性：$P\left(\bigcup_{n} A_{n}\right) \leqslant \sum_{n} P\left(A_{n}\right)$
  
  - 还可以推出Bonferroni不等式：$P(A B) \geqslant P(A)+P(B)-1$
