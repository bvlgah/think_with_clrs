# String Matching

## Exercises

### 32.4-8

Give an ![runtime][O \left( m \Sigma \right)]-time algorithm for computing transition function ![transition-function][\delta]
for the string-matching automaton corresponding to a given pattern ![pattern][P]. (Hint: Prove that ![hint][\delta \left( q, a \right) = \delta \left( \pi \left\[ q \right\], a \right)]
if ![condition-1][q = m] or ![condition-2][P \left\[ q + 1 \right\] \neq a])

**Solution**:

First of all, we need to prove the hint. There are 3 cases to consider.

**Case 1:** ![q_lt_m][q < m], and ![all_a][\forall a \in \Sigma] but ![a_neq][a \neq P \left\[ q + 1 \right\]].

Since ![delta_definition][\delta \left\( q, a \right\) = \sigma \left\( P_q a \right\) = k], then ![pk_is_suffix_of_pqa][P_k \sqsupset P_q a].

We know ![implication][P_{\pi \left\[ q \right\]} \sqsupset P_q \Rightarrow P_{\pi \left\[ q \right\]} a \sqsupset P_q a], because
![P_pi_q][P_{\pi \left\[ q \right\]}] is the longest prefix of ![P][P] also the suffix of ![P_q][P_q],
then ![pk_is_suffix_ppia][P_k \sqsupset P_{\pi \left\[ q \right\]} a].

The next step is to prove ![P_k][P_k] is the longest prefix of ![P][P] also the suffix of ![p_piq_a][P_{\pi \left\[ q \right\]} a].
Assume ![l_gte_k][l >= k] and ![pl_suffix_ppia][P_l \sqsupset P_{\pi \left\[ q \right\]} a], then ![pl_is_suffix_pqa][P_l \sqsupset P_q a].
According to the definition of ![sigma][\sigma], ![k_gte_l][k >= l]. Therefore, ![l_eq_k][l = k],
![sigma_ppiqa_eq_k][\sigma \left( P_{\pi \left\[ q \right\]} a \right) = k], and ![hint][\delta \left( q, a \right) = \delta \left( \pi \left\[ q \right\], a \right)].

**Case 2**: ![q_lt_m][q < m] and ![a_eq_pq+1][a = P \left\[ q + 1 \right\]]. ![delta_pqa_eq_q+1][\delta \left( P_q, a \right) = q + 1]

**Case 3**: ![q_eq_m][q = m]. Case 3 is similar to Case 1.

Secondly, how can ![pi][\pi] be updated?

![ppiq_suffix_pq_implication][P_{\pi \left\[ q \right\]} \sqsupset P_q \Rightarrow P_{\pi \left\[ q \right\]} P \left\[ q + 1 \right\] \sqsupset P_q P \left\[ q + 1 \right\]].
Therefore, ![update_piq][\pi \left\[ q + 1 \right\] = \delta \left( \pi \left\[ q \right\], P \left\[ q + 1 \right\] \right)].

