---
title: "Problem 1"
description: "A quick number theory problem"
date: 2020-11-12T16:28:34+01:00
draft: false
markup: "mmark"
---

Find all $$x, y \in \Z_+$$ and primes $$p$$ such that

$$p^x + 1 = y^2$$

---END OF GOAL---

We begin by rearranging and transforming our equation:

$$ \begin{aligned}
  p^x + 1 &= y^2 \\
  p^x &= y^2 - 1 \\
  p^x &= (y+1)(y-1)
\end{aligned} $$


Therefore, we have

$$
 \left.\begin{aligned}
  y+1&=p^a, a \in \Z_+ \\
  y+1&=p^b, b \in \Z_+, a > b
 \end{aligned}\right\}
 \Longrightarrow
 (y+1)-(y-1) = p^a - p^b
 \Longrightarrow
 2 = p^b(p^{a-b} - 1)
$$


This leaves us with two cases:

1) Case 1: $$p^b = 2; p^{a-b} - 1 = 1$$. This gives us $$p=2,a=2,b=1$$.
2) Case 2: $$p^b = 1; p^{a-b} - 1 = 2$$. This gives us $$p=3,a=1,b=0$$.


And therefore the solutions are:

$$\begin{aligned}
  \textbf{p=2, x=3, y=3} \\
  \textbf{p=3, x=1, y=2}
\end{aligned}$$


And we are done.
