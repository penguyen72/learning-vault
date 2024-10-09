An on-policy [[Reinforcement Learning]] algorithm

#### Pseudocode
![[Screenshot 2024-10-03 at 7.18.30 PM.png]]

### Explanation
1. Initialize two neural networks with the parameters $\theta_{0}$ and $\phi_{0}$ for policy (actor) and value (critic) network, respectively
2. Iterate through $k$ where $k$ is the number of runs
3. Collect a set of trajectories. This would be your batch containing multiple episodes. Since the objective function is maximizing over all episodes and all timestamps in that episode. We can just store the trajectories in a 1d array ignoring episode boundaries