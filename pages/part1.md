# Mathematical reasoning

::: warning
The information in this section is being updated.
:::

In this part of the course we work on the following skills:

- Understand the precise meanings of mathematical statements, form our own precise statements, find logic buried in confused statements and describe it in clear terms.
- Manipulate statements, such as finding contrapositives, inconsistencies, special cases or generalizations.
- Form chains of logical manipulations while identifying and fixing mistakes.
- Justify or find counterexamples to our own guesses.

This text is not a comprehensive overview, it is meant only as a reminder and light discussion of the key notions. In a sense logic is innate however our abilities working with logical reasoning can be improved and refined, it is a skill to be studied like any other.

See also the [additional exercises](/pages/exercises1) associated to this part of the course.

## Models, logical consequences

We take the point of view that "doing science" involves developing well-defined models which describe physical phenomena (anything like the trajectory of a projectile, fluid mechanics, economics, etc.) whilst "doing mathematics" involves analysing the logical consequences of these models. The consequences understood by studying the model can then be used to further test the model or design applications which use these physical phenomena.

We need to be rigorous in our reasoning, otherwise, as we will see in some examples, the conclusions can be erroneous and the difficulties are often subtle.

### Curves of constant width

Shortly we will consider examples in calculus but it is worthwhile to consider a real world application of the rigour and reasoning we aspire to. Suppose we are organising the production facilities which manufacture a component that is round (maybe a rocket body, maybe a gas tube, etc.). As part of the production it is important to have a procedure which guarantees that the fabrication is done to the correct tolerance. The idea proposed is:

> "We measure the width from all angles to confirm that the manufactured component is correct."

This is a two-dimensional problem in the sense we assume that the object is a closed curve in $\mathbb{R}^2$. For a given angle we define the width of this curve to be the smallest distance between two parallel lines which touch the curve in a single point but never cross it (one each side of the curve). We say that the curve has constant width if this width is equal from every direction.
This is just what we would check using calipers on a part and rotating. The abstract version of this problem is that we want to show that being a circle follows from constant width. The following statement is intuitive and true.

::: theorem
A circle has constant width.
:::

However the converse is not true, indeed the following is true.

::: theorem
There exist constant width curves which are not circles.
:::

