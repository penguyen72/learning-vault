An on-policy [[Reinforcement Learning]] algorithm

#### Pseudocode
![[Screenshot 2024-10-03 at 7.18.30 PM.png]]

### Explanation
1. Initialize a policy and value network. 
	1. For a basic model, both networks can be setup with one input layer, one hidden layer, and one output layer
	2. The activation function that was used prior to the hidden layer and output layer was the Tanh activation function (action space ranges from -1 to 1)
	3. There are 64 nodes in the hidden layer
	4. The policy network acted as the actor and the value network acted as the critic
	5. For stochastic policies, it is best to use a [[Multivariate Gaussian Distribution]]. 
2. Iterate for a specific number of timesteps where one timestep is performing one action in our environment
3. Collected the set of trajectories also known as a batch. One batch contains multiple different episodes where the total number of timesteps in the entire batch make up the hyperparameter τ. 
	1. The batch contains state before the action was taken, the action, the reward, and the log probability of the action.
4. Computed the rewards to go for each episode in the batch
$$
\hat{R_t} = \sum_{t=0}^{T} \gamma^{t} r_{t}
$$
5. Computed the advantage to go for each episode in the batch
$$
A^{\pi}(s,a) = Q^{\pi}(s,a) - V^{\pi}(s)
$$
 6. Update the policy by maximizing the objective function with a specific $\epsilon$ value 
 7. Fit the value function with the mean squared error
#### Implementation Details
- The number of times the policy and value function updates is the ***epochs***
- A single vector of log standard deviation is not a function of state. It is a standalone parameter. This vector is converted to a covariance matrix that is used in Gaussian distribution
- The batch was stored in a one dimensional array. Since both the objective function and the mean squared error equation sums across all batches.

References:
- [PPO Background](https://spinningup.openai.com/en/latest/algorithms/ppo.html)
- [Stochastic Policies](https://spinningup.openai.com/en/latest/spinningup/rl_intro.html?highlight=stochastic#policies)