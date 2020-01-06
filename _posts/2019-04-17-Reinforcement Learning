## TD learning 

Temporal difference (TD) learning refers to a class of model-free reinforcement learning methods which learn by bootstrapping from the current estimate of the value function. TD methods adjust predictions to match later, more accurate, predictions about the future before the final outcome is known.

## Monte Carlo
Monte Carlo methods only adjust their estimates once the final outcome is known

## TD Lambda
The lambda parameter refers to the trace decay parameter, with 0<=lambda<=1. Higher settings lead to longer lasting traces; that is, a larger proportion of credit from a reward can be given to more distant states and actions when lambda is higher, with lambda =1 producing parallel learning to Monte Carlo RL algorithms.

- TD is sampling from environment like Monte Carlo and is bootstrapping like DP
Wait only n step for estimate
- TD and DP are bootstrapping because it uses next step's state for estimate. The next step's state represent the future rewards (bootstrapping). While MC is not bootstrapping. it's getting estimate from an episode's real rewards.
- TD has advantage over DP because it does not require a model of environment, the transition function
- TD has advantage over Monte Carlo because they are implemented in an online, fully incremental fashion. MC must wait until the end of an episode. Can be a significant advantage if episodes are long. (**TD converges faster**)


- Both TD are Monte Carlo are sampling update, unlike DP. It doesn't know the distribution of the transition
- TD with eligibility trace to obtain general method to learn more efficiently
- TD(1) is Monte Carlo, TD(0) is one-step TD. In between are intermediate methods

## Learning rate properties to TD learning
1. sum(alpha_T) = infinity (sum of alpha_T over time T)
2. sum(alpha_T^2) < infinity (sum of alpha_T over time T)

[Details](https://classroom.udacity.com/courses/ud600/lessons/4178018883/concepts/41512300930923)
