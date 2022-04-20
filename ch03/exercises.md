# Growth of Functions

## Exercises

### 3.1-1

Prove <img src="https://i.upmath.me/svg/max(f(n)%2C%20g(b))%20%3D%20%5CTheta%20(f(n)%20%2B%20g(n))" alt="max(f(n), g(b)) = \Theta (f(n) + g(n))" />.

Proof:

Since <img src="https://i.upmath.me/svg/f(n)" alt="f(n)" /> and <img src="https://i.upmath.me/svg/g(n)" alt="g(n)" /> are asymptotically non-negative, there exist
<img src="https://i.upmath.me/svg/n_0" alt="n_0" /> and <img src="https://i.upmath.me/svg/n_1" alt="n_1" /> that <img src="https://i.upmath.me/svg/f(n)%20%5Cge%200" alt="f(n) \ge 0" /> for all <img src="https://i.upmath.me/svg/n%20%5Cge%20n_0" alt="n \ge n_0" /> and
<img src="https://i.upmath.me/svg/g(n)%20%5Cge%200" alt="g(n) \ge 0" /> for all <img src="https://i.upmath.me/svg/n%20%5Cge%20n_1" alt="n \ge n_1" /> respectively. Then, for all
<img src="https://i.upmath.me/svg/n%20%5Cge%20max(n_0%2C%20n_1)" alt="n \ge max(n_0, n_1)" />, let <img src="https://i.upmath.me/svg/c_0%20%3D%20%5Cfrac%7B1%7D%7B2%7D" alt="c_0 = \frac{1}{2}" /> and <img src="https://i.upmath.me/svg/c_1%20%3D%201" alt="c_1 = 1" />, we get

<img src="https://i.upmath.me/svg/%5Cfrac%7B1%7D%7B2%7D%20max(f(n)%2C%20g(n))%20%5Cle%20max(f(n)%2C%20g(n))%20%5Cle%20f(n)%20%2B%20g(n)" alt="\frac{1}{2} max(f(n), g(n)) \le max(f(n), g(n)) \le f(n) + g(n)" />

According to the definition of <img src="https://i.upmath.me/svg/%5CTheta" alt="\Theta" />-notation, <img src="https://i.upmath.me/svg/max(f(n)%2C%20g(b))%20%3D%20%5CTheta%20(f(n)%20%2B%20g(n))" alt="max(f(n), g(b)) = \Theta (f(n) + g(n))" />.

### 3.1-2

Show that <img src="https://i.upmath.me/svg/(n%20%2B%20a)%5Eb%20%3D%20%5CTheta%20(n%5Eb)" alt="(n + a)^b = \Theta (n^b)" /> where <img src="https://i.upmath.me/svg/a" alt="a" /> and <img src="https://i.upmath.me/svg/b" alt="b" /> are real constants
and <img src="https://i.upmath.me/svg/b%20%3E%200" alt="b &gt; 0" />.

What needed is to find positive constants <img src="https://i.upmath.me/svg/c_0" alt="c_0" />, <img src="https://i.upmath.me/svg/c_1" alt="c_1" /> and <img src="https://i.upmath.me/svg/n_0" alt="n_0" /> such that

<img src="https://i.upmath.me/svg/c_0%20%5Cle%20(1%2B%5Cfrac%7Ba%7D%7Bn%7D)%5Eb%20%5Cle%20c_1" alt="c_0 \le (1+\frac{a}{n})^b \le c_1" />

for all <img src="https://i.upmath.me/svg/n%20%5Cge%20n_0" alt="n \ge n_0" />. Choosing
<img src="https://i.upmath.me/svg/%5Cdelimitershortfall%3D-1pt%20n_0%20%3D%202%5Cleft%5Clceil%20%7Ca%7C%20%5Cright%5Crceil" alt="\delimitershortfall=-1pt n_0 = 2\left\lceil |a| \right\rceil" />,
<img src="https://i.upmath.me/svg/c_0%20%3D%20%5Cfrac%7B1%7D%7B2%7D" alt="c_0 = \frac{1}{2}" /> and <img src="https://i.upmath.me/svg/c_1%20%3D%20%5Cfrac%7B3%7D%7B2%7D" alt="c_1 = \frac{3}{2}" /> makes the inequalities hold.

### 3.1-3

Is <img src="https://i.upmath.me/svg/2%5E%7Bn%20%2B%201%7D%20%3D%20O(2%5En)" alt="2^{n + 1} = O(2^n)" />? Is <img src="https://i.upmath.me/svg/2%5E%7B2%5En%7D%20%3D%20O(2%5En)" alt="2^{2^n} = O(2^n)" />?

Since <img src="https://i.upmath.me/svg/2%5En%20%5Cle%202%5E%7Bn%20%2B%201%7D%20%5Cle%202%20%5Ccdot%202%5En" alt="2^n \le 2^{n + 1} \le 2 \cdot 2^n" />, the answer to the first question is yes.

The short answer to the second one is not because <img src="https://i.upmath.me/svg/2%5E%7B2%5En%7D" alt="2^{2^n}" /> always "grows" faster
than <img src="https://i.upmath.me/svg/2%5En" alt="2^n" />.

