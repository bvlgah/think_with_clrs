# Problems

## 32-1 String matching based on repetition factors

Let ![yi][y ^ i] denote the concatenation of string ![y][y] with itself ![i][i] times.
For example, ![ab^3][\left( ab \right) ^ 3 = abababa].
We say that a string ![x_in_Sigma][x \in \Sigma ^ *] has repetition factor ![r][r]
if ![x_eq_yr][x = y ^ r] for some string ![y_in_sigma][y \in \Sigma ^ *] and
![r_gt_0][r > 0]. Let ![rho_x][\rho \left( x \right)] denote the largest ![r][r]
such that ![x][x] has repetition factor ![r][r]. What is the running time of your
algorithm?

**a.** Give an efficient algorithm that takes as input a pattern ![pattern][P \left\[ 1 .. m \right\]]
and computes the value ![rho_pi][\rho \left( P_i \right)] for ![i_range][i = 1, 2, ..., m].

[Andrew Lohr][solutions to chapter 32 of CLRS] gave a inspiring solution. More details are added to it as follows.

if ![Pi_eq_yir][P_i = y_i ^ r] for some string ![yi_in_sigma][y_i \in \Sigma ^ *] and
![r_gt_0][r > 0], then ![yj_suffix_pi][y ^ j \sqsupset P_i] for ![j_range][j = \left\[ 1, 2, ..., r - 1 \right\]].
Let ![y_size_eq_k][\left| y_i \right| = k], ![pjk_suffix_pi][P_{jk} \sqsupset P_i],
then ![jk_in_pi_star][jk \in \pi ^ * \left\[ i \right\]]. Since ![r-1k_lte_pii][\left( r - 1 \right) k \leq \pi \left\[ i \right\]], 
![i_minus_r-1k][i - \left( r - 1 \right) k = r k - (r - 1) k = k \geq i - \pi \left\[ i \right\]]. There are
two case about ![i_minus_pii][i - \pi \left\[ i \right\]] to consider.

**Case 1.** If ![i_mod_i_minus_pii_eq_zero][i \mod \left( i - \pi \left\[ i \right\] \right) = 0], then ![k_eq_i_minus_pii][k = i - \pi \left\[ i \right\]].

**Case 2.** If ![i_mod_i_minus_pii_ne_zero][i \mod \left( i - \pi \left\[ i \right\] \right) \ne 0],
let ![l_eq_i_minus_pii][l = i - \pi \left\[ i \right\]], ![k][k] must be greater than ![l][l].
Assume ![k_lt_i][k < i], we know ![pl_size_lt_pk_size][\left| P_l \right| < \left| P_k \right|].
Since ![pik_eq_pki][P_{i - k} = P \left\[ k + 1 \right\] P \left\[ k + 2 \right\] ... P\left\[ i \right\]]
and ![pk_eq_pllk][P_l = P \left\[ k + 1 \right\] P \left\[ k + 2 \right\] ... P \left\[ k + l \right\]],
then ![l_plus_k_eq_k_minus_l_plus_k][l + k = k - l + k \Rightarrow k = 2 l]. If ![k_eq_2l][k = 2 l],
then ![i_mod_l_eq_0][i \mod l = 0]. But we know that ![i_mod_i_minus_pii_ne_zero][i \mod \left( i - \pi \left\[ i \right\] \right) \ne 0].
This contradiction means that ![k_eq_i][k = i].

Finally, the algorithm is:

1. Compute the ![pi][\pi] function.

2. For each ![i][i], compute ![s_eq_i_mod_i_minus_pii][s = i \mod \left( i - \pi \left\[ i \right\] \right)].

3. If ![s_eq_zero][s = 0], ![r_eq_i_divided_by_i_minus_pii][r = \frac{i}{i - \pi \left\[ i \right\]}]; otherwise,
![r_eq_1][r = 1].

The running time of the algorithm is ![o_p_size][O \left( \left| P \right| \right)].


[solutions to chapter 32 of CLRS]: https://sites.math.rutgers.edu/~ajl213/CLRS/Ch32.pdf "solutions to exercises and problems following the chapter 32 of CLRS"

