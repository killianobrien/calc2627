---
title: "Riemann integral exercises with solutions"
author: Killian O'Brien
---

## Summation formulae

Recall the summation formulae for consecutive powers we used in the lecture.

* $$\sum_{j=1}^n j = \frac{n(n+1)}{2},$$
* $$\sum_{j=1}^n j^2 = \frac{n(n+1)(2n+1)}{6},$$
* $$\sum_{j=1}^n j^3 = \frac{n^2(n+1)^2}{4}$$

### 1. Arithmetic sequences

Use the formula for the sum of first powers to develop a general formula for summing the first $n$ terms of an arithmetic sequence, with initial term $b$ and constant difference $a$, i.e.

$$
\sum_{m=0}^{n-1}(am+b)=\dots.
$$

#### Solution

Using linearity of summation,

$$
\sum_{m=0}^{n-1}(am+b)
=
a\sum_{m=0}^{n-1}m+b\sum_{m=0}^{n-1}1.
$$

Since

$$
\sum_{m=0}^{n-1}m
=
\frac{(n-1)n}{2}
$$

and

$$
\sum_{m=0}^{n-1}1=n,
$$

we obtain

$$
\sum_{m=0}^{n-1}(am+b)
=
a\frac{n(n-1)}{2}+bn.
$$

Factoring out $n$ gives the compact form

$$
\boxed{
\sum_{m=0}^{n-1}(am+b)
=
n\left(b+\frac{a(n-1)}{2}\right)
}.
$$

This agrees with the familiar formula

$$
\text{(number of terms)}
\times
\text{(average of first and last terms)}.
$$

---

### 2. Sum of fourth powers

Assume for the moment that there exists a formula for the sum of fourth powers, giving a polynomial of degree $5$ with rational coefficients, of the form

$$
\sum_{i=1}^n i^4
=
q_0+q_1n+q_2n^2+q_3n^3+q_4n^4+q_5n^5.
$$

- By sampling this formula for various values for $n$, generate a system of six linear equations for the unknown $q_j$.
- The system should have a unique solution. Use Matlab or similar to solve for the $q_j$, thus discovering what the formula is.
- How might we **prove** that this formula holds for all $n\ge1$?

#### Solution

Evaluating at $n=0,1,2,3,4,5$ gives

$$
0=q_0,
$$

$$
1=q_0+q_1+q_2+q_3+q_4+q_5,
$$

$$
17=q_0+2q_1+4q_2+8q_3+16q_4+32q_5,
$$

$$
98=q_0+3q_1+9q_2+27q_3+81q_4+243q_5,
$$

$$
354=q_0+4q_1+16q_2+64q_3+256q_4+1024q_5,
$$

$$
979=q_0+5q_1+25q_2+125q_3+625q_4+3125q_5.
$$

Solving this system yields

$$
q_0=0,\qquad
q_1=-\frac{1}{30},\qquad
q_2=0,
$$

$$
q_3=\frac13,\qquad
q_4=\frac12,\qquad
q_5=\frac15.
$$

Hence

$$
\sum_{i=1}^n i^4
=
\frac15n^5+\frac12n^4+\frac13n^3-\frac1{30}n.
$$

Factoring gives the standard formula

$$
\boxed{
\sum_{i=1}^n i^4
=
\frac{n(n+1)(2n+1)(3n^2+3n-1)}{30}
}.
$$

To prove the formula, one can use **mathematical induction**.

**Base case:** $n=1$:

$$
1^4=1
$$

and

$$
\frac{1\cdot2\cdot3\cdot(3+3-1)}{30}
=
1.
$$

So the formula is true for $n=1$.

**Inductive step:** Assume the formula holds for some $n$. Then

$$
\sum_{i=1}^{n+1} i^4
=
\sum_{i=1}^{n} i^4 +(n+1)^4.
$$

Substituting the induction hypothesis and simplifying shows that

$$
\sum_{i=1}^{n+1} i^4
=
\frac{(n+1)(n+2)(2n+3)\bigl(3(n+1)^2+3(n+1)-1\bigr)}{30},
$$

which is precisely the required formula with $n$ replaced by $n+1$.

Therefore the formula holds for all $n\ge1$.

---

## Partitions

### 3. Equally-spaced partitions

Consider a general interval $[a,b]$ of real numbers, where $a<b$. Write down the general formula for the equally-spaced partition of $[a,b]$ into $n$ sub-intervals.

$$
x_i=\dots \qquad (0\le i\le n).
$$

Then give formulae for the different possible strategies for choosing the representative points $x_i^*$ using the left-hand edge points, right-hand edge points or mid-points of the sub-intervals.

$$
x_i^*=\dots \qquad (1\le i\le n).
$$

#### Solution

The width of each subinterval is

$$
\Delta x=\frac{b-a}{n}.
$$

The equally spaced partition points are

$$
\boxed{
x_i=a+i\Delta x
=
a+\frac{i(b-a)}{n}
\qquad (0\le i\le n).
}
$$

For the left-endpoint rule,

$$
\boxed{
x_i^*=x_{i-1}
=
a+\frac{(i-1)(b-a)}{n}
}.
$$

For the right-endpoint rule,

$$
\boxed{
x_i^*=x_i
=
a+\frac{i(b-a)}{n}
}.
$$

For the midpoint rule,

$$
x_i^*
=
\frac{x_{i-1}+x_i}{2}.
$$

Substituting the formulas for the partition points,

$$
\boxed{
x_i^*
=
a+\left(i-\frac12\right)\frac{b-a}{n}.
}
$$

---

## A Riemann integral

### 4. Evaluate a Riemann integral

Set up and evaluate a Riemann integral for the definite integral $J$, using equally spaced partitions and your preferred choice of representative points,

$$
J=\int_{-2}^{1}3x^2\,dx.
$$

#### Solution

Choose right endpoints.

The interval is $[-2,1]$, so

$$
\Delta x=\frac{1-(-2)}{n}
=
\frac3n.
$$

The partition points are

$$
x_i=-2+\frac{3i}{n}.
$$

The Riemann sum is

$$
J
=
\lim_{n\to\infty}
\sum_{i=1}^{n}
3\left(-2+\frac{3i}{n}\right)^2
\frac3n.
$$

Expanding,

$$
3\left(-2+\frac{3i}{n}\right)^2
=
12-\frac{36i}{n}
+\frac{27i^2}{n^2}.
$$

Hence

$$
J
=
\lim_{n\to\infty}
\left[
\frac{36}{n}\sum_{i=1}^{n}1
-\frac{108}{n^2}\sum_{i=1}^{n}i
+\frac{81}{n^3}\sum_{i=1}^{n}i^2
\right].
$$

Using

$$
\sum_{i=1}^{n}1=n,
\qquad
\sum_{i=1}^{n}i=\frac{n(n+1)}2,
\qquad
\sum_{i=1}^{n}i^2=\frac{n(n+1)(2n+1)}6,
$$

we obtain

$$
J
=
\lim_{n\to\infty}
\left[
36
-54\frac{n+1}{n}
+\frac{81}{6}
\frac{n(n+1)(2n+1)}{n^3}
\right].
$$

Taking the limit,

$$
J
=
36-54+\frac{81}{6}\cdot 2
=
36-54+27
=
9.
$$

Therefore

$$
\boxed{
\int_{-2}^{1}3x^2\,dx = 9.
}
$$