[O \left( m \Sigma \right)]: http://latex.codecogs.com/svg.latex?O&space;\left(&space;m&space;\Sigma&space;\right) "O \left( m \Sigma \right)"
[\delta]: http://latex.codecogs.com/svg.latex?\delta "http://latex.codecogs.com/svg.latex?\delta"
[\delta \left( q, a \right) = \delta \left( \pi \left\[ q \right\], a \right)]: http://latex.codecogs.com/svg.latex?\delta&space;\left(&space;q,&space;a&space;\right)&space;=&space;\delta&space;\left(&space;\pi&space;\left[&space;q&space;\right],&space;a&space;\right) "http://latex.codecogs.com/svg.latex?\delta \left( q, a \right) = \delta \left( \pi \left[ q \right], a \right)"
[q = m]: http://latex.codecogs.com/svg.latex?q&space;=&space;m "http://latex.codecogs.com/svg.latex?q = m"
[P \left\[ q + 1 \right\] \neq a]: http://latex.codecogs.com/svg.latex?P&space;\left&space;[&space;q&space;&plus;&space;1&space;\right&space;]&space;\neq&space;a "http://latex.codecogs.com/svg.latex?P \left[ q + 1 \right] \neq a"
[q < m]: http://latex.codecogs.com/svg.latex?q&space;<&space;m "http://latex.codecogs.com/svg.latex?q < m"
[\forall a \in \Sigma]: http://latex.codecogs.com/svg.latex?\forall&space;a&space;\in&space;\Sigma "http://latex.codecogs.com/svg.latex?\forall a \in \Sigma"
[a \neq P \left\[ q + 1 \right\]]: http://latex.codecogs.com/svg.latex?a&space;\neq&space;P&space;\left&space;[&space;q&space;&plus;&space;1&space;\right&space;] "http://latex.codecogs.com/svg.latex?a \neq P \left [ q + 1 \right ]"
[P]: http://latex.codecogs.com/svg.latex?P "http://latex.codecogs.com/svg.latex?P"
[\delta \left\( q, a \right\) = \sigma \left\( P_q a \right\) = k]: http://latex.codecogs.com/svg.latex?\delta&space;\left(&space;q,&space;a&space;\right)&space;=&space;\sigma&space;\left(&space;P_q&space;a&space;\right)&space;=&space;k "http://latex.codecogs.com/svg.latex?\delta \left( q, a \right) = \sigma \left( P_q a \right) = k"
[P_k \sqsupset P_q a]: http://latex.codecogs.com/svg.latex?P_k&space;\sqsupset&space;P_q&space;a "http://latex.codecogs.com/svg.latex?P_k \sqsupset P_q a"
[P_{\pi \left\[ q \right\]} \sqsupset P_q \Rightarrow P_{\pi \left\[ q \right\]} a \sqsupset P_q a]: http://latex.codecogs.com/svg.latex?P_{\pi&space;\left[&space;q&space;\right]}&space;\sqsupset&space;P_q&space;\Rightarrow&space;P_{\pi&space;\left[&space;q&space;\right]}&space;a&space;\sqsupset&space;P_q&space;a "http://latex.codecogs.com/svg.latex?P_{\pi \left[ q \right]} \sqsupset P_q \Rightarrow P_{\pi \left[ q \right]} a \sqsupset P_q a"
[P_{\pi \left\[ q \right\]}]: http://latex.codecogs.com/svg.latex?P_{\pi&space;\left[&space;q&space;\right]} "http://latex.codecogs.com/svg.latex?P_{\pi \left[ q \right]}"
[P_q]: http://latex.codecogs.com/svg.latex?P_q "http://latex.codecogs.com/svg.latex?P_q"
[P_k \sqsupset P_{\pi \left\[ q \right\]} a]: http://latex.codecogs.com/svg.latex?P_k&space;\sqsupset&space;P_{\pi&space;\left[&space;q&space;\right]}&space;a "http://latex.codecogs.com/svg.latex?P_k \sqsupset P_{\pi \left[ q \right]} a"
[P_k]: http://latex.codecogs.com/svg.latex?P_k "http://latex.codecogs.com/svg.latex?P_k"
[P_{\pi \left\[ q \right\]} a]: http://latex.codecogs.com/svg.latex?P_{\pi&space;\left\[&space;q&space;\right\]}&space;a "http://latex.codecogs.com/svg.latex?P_{\pi \left\[ q \right\]} a"
[l >= k]: http://latex.codecogs.com/svg.latex?l&space;>=&space;k "http://latex.codecogs.com/svg.latex?l >= k"
[P_l \sqsupset P_{\pi \left\[ q \right\]} a]: http://latex.codecogs.com/svg.latex?P_l&space;\sqsupset&space;P_{\pi&space;\left\[&space;q&space;\right\]}&space;a "http://latex.codecogs.com/svg.latex?P_l \sqsupset P_{\pi \left\[ q \right\]} a"
[P_l \sqsupset P_q a]: http://latex.codecogs.com/svg.latex?P_l&space;\sqsupset&space;P_q&space;a "http://latex.codecogs.com/svg.latex?P_l \sqsupset P_q a"
[\sigma]: http://latex.codecogs.com/svg.latex?\sigma "http://latex.codecogs.com/svg.latex?\sigma"
[k >= l]: http://latex.codecogs.com/svg.latex?k&space;>=&space;l "http://latex.codecogs.com/svg.latex?k >= l"
[l = k]: http://latex.codecogs.com/svg.latex?l&space;=&space;k "http://latex.codecogs.com/svg.latex?l = k"
[\sigma \left( P_{\pi \left\[ q \right\]} a \right) = k]: http://latex.codecogs.com/svg.latex?\sigma&space;\left(&space;P_{\pi&space;\left\[&space;q&space;\right\]}&space;a&space;\right)&space;=&space;k "http://latex.codecogs.com/svg.latex?\sigma \left( P_{\pi \left\[ q \right\]} a \right) = k"
[a = P \left\[ q + 1 \right\]]: http://latex.codecogs.com/svg.latex?a&space;=&space;P&space;\left\[&space;q&space;&plus;&space;1&space;\right\] "http://latex.codecogs.com/svg.latex?a = P \left\[ q + 1 \right\]"
[\delta \left( P_q, a \right) = q + 1]: http://latex.codecogs.com/svg.latex?\delta&space;\left(&space;P_q,&space;a&space;\right)&space;=&space;q&space;&plus;&space;1 "http://latex.codecogs.com/svg.latex?\delta \left( P_q, a \right) = q + 1"
[\pi]: http://latex.codecogs.com/svg.latex?\pi "http://latex.codecogs.com/svg.latex?\pi"
[P_{\pi \left\[ q \right\]} \sqsupset P_q \Rightarrow P_{\pi \left\[ q \right\]} P \left\[ q + 1 \right\] \sqsupset P_q P \left\[ q + 1 \right\]]: http://latex.codecogs.com/svg.latex?P_{\pi&space;\left\[&space;q&space;\right\]}&space;\sqsupset&space;P_q&space;\Rightarrow&space;P_{\pi&space;\left\[&space;q&space;\right\]}&space;P&space;\left\[&space;q&space;&plus;&space;1&space;\right\]&space;\sqsupset&space;P_q&space;P&space;\left\[&space;q&space;&plus;&space;1&space;\right\] "http://latex.codecogs.com/svg.latex?P_{\pi \left\[ q \right\]} \sqsupset P_q \Rightarrow P_{\pi \left\[ q \right\]} P \left\[ q + 1 \right\] \sqsupset P_q P \left\[ q + 1 \right\]"
[\pi \left\[ q + 1 \right\] = \delta \left( \pi \left\[ q \right\], P \left\[ q + 1 \right\] \right)]: http://latex.codecogs.com/svg.latex?\pi&space;\left\[&space;q&space;&plus;&space;1&space;\right\]&space;=&space;\delta&space;\left(&space;\pi&space;\left\[&space;q&space;\right\],&space;P&space;\left\[&space;q&space;&plus;&space;1&space;\right\]&space;\right) "http://latex.codecogs.com/svg.latex?\pi \left\[ q + 1 \right\] = \delta \left( \pi \left\[ q \right\], P \left\[ q + 1 \right\] \right)"