[\left( ab \right) ^ 3 = abababa]: http://latex.codecogs.com/svg.latex?\left(&space;ab&space;\right)&space;^&space;3&space;=&space;abababa "http://latex.codecogs.com/svg.latex?\left( ab \right) ^ 3 = abababa"
[y ^ i]: http://latex.codecogs.com/svg.latex?y&space;^&space;i "http://latex.codecogs.com/svg.latex?y ^ i"
[y]: http://latex.codecogs.com/svg.latex?y "http://latex.codecogs.com/svg.latex?y"
[i]: http://latex.codecogs.com/svg.latex?i "http://latex.codecogs.com/svg.latex?i"
[x \in \Sigma ^ *]: http://latex.codecogs.com/svg.latex?x&space;\in&space;\Sigma&space;^&space;* "http://latex.codecogs.com/svg.latex?x \in \Sigma ^ *"
[r]: http://latex.codecogs.com/svg.latex?i "http://latex.codecogs.com/svg.latex?r"
[x = y ^ r]: http://latex.codecogs.com/svg.latex?x&space;=&space;y&space;^&space;r "http://latex.codecogs.com/svg.latex?x = y ^ r"
[y \in \Sigma ^ *]: http://latex.codecogs.com/svg.latex?y&space;\in&space;\Sigma&space;^&space;* "http://latex.codecogs.com/svg.latex?y \in \Sigma ^ *"
[r > 0]: http://latex.codecogs.com/svg.latex?r&space;>&space;0 "http://latex.codecogs.com/svg.latex?r > 0"
[\rho \left( x \right)]: http://latex.codecogs.com/svg.latex?\rho&space;\left(&space;x&space;\right) "http://latex.codecogs.com/svg.latex?\rho \left( x \right)"
[x]: http://latex.codecogs.com/svg.latex?x "http://latex.codecogs.com/svg.latex?x"
[P \left\[ 1 .. m \right\]]: http://latex.codecogs.com/svg.latex?P&space;\left\[&space;1&space;..&space;m&space;\right\] "http://latex.codecogs.com/svg.latex?P \left\[ 1 .. m \right\]"
[\rho \left( P_i \right)]: http://latex.codecogs.com/svg.latex?\rho&space;\left(&space;P_i&space;\right) "http://latex.codecogs.com/svg.latex?\rho \left( P_i \right)"
[i = 1, 2, ..., m]: http://latex.codecogs.com/svg.latex?i&space;=&space;1,&space;2,&space;...,&space;m "http://latex.codecogs.com/svg.latex?i = 1, 2, ..., m"
[P_i = y_i ^ r]: http://latex.codecogs.com/svg.latex?P_i&space;=&space;y_i&space;^&space;r "http://latex.codecogs.com/svg.latex?P_i = y_i ^ r"
[y_i \in \Sigma ^ *]: http://latex.codecogs.com/svg.latex?y_i&space;\in&space;\Sigma&space;^&space;* "http://latex.codecogs.com/svg.latex?y_i \in \Sigma ^ *"
[y ^ j \sqsupset P_i]: http://latex.codecogs.com/svg.latex?y&space;^&space;j&space;\sqsupset&space;P_i "http://latex.codecogs.com/svg.latex?y ^ j \sqsupset P_i" 
[j = \left\[ 1, 2, ..., r - 1 \right\]]: http://latex.codecogs.com/svg.latex?j&space;=&space;\left\[&space;1,&space;2,&space;...,&space;r&space;-&space;1&space;\right\] "http://latex.codecogs.com/svg.latex?j = \left\[ 1, 2, ..., r - 1 \right\]"
[\left| y_i \right| = k]: http://latex.codecogs.com/svg.latex?\left|&space;y_i&space;\right|&space;=&space;k "http://latex.codecogs.com/svg.latex?\left| y_i \right| = k"
[P_{jk} \sqsupset P_i]: http://latex.codecogs.com/svg.latex?P_{jk}&space;\sqsupset&space;P_i "http://latex.codecogs.com/svg.latex?P_{jk} \sqsupset P_i"
[jk \in \pi ^ * \left\[ i \right\]]: http://latex.codecogs.com/svg.latex?jk&space;\in&space;\pi&space;^&space;*&space;\left\[&space;i&space;\right\] "http://latex.codecogs.com/svg.latex?jk \in \pi ^ * \left\[ i \right\]"
[\left( r - 1 \right) k \leq \pi \left\[ i \right\]]: http://latex.codecogs.com/svg.latex?\left(&space;r&space;-&space;1&space;\right)&space;k&space;\leq&space;\pi&space;\left\[&space;i&space;\right\] "http://latex.codecogs.com/svg.latex?\left( r - 1 \right) k \leq \pi \left\[ i \right\]"
[i - \left( r - 1 \right) k = r k - (r - 1) k = k \geq i - \pi \left\[ i \right\]]: http://latex.codecogs.com/svg.latex?i&space;-&space;\left(&space;r&space;-&space;1&space;\right)&space;k&space;=&space;r&space;k&space;-&space;(r&space;-&space;1)&space;k&space;=&space;k&space;\geq&space;i&space;-&space;\pi&space;\left\[&space;i&space;\right\] "http://latex.codecogs.com/svg.latex?i - \left( r - 1 \right) k = r k - (r - 1) k = k \geq i - \pi \left\[ i \right\]"
[i - \pi \left\[ i \right\]]: http://latex.codecogs.com/svg.latex?i&space;-&space;\pi&space;\left\[&space;i&space;\right\] "http://latex.codecogs.com/svg.latex?i - \pi \left\[ i \right\]"
[i \mod \left( i - \pi \left\[ i \right\] \right) = 0]: http://latex.codecogs.com/svg.latex?i&space;\mod&space;\left(&space;i&space;-&space;\pi&space;\left\[&space;i&space;\right\]&space;\right)&space;=&space;0 "http://latex.codecogs.com/svg.latex?i \mod \left( i - \pi \left\[ i \right\] \right) = 0"
[k = i - \pi \left\[ i \right\]]: http://latex.codecogs.com/svg.latex?k&space;=&space;i&space;-&space;\pi&space;\left\[&space;i&space;\right\] "http://latex.codecogs.com/svg.latex?k = i - \pi \left\[ i \right\]"
[i \mod \left( i - \pi \left\[ i \right\] \right) \ne 0]: http://latex.codecogs.com/svg.latex?i&space;\mod&space;\left(&space;i&space;-&space;\pi&space;\left\[&space;i&space;\right\]&space;\right)&space;\ne&space;0 "http://latex.codecogs.com/svg.latex?i \mod \left( i - \pi \left\[ i \right\] \right) \ne 0"
[l = i - \pi \left\[ i \right\]]: http://latex.codecogs.com/svg.latex?l&space;=&space;i&space;-&space;\pi&space;\left\[&space;i&space;\right\] "http://latex.codecogs.com/svg.latex?l = i - \pi \left\[ i \right\]"
[k]: http://latex.codecogs.com/svg.latex?k "http://latex.codecogs.com/svg.latex?k"
[l]: http://latex.codecogs.com/svg.latex?l "http://latex.codecogs.com/svg.latex?l"
[k < i]: http://latex.codecogs.com/svg.latex?k&space;<&space;i "http://latex.codecogs.com/svg.latex?k < i"
[\left| P_l \right| < \left| P_k \right|]: http://latex.codecogs.com/svg.latex?\left|&space;P_l&space;\right|&space;<&space;\left|&space;P_k&space;\right| "http://latex.codecogs.com/svg.latex?\left| P_l \right| < \left| P_k \right|"
[P_{i - k} = P \left\[ k + 1 \right\] P \left\[ k + 2 \right\] ... P\left\[ i \right\]]: http://latex.codecogs.com/svg.latex?P_{i&space;-&space;k}&space;=&space;P&space;\left\[&space;k&space;&plus;&space;1&space;\right\]&space;P&space;\left\[&space;k&space;&plus;&space;2&space;\right\]&space;...&space;P\left\[&space;i&space;\right\] "http://latex.codecogs.com/svg.latex?P_{i - k} = P \left\[ k + 1 \right\] P \left\[ k + 2 \right\] ... P\left\[ i \right\]"
[P_l = P \left\[ k + 1 \right\] P \left\[ k + 2 \right\] ... P \left\[ k + l \right\]]: http://latex.codecogs.com/svg.latex?P_l&space;=&space;P&space;\left\[&space;k&space;&plus;&space;1&space;\right\]&space;P&space;\left\[&space;k&space;&plus;&space;2&space;\right\]&space;...&space;P&space;\left\[&space;k&space;&plus;&space;l&space;\right\] "http://latex.codecogs.com/svg.latex?P_l = P \left\[ k + 1 \right\] P \left\[ k + 2 \right\] ... P \left\[ k + l \right\]"
[l + k = k - l + k \Rightarrow k = 2 l]: http://latex.codecogs.com/svg.latex?l&space;&plus;&space;k&space;=&space;k&space;-&space;l&space;&plus;&space;k&space;\Rightarrow&space;k&space;=&space;2&space;l "http://latex.codecogs.com/svg.latex?l + k = k - l + k \Rightarrow k = 2 l"
[k = 2 l]: http://latex.codecogs.com/svg.latex?k&space;=&space;2&space;l "http://latex.codecogs.com/svg.latex?k = 2 l"
[i \mod l = 0]: http://latex.codecogs.com/svg.latex?i&space;\mod&space;l&space;=&space;0 "http://latex.codecogs.com/svg.latex?i \mod l = 0"
[k = i]: http://latex.codecogs.com/svg.latex?k&space;=&space;i "http://latex.codecogs.com/svg.latex?k = i"
[s = i \mod \left( i - \pi \left\[ i \right\] \right)]: http://latex.codecogs.com/svg.latex?s&space;=&space;i&space;\mod&space;\left(&space;i&space;-&space;\pi&space;\left\[&space;i&space;\right\]&space;\right) "http://latex.codecogs.com/svg.latex?s = i \mod \left( i - \pi \left\[ i \right\] \right)"
[s = 0]: http://latex.codecogs.com/svg.latex?s&space;=&space;0 "http://latex.codecogs.com/svg.latex?s = 0"
[r = \frac{i}{i - \pi \left\[ i \right\]}]: http://latex.codecogs.com/svg.latex?r&space;=&space;\frac{i}{i&space;-&space;\pi&space;\left\[&space;i&space;\right\]} "http://latex.codecogs.com/svg.latex?r = \frac{i}{i - \pi \left\[ i \right\]}"
[r = 1]: http://latex.codecogs.com/svg.latex?r&space;=&space;1 "http://latex.codecogs.com/svg.latex?r = 1"
[O \left( \left| P \right| \right)]: http://latex.codecogs.com/svg.latex?O&space;\left(&space;\left|&space;P&space;\right|&space;\right) "http://latex.codecogs.com/svg.latex?O \left( \left| P \right| \right)"
[\pi]: http://latex.codecogs.com/svg.latex?\pi "http://latex.codecogs.com/svg.latex?\pi"
