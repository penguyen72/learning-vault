A [[Reinforcement Learning]] technique that iterates over policies to create a strictly improving policy in each iteration.

### Policy Iteration Algorithm
The algorithm interleaves policy evaluation and policy improvement to compute the optimal policy $\pi$

#### Note
- It is proven that each iteration will either create the same policy or a more optimal policy. This is why we do not have to worry about iterating to a less optimal policy