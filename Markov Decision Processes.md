### Markovian Property
- Only the present state matters!
- Rules are stationary (transition model is stationary)
### Markov Decision Process Representation
$$
\begin{aligned} 
States &: S \\
Model &: T(s,a,s') \sim Pr(s'|s,a) \\
Actions &: A(s), A \\
Reward &: R(s), R(s,a), R(s,a,s') \\
Policy &: \pi(s) \rightarrow a \\
&: \pi^{*}
\end{aligned} 
$$
$R(s)$ : Reward for entering in a state
$R(s,a)$: Reward for entering a state and taking an action
$R(s,a,s')$: Reward for entering a state, taking an action, and ending up in a state

### Notes
It is possible to create a Markovian Process from information from previous states by changing the definition of the current state to hold information about these previous states 

These are equivalent because similar to how we can convert a Non-Markovian Process to a Markovian Process by including the history of the states in the current state. It is possible to fold in the action it took to get into a state.

The <span style="font-weight:bold; color:rgb(184, 31, 255)">policy</span> $(\pi(s))$ is the solution to the Markov Decision Process. The<span style="font-weight:bold; color:rgb(184, 31, 255)"> optimal policy </span>$(\pi^{*})$ is the policy that maximizes the long term reward.

### References
- [[Reinforcement Learning]]