Here is an implementation in Rust (for folks who are curious about the use of `RefCell`, I wrote a small [article][A Use Case of RefCell] about it):

```Rust
use std::collections::HashMap;
use std::cell::RefCell;
use std::convert::TryFrom;

impl Solution {
    pub fn str_str(haystack: String, needle: String) -> i32 {
        let text = haystack.as_bytes();
        let pattern = needle.as_bytes();
        
        if pattern.len() == 0 {
            return 0;
        }
        
        if text.len() < pattern.len() {
            return -1;
        }
        
        let mut state = 0;
        let states = Self::get_transitions(pattern);
        
        for (index, ch) in text.iter().enumerate() {
            state = match states[state].borrow().get(ch) {
                Some(&s) => s,
                None => 0,
            };
            
            if state == pattern.len() {
                return i32::try_from(index - pattern.len() + 1).unwrap();
            }
        }
        
        -1
    }
    
    fn get_transitions(pattern: &[u8]) -> Vec<RefCell<HashMap<u8, usize>>> {
        let mut states = Vec::with_capacity(pattern.len() + 1);
        
        for _ in 0..=pattern.len() {
            states.push(RefCell::new(HashMap::new()));
        }
        
        let mut pi = 0;
        states[0].borrow_mut().insert(pattern[0], 1);
        
        for i in 1..=pattern.len() {
            for (&ch, &state) in states[pi].borrow().iter() {
                states[i].borrow_mut().insert(ch, state);
            }
            
            if i < pattern.len() {
                states[i].get_mut().insert(pattern[i], i + 1);
                pi = match states[pi].borrow().get(&pattern[i]) {
                    Some(&s) => s,
                    None => 0,
                };
            }
        }
        
        states
    }
}
```
[A Use Case of RefCell]: https://pjatgithub.github.io/posts/a-use-case-of-refcell/ "A Use Case of RefCell"
