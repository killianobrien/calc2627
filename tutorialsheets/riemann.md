---
title: "Riemann integral exercises"
author: Killian O'Brien
---

<head>
		<!-- <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script> -->
		<link rel="preconnect" href="https://fonts.googleapis.com">
		<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
		<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:ital@0;1&display=swap" rel="stylesheet">
		<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Serif&display=swap" rel="stylesheet">
        <style>
            body {
			 /* font-family: 'IBM Plex Sans', sans-serif; */
			 font-family: 'IBM Plex Serif', serif;
             font-size: 0.8em;
             }
             a {
  color: blue;
}
a:visited {
  color: green;
}
a:hover {
  color: hotpink;
}

</style>
</head>

## Summation formulae

Recall the summation formulae for consecutive powers we used in the lecture.

* $$\sum_{j=1}^n j = \frac{n(n+1)}{2},$$
* $$\sum_{j=1}^n j^2 = \frac{n(n+1)(2n+1)}{6},$$
* $$\sum_{j=1}^n j^3 = \frac{n^2(n+1)^2}{4}$$

1. Use the formula for the sum of first powers to develop a general formula for summing a finite arithmetic sequence of the form 
$$ \sum_{m=1}^n (am + b) = \dots .$$

2. Assume for the moment that there exists a formula for the sum of fourth powers, giving a polynomial of degree $5$ with rational coefficients, of the form 
$$ \sum_{i=1}^n i^4 = q_0 + q_1 n + q_2 n^2 + q_3 n^3 + q_4 n^4 + q_5 n^5, \quad (q_j \in \mathbb{Q}).$$
    - By sampling this formula for various values for $n$, generate a system of six linear equations for the unknown $q_j$. 
    - The system should have a unique solution. Use Matlab or similar to solve for the $q_j$, thus discovering what the formula is. 
    - How might we **prove** that this formula holds for all $n \geq 1$?

## Partitions

3. Consider a general interval $[a,b]$ of real numbers, where $a \lt b$. Write down the general formula for the equally-spaced partition of $[a,b]$ into $n$ sub-intervals. 
$$x_i = \dots \quad (0 \leq i \leq n).$$
Then give formulae for the different possible strategies for choosing the representative points $x_i^*$ using the left-hand edge points, right-hand edge points or mid-points of the sub-intervals,
$$x_i^* = \dots \quad (1 \leq i \leq n).$$ 

## A Riemann integral

4. Set up and evaluate a Riemann integral for the definite integral $J$, using equally spaced partitions and your preferred choice of representative points,  
$$J = \int_{-2}^1 3x^2 \, dx.$$