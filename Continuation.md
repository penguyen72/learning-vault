An equation derived from the [[Bellman Equation]] and [[Q-Function]]

$$
C(s, a) = \gamma \sum_{s'} P(s' | s, a)  \max_{a'} \left(R(s',a') + C(s',a') \right)
$$