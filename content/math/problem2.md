---
title: "Problem 2"
description: "IMO 2005 Q4"
date: 2020-11-27T18:48:34+01:00
draft: false
markup: "mmark"
---

Show that for all primes $$p$$ there is a $$n \in \N$$ such that

$$2^n + 3^n + 6^n - 1 \equiv 0 \quad (mod \quad p)$$

---END OF GOAL---

This being a modulo problem with primes, we should keep in mind Fermat's Little Theorem:

$$p \space \text{prime}, a \in \N \Rightarrow a^p \equiv a \space (mod \space p)$$

Let's first find $$n$$ for the cases $$p = 2$$ and $$p = 3$$.

$$p = 2; \quad 2 + 3 + 6 - 1 \equiv_2 10 \equiv_2 0$$

$$p = 3; \quad 2^2 + 3^2 + 6^2 - 1 \equiv_3 48 \equiv_3 0$$

Now, we can use Fermat's Little Theorem to state that, if $$p > 3$$,

$$2^{p-1} \equiv 3^{p-1} \equiv 6^{p-1} \equiv 1 \space (mod \space p)$$

so

$$2^{p-2} \equiv_p 2^{-1}, 3^{p-2} \equiv_p 3^{-1}, 6^{p-2} \equiv_p 6^{-1},$$

We need $$p > 3$$ for these inverses to be well defined. We therefore have


$$2^{p-2} + 3^{p-2} + 6^{p-2} \equiv_p 2^{-1} + 3^{-1} + 6^{-1} \equiv_p 6^{-1}(3+2+1)
\equiv_p 6^{-1}(6) \equiv_p 1$$


Which gives us the final result

$$2^{p-2} + 3^{p-2} + 6^{p-2} - 1 \equiv_p 0$$

And we are done.
