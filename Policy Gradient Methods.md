A class of [[Reinforcement Learning]] algorithms that uses the directly optimizes parameters of a policy to maximize the expected cumulative reward. 

#### Policy Gradient Estimator
$$
\hat{g} = \hat{\mathbb{E}}\left[\nabla_{\theta} log \pi_{\theta}\right(a_t | s_t)\hat{A_t}]
$$
- $\theta$ is the set of parameters (such as weights and biases for a neural network) for a policy
- $\hat{g}$ is the estimate of the gradient of the objective function with respect to policy parameters $\theta$
- $\hat{\mathbb{E}}[\cdot]$ is the empirical average over a finite batch of samples  
- $\nabla_{\theta}$ is the gradient with respect to $\theta$
- $\pi_{\theta}(a_t | s_t)$ is the probability distribution over actions, which are parameterized by $\theta$
- $\hat{A_{t}}$ is the estimated advantage at time step $t$. Indicates how much better or worse an action was compared to the expected action
- $\pi_{\theta}$ is the stochastic policy
#### Objective Function 
$$
L^{PG}(\theta) = \hat{\mathbb{E}}\left[log \pi_{\theta}\right(a_t | s_t)\hat{A_t}]
$$
The goal of policy gradient methods is to **maximize** the objective function with gradient ascent. 
#### Derivation
The policy gradient is derived by taking the gradient with respect to $\theta$ of the objective function. This means that
$$
\hat{g} = \nabla_{\theta}L^{PG}(\theta)
$$

#### References 
- [[Value-based Methods]]