A fundamental concept in dynamic programming and [[Reinforcement Learning]] used to express the relationship between current state and future rewards.
$$
V(s) = \max_a \left[ R(s, a) + \gamma \sum_{s'} P(s' | s, a) V(s') \right]
$$
Where:
- $V(s)$ is the value of state $s$
- $R(s,a)$ is the reward for taking action aaa in state $s$
- $\gamma$ is the discount factor
- $P(s′'|s,a)$ is the transition probability from state $s$ to state $s'$ under action $a$,
- $V(s′)$ is the value of the next state $s'$

### Discount factor $\gamma$
Indicates that future rewards are significant, but are less significant than future rewards
##### When $\gamma = 0$  
Future rewards are not important at all. The model only cares about immediate rewards
##### When $\gamma = 1$  
Future rewards are as important as immediate rewards


### Relations between Bellman Equations
|          | $V(s)$                                   | $Q(s,a)$                                        | $C(s,a)$                   |
| -------- | ---------------------------------------- | ----------------------------------------------- | -------------------------- |
| $V(s)$   | $V(s)$                                   | $\max_a Q(s,a)$                                 | $\max_a (R(s,a) + C(s,a))$ |
| $Q(s,a)$ | $R(s,a)+\gamma \sum_{s'} T(s,a,s')V(s')$ | $Q(s,a)$                                        | $R(s,a) + C(s,a)$          |
| $C(s,a)$ | $\gamma \sum_{s'} T(s,a,s')V(s')$        | $\gamma \sum_{s'} T(s,a,s') \max_{a'} Q(s',a')$ | $C(s,a)$                   |
