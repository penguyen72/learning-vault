A [[Policy]] is deterministic if there is only one action for a given state. This is commonly denoted by $\mu$ 
$$
a_t = \mu(s_t)
$$
#### Implementation
When building a deterministic policy for a continuous action space, you can setup a simple neural network that takes in the observation space in the input layer and the action space in the output layer.

The number of hidden layers, activation function, and optimizers are hyperparameters
#### Code
```python
network = nn.Sequential(
				nn.Linear(obs_dim, 64),
		        nn.Tanh(),
		        nn.Linear(64, 64),
		        nn.Tanh(),
		        nn.Linear(64, act_dim)
		  )
```