This can be proved by constructing many such curves, for example the [Reuleaux triangle](https://en.wikipedia.org/wiki/Reuleaux_triangle). Indeed there are such curves which look similar to regular polygons but still have constant width.

![Reuleaux triangle](/images/svg/reuleaux.svg "The Reuleaux triangle is a curve of constant width")

## Mathematical statements

Mathematical reasoning proceeds as a sequence of mathematical statements.
Statements are true or false. E.g., $2+2=4$ is a true statement and $2+2=5$ is a false statement. Not all combination of words or mathematical symbols is a statement. E.g.,
$$ =4+\times 4 = - = 3$$
is not a statement, this combination of symbols fails to have meaning. Similarly 
$$0/0 = 1$$
is not a statement since division by zero is not defined. We say such are _ill-formed_ or _ill-defined_. Statements may also contain words or consist entirely of words, e.g.,

> There are infinitely many prime numbers

is a well-formed mathematical statement. Some statements, e.g.,
$$7=7, \quad 5\leq5$$
are true but are unlikely to be useful. On the other hand the statement
$$\pi=22/7$$
is false but could be useful (we could make this a precise statement describing how this is a true approximation).

We say that a combination of symbols such as,
$$2+2$$
is an _expression_, not a statement. This expression produces a value, it is not something that is true or false. As with expression, we must work with _well-defined_ or _well-formed_ expressions.
In order to be mathematically rigorous, we must avoid _ill-defined_ or _ill-formed_ expressions, e.g.,
$$1+{2}/{0}, \quad \sin^{-1}(2).$$
We often make statements out of expressions by using relations (e.g., $=$, $<$, $\in$, $\subset$) or by using properties (e.g., "is prime", "is invertible"). _Compound statements_ can be formed from other statements by using logical connectives (e.g., and, or, not, if, if and only if,...). We will often do this. E.g., the statement

> $2+2=5$ if and only if $4+4=10$

is formed by combining two statements. Note that this statement is well-formed and true (we can prove by calculation). However it is vacuous in the sense that the hypothesis is false.

::: info Exercise
Identify the hypothesis and conclusion in the following statements.

1. If $x$ is a positive real number that satisfies $x^2 − 2x + 1 < 0$, then $x < 1$.
2. If $x$ is a real number, then either $x \leq 0$, $x \geq 0$.
3. If there exists a real number $x$ such that $x^4 + 1 = 0$, then any real number is either an integer or a
   multiple of $\pi$.
4. The inverse of a irrational number is also irrational.
5. For each $x\in\mathbb{R}$ there exists $y\in\mathbb{R}$ such that $x=y^2$.

:::

### Negation

The negation of statements is often essential. Although a rather natural idea this can sometimes become confusing when combined with logical connectives and quantifiers.

| Statement                         | Negation                             |
| --------------------------------- | ------------------------------------ |
| $P$ or $Q$                        | Not $P$ and not $Q$                  |
| $P$ and $Q$                       | Not $P$ or not $Q$                   |
| If $P$, then $Q$                  | $P$ and not $Q$                      |
| For all $x$, $P(x)$               | There exist $x$ such that not $P(x)$ |
| There exists $x$ such that $P(x)$ | For every $x$, not $P(x)$            |

::: info Exercise
Think of day-to-day examples which illustrate the logic described in this table.
:::

::: info Exercise
Find the negation of the following statements

1. Some prime numbers are odd.
2. Nobody is lazy.
3. Some horses are black.
4. For every $x\in\mathbb{R}$, $x^2 \geq 0$.
5. There exists $x\in\mathbb{R}$ such that $x^2 = 7$.
6. For each $x\in\mathbb{R}$ there exists $y\in\mathbb{R}$ such that $x=y^2$.
7. If $x,y\geq 0$ then $\sqrt{x}=\sqrt{y}$ implies that $x=y$.

:::

## Structure of proofs

Be they calculations or logical steps expressed in words, proofs must be a chain of rigorous steps. The correct conclusion without solid logic is not a proof. Typically there are many different ways to write a proof, often very different one to the other. Here we discuss a few possibilities and introduce some terminology so it is easier to discuss when we work with such.

<!-- Two humorous examples with correct conclusions but which are not proofs:
$$
\begin{aligned}
  \frac{16}{64} &= \frac{1\not{6}}{\not{6}4} = \frac{1}{4}, \\
  \frac{d}{dx} \frac{1}{x} &= \frac{d}{d} \frac{1}{x^2} = \frac{\not{d}}{\not{d}} \frac{1}{x^2} = - \frac{1}{x^2}.
\end{aligned}
$$ -->

### Calculation proofs

These are the classic school mathematics problems, often phrased as "evaluate..." or "calculate...".
The proof in these cases is simply a chain of equalities to produce the final result.
Since we already have seen so many of these we instead look at a couple of false proofs and practice our skill at searching for gaps and errors in proofs.

::: info ~~Theorem~~
$5=4$
:::

::: info ~~Proof~~

- Since $-20=-20$ we know that $25 - 45 = 16 -36$.
- Which we rewrite as $5^2 - 5 \times 9 = 4^2 - 4 \times 9$.
- Adding $\frac{81}{4}$ on both sides, $5^2 - 5 \times 9 + \frac{81}{4} = 4^2 - 4 \times 9 + \frac{81}{4}$.
- These are both perfect squares and so $\left(5-\frac{9}{2}\right)^2 = \left(4-\frac{9}{2}\right)^2$.
- Taking the square root of both sides, $5-\frac{9}{2} = 4-\frac{9}{2}$.
- And so $5=4$.

:::

::: info Exercise
In which step in the above argument is there an error?
:::

<!--
Alternatively calculations might be more about geometrical reasoning.
When a proof relies on a picture and an appeal to intuition we must be particularly careful with arguments.

::: info ~~Theorem~~
Every triangle is isosceles.
:::

::: info ~~Proof~~
Start from a triangle $ABC$.
Sketch the triangle and the lines described in the following steps.

- Draw the perpendicular bisector of $BC$, and the angle bisector from $A$.
- Let $I$ be their intersection (if it is not unique, you are done).
- Let $J$ be the projection of $I$ over $AB$, $K$ that over $AC$.
- Considering the right angle triangles $AIJ$ and $AIK$, we see that (lengths) $AJ=AK$, and that $IJ=IK$.
- Then looking at right triangles $BIJ$ and $CIK$, we obtain that $BJ=CK$.
- We conclude that $AB = AJ+JB = AK+KC = AC$.

::: -->

### Proof by cases

A common scenario is when during a proof we must consider two cases depending on whether a certain quantity is zero or otherwise we can divide through by this quantity.
Another example is:

::: theorem
Suppose that $n$ is an integer. Then $n(n+1)$ is an even integer.
:::

::: info Proof

- If $n$ is even, then $n(n+1)$ is also even since the multiple of an even number is even.
- If $n$ is odd, then $n+1$ is even and so $n(n+1)$ is even, again because the multiple of an even number is even.
- Since $n$ is an integer, $n$ is either even or odd so one of these two cases holds.
  :::

Observe that, in the proof, one of the first two statements is vacuous in the sense that only one can be true for a given $n$.

### Proof by contradiction

It is often convenient to prove a statement by supposing that the conclusion is false and showing this contradicts the hypothesis, this is called [proof by contradiction](https://en.wikipedia.org/wiki/Proof_by_contradiction). In the abstract, if $P$ and $Q$ are statements then the statement "If $P$, then $Q$" is equivalent to "Not $Q$, then not $P$".

> Archibald uses an umbrella whenever it rains.
> If we see Archibald isn't using an umbrella then we know that it is not raining.

::: info Problem
Let $x$ and $y$ be real numbers and suppose that $xy > 0$ and $x \geq 0$. Show that $y>0$.
:::

To prove this statement we can suppose, for the sake of contradiction, that $y\leq 0$. Since also $x \geq 0$ this implies that $xy \leq 0$ but this is a contradiction.

### Proof by induction

The principle of [mathematical induction](https://en.wikipedia.org/wiki/Mathematical_induction) is often a powerful technique in proofs.

A statement which is amenable to proof by induction is the following.

> $2^n \geq n+1$ for all natural numbers $n$.

However, let's take this opportunity to discuss what to do when such statements come to us. In the high school world the is no doubt, we are required to follow a procedure that is clearly prescribed.
However as grown up thinkers everything is more open and there are many "correct" solutions. Firstly we need to ask ourselves if the statement is true! In this case we try a few of the smaller natural numbers and we see that it does seem to be true. (If we thought it wasn't true then we would try to find counter examples to prove that it is false.) So now we need to write a proof of the statement. One way to think about this would be to consider the graph $y=2^x-(x+1)$. That this graph lies above the axis is equivalent to the statement being true. We could consider the gradient of $2^x-(x+1)$ and prove that it stays positive. This is a perfectly reasonable proof.

The statement can also be proven by induction in a concise way. To a large degree, the choice of proof is aesthetic.

Again time to practice our skill at finding gaps in proofs.

::: info ~~Theorem~~
All sheep are the same colour.
:::

::: info ~~Proof~~
We prove by induction that a group of $N$ sheep are all the same colour.

- The case $N=1$ is immediate because a single sheep is the same colour as itself.

We will now assume that a group of $N$ sheep are all the same colour and consider a group of $N+1$ sheep.

- Removing a single sheep gives a group of $N$ sheep. Removing a different one gives another group of $N$ sheep.
- Within each group all the sheep are the same colour.
- The two groups have $N-1$ sheep in common so both groups are sheep of the same colour as each other and so all of them are the same colour.

:::

::: info Exercise
Where is the logical gap in the above argument?
:::

## Quantifiers

Almost always, mathematical statements will involve quantifies. As we have already seen, various statements are stated "for all..." or perhaps "there exists... such that". This is a natural concept, like saying "every bird can fly" or "there exists a bird which can swim".

::: info Exercise
What does each of the following statements mean, and which of them are true?

1. For every positive number $x$, and every positive number $y$, we have $y^2=x$.
2. There exists a positive number $x$ such that for every positive number $y$, we have $y^2=x$.
3. There exists a positive number $x$, and there exists a positive number $y$, such that $y^2=x$.
4. For every positive number $y$, there exists a positive number $x$ such that $y^2=x$.
5. There exists a positive number $y$ such that for every positive number $x$, we have $y^2=x$.

:::

The following is more practice for us to understand the process of developing an understanding and proof of a statement.

::: info Problem
Let $a$ be a real number. Suppose that, for every real number $x$, then $a\leq x^2 - 2x$. Show that $a\leq -1$.
:::

As before it is important for us to start by trying things, by guessing and then by adding rigour to the argument.
If we didn't try anything until we were certain of the final answer then we would be severely limiting our potential.

## Optimality of statements

- Can we improve some given result?
- Can we show that the assumptions of a given statement are required?

Recall the following result from Mathematical Analysis 1.

::: theorem
Let $f$ be differentiable on $(a, b)$ and suppose that $f$ takes a local minimum or maximum at the point $c \in (a, b)$. Then $f^{\prime}(c) = 0$.
:::

<!-- ::: theorem
Let $f$ be defined on an open interval $(a, b)$ and assume that $f$ takes a local minimum or a local maximum at the point $c \in (a, b)$.
If $f$ is differentiable at $c$ then $f^{\prime}(c) = 0$.
::: -->

::: info Exercise
Could we improve the statement with a stronger conclusion?
Could we improve the statement with a weaker hypothesis?
:::

Observe that, if we modify the statement with a stronger conclusion or a weaker hypothesis then the new statement implies the original statement. It will often be of practical importance to improve theorems in this way or to show examples which demonstrate that all the hypothesis are required and that it is not possible to strengthen the conclusion. If a statement is an implication then if often makes sense to ask if it can be upgraded to an if-and-only-if statement. Again, if possible, this would produce a statement which implies the original one.

## Why study analysis?

Let's consider some examples which demonstrate some of the motives behind studying analysis (as opposed to calculus).

### Geometric series

The geometric series
$S = 1 + \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + \cdots$
can be summed by the following simple trick.
Multiplying by $2$ we obtain that

$$
  2S = 2 + 1 + \tfrac{1}{2} + \tfrac{1}{4} + \tfrac{1}{8} + \tfrac{1}{16} + \cdots = 2+S
$$

and so $S=2$.
If we try to do the same to the sum
$T = 1 + 2 + 4 + 8 + 16 + \cdots$
we get the nonsensical answer

$$
  2T = 2 + 4 + 8 + 16 + \cdots = T - 1
$$

and so $T = -1$.
Why should we trust the argument in the first case and not in the second?

### Interchanging sums

If we consider any matrix of numbers, for example,

$$
  \left(\begin{smallmatrix}
    1 & 2 & 3 \\
    4 & 5 & 6 \\
    7 & 8 & 9
  \end{smallmatrix}\right)
$$

we can sum first the rows $6 + 15 + 24 = 45$ or first the columns $12 + 15 + 18 = 45$ to obtain the total sum of all numbers.
This is the rule

$$
  \sum_{j=1}^{m} \sum_{k=1}^{n} a_{jk} = \sum_{k=1}^{n} \sum_{j=1}^{m}  a_{jk}.
$$

We would like to believe that also $\sum_{j=1}^{\infty} \sum_{k=1}^{\infty} a_{jk} = \sum_{k=1}^{\infty} \sum_{j=1}^{\infty}  a_{jk}$.
However this doesn't work for the following matrix:

$$
  \left(\begin{smallmatrix}
    1      & 0      & 0      & \cdots \\
    -1     & 1      & 0      & \cdots \\
    0      & -1     & 1      & \cdots \\
    \vdots & \vdots & \vdots & \ddots
  \end{smallmatrix}\right).
$$

We often want to swap the order of summing (or integrating) and often need to consider infinite sums (or integrals). When can we do this and can't we?

### Interchanging integrals

Let's try to integrate $e^{-xy} - xye^{-xy}$ with respect to both $x$ and $y$.
Is the following true?

$$
  \int_{0}^{\infty} \left[ \int_{0}^{1} (e^{-xy} - xye^{-xy}) \ dy \right] \ dx
  \overset{\text{\large ?}}{=} \int_{0}^{1} \left[ \int_{0}^{\infty}  (e^{-xy} - xye^{-xy}) \ dx \right] \ dy.
$$

::: info Exercise
Calculate,

1. $\int_{0}^{1} (e^{-xy} - xye^{-xy}) \ dy = \text{?}$
2. $\int_{0}^{\infty} \left[ \int_{0}^{1} (e^{-xy} - xye^{-xy}) \ dy \right] \ dx = \text{?}$
3. $\int_{0}^{\infty} (e^{-xy} - xye^{-xy}) \ dx = \text{?}$
4. $\int_{0}^{1} \left[ \int_{0}^{\infty}  (e^{-xy} - xye^{-xy}) \ dx \right] \ dy = \text{?}$

Does the order of integration matter?
:::

<!-- Since
$$\int_{0}^{1} (e^{-xy} - xye^{-xy}) \ dy = {\left[ye^{-xy}\right]}_{y=0}^{1} = e^{-x},$$
the left-hand side is equal to
$\int_{0}^{\infty} e^{-x} \ dx = {\left[-e^{-x} \right]}_{0}^{\infty} = 1$.
However, since
$$\int_{0}^{\infty} (e^{-xy} - xye^{-xy}) \ dx = {\left[ xe^{-xy} \right]}_{x=0}^{\infty} = 0,$$
the right-hand side is $\int_{0}^{1} 0 \ dx = 0$.
So how do we know when to trust the interchange of intervals? -->

### Interchanging limits

Similar to the question of exchanging integrals, we could exchange the order of limits.
Is the following true?

$$
  \lim_{x\to 0}\lim_{y\to 0} \frac{x^2}{x^2 + y^2}
  \overset{\text{\large ?}}{=}
  \lim_{y\to 0}\lim_{x\to 0} \frac{x^2}{x^2 + y^2}.
$$

::: info Exercise
Calculate,

1. $\lim_{y\to 0} \frac{x^2}{x^2 + y^2} = \text{?}$
2. $\lim_{x\to 0} \frac{x^2}{x^2 + y^2} = \text{?}$

Does the order of taking limits matter?
What does the graph of this function look like?
:::

<!-- However
$$\lim_{y\to 0} \frac{x^2}{x^2 + y^2} = \frac{x^2}{x^2 + 0} = 1$$
and so the left-hand side is $1$
whereas
$$\lim_{x\to 0} \frac{x^2}{x^2 + y^2} = \frac{0}{0 + y^2} = 0$$
so the right-hand side is $0$. -->

Under what circumstances is it legitimate to swap the order of integration or taking limits?
We need to be rigorous in our logic otherwise, as we have seen in these examples, the conclusions can be erroneous and the difficulties are often subtle.

## Further reading

- Analysis I: Third Edition (Texts and Readings in Mathematics) (2016) by _Terence Tao_ (particularly §1.2 "Why Analysis?" and Appendix A "The basics of mathematical logic")
- [The mechanics of proof](https://hrmacbeth.github.io/math2001/) by _Heather Macbeth_
- How to Think Like a Mathematician: A Companion to Undergraduate Mathematics (2009) by _Kevin Houston_
