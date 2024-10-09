A [[Policy]] is stochastic if there is a probability of different actions that an agent can take in a state. This is commonly denoted as $\pi$ 
$$
a_t \sim \pi(\cdot | s_t)
$$
The two most common kinds of stochastic policies in [[Deep Reinforcement Learning]] 
- Categorical Policies (discrete action spaces)
- Diagonal Gaussian Policies (continuous action spaces)

Two key computations are centrally important for using and training stochastic polices
- sampling actions from the policy
- and computing log likelihoods of particular actions under a policy

#### Categorical Polices
A policy that is a classifier over a discrete actions. The neural network would be built in the same manner as a classifier where the input layer is the observation space and the output layer would be a vector that is the size of the action space.

The vector would give you [[logits]] for each action, so you would have to pass it through an activation function to convert it to a probability $P_{\theta}(s)$. 

**NOTE:** This is not log-likelihood. Additional steps would need to be taken
#### Diagonal Gaussian Policies
A policy that uses a [[Multivariate Gaussian Distribution]] to determine actions. 

There are two ways to implement this:
- Constructing a single vector of log standard deviations which is independent from the state. The $log \sigma$ are standalone parameters
- Construct a neural network that outputs log standard deviations and then exponentiate to get the standard deviation. This is because the standard deviation should be positive and it is easier to constrain after training the network.

