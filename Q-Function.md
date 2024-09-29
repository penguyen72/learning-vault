An equation derived from the [[Bellman Equation]] by incorporating actions. It evaluates the expected utility (reward) of taking a particular action in a given state **and then** acting optimally after that

$$
Q(s, a) = R(s,a) + \gamma \sum_{s'} P(s' | s, a)  \max_{a'} \left(Q(s',a') \right)
$$
#### Differences between Bellman and Q-Function
Bellman equation evaluates the value of a state, assuming optimal actions are taken after reaching the state

Q-Function focuses on the value of taking a specific action in a state

We can express the value of a state as the maximum value of taking any action from that state
$$
V(s) = \max_a Q(s,a)
$$
