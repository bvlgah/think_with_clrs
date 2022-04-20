# Growth of Functions

## Exercises

### 3.1-1

Prove $$max(f(n), g(b)) = \Theta (f(n) + g(n))$$.

Proof:

Since $$f(n)$$ and $$g(n)$$ are asymptotically non-negative, there exist
$$n_0$$ and $$n_1$$ that $$f(n) \ge 0$$ for all $$n \ge n_0$$ and
$$g(n) \ge 0$$ for all $$n \ge n_1$$ respectively. Then, for all
$$n \ge max(n_0, n_1)$$, let $$c_0 = \frac{1}{2}$$ and $$c_1 = 1$$, we get

$$\frac{1}{2} max(f(n), g(n)) \le max(f(n), g(n)) \le f(n) + g(n)$$

According to the definition of $$\Theta$$-notation,
$$max(f(n), g(b)) = \Theta (f(n) + g(n))$$.

### 3.1-2

Show that $$(n + a)^b = \Theta (n^b)$$ where $$a$$ and $$b$$ are real
constants and $$b > 0$$.

What needed is to find positive constants $$c_0$$, $$c_1$$ and $$n_0$$
such that

$$c_0 \le (1+\frac{a}{n})^b \le c_1$$

for all $$n \ge n_0$$. Choosing
$$\delimitershortfall=-1pt n_0 = 2\left\lceil |a| \right\rceil$$,
$$c_0 = \frac{1}{2}$$ and $$c_1 = \frac{3}{2}$$ makes the inequalities hold.

### 3.1-3

Is $$2^{n + 1} = O(2^n)$$? Is $$2^{2^n} = O(2^n)$$?

Since $$2^n \le 2^{n + 1} \le 2 \cdot 2^n$$, the answer to the first
question is yes.

The short answer to the second one is not because $$2^{2^n}$$ always "grows"
faster than $$2^n$$.

