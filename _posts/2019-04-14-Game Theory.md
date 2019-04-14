---
layout: post
title: Game Theory
tags: Nash Equilibrium, Correlated Equilibrium, Markov Games
---

## Nash Equilibrium vs. Correlated Equilibrium
Nash equilibrim always exists in Markov game. But it need not to be the optimal equilibrium.

There are two types of Nash equilibrium - pure strategy and mixed strategy NE. In pure strategy NE, each player plays a strategy from which she has no incentive to deviate. In a mixed strategy NE, instead of a fixed strategy, the players assign a probability to play each strategy in equilibrium. A mixed NE always exist, but pure strategy NE may or may not exist. Also, a set of NE need not be a singleton. 

Nash Equilibrium is a vector of independent probability distributions over actions, in which all agents optimize with respect to one another's probabilities.

A Correlated Equilibrium allows for the possibility of dependencies in the agents' randomizations: a CE is a probability distribution over the join space of actions, in which all agents optimize with respect to one another's probabilities, conditioned on their own. (Greenwald 2003)


In a mixed Nash equilibrium, the player's actions are independent random variables. Knowing that a player 1's strategy (action distribution), would NOT give any information to player 2.

In correlated equilibria the actions need not be independent. The idea is that each player choose their action according to the observation of the value of the same public signal. A strategy assigns an action to every possible obseration a player can make. If no player would want to deviate from the recommended strategy, the distribution is called a correlated equilibrium.

Correlated equailibrium is a general form of Nash equalibrium.

Correlated that's not Nash Equilibrium can achieve higher rewards than NE by avoiding positive probability mass on less desirable outcomes, unlike mixed strategy NE. (Greenwald 2003)


## Markov Games
Stochastic games generalize repeated games and Markov decision processes (MDP).

A stochastic game is a tuple <I, S (Ai(s)), P, Ri>. I is a set of n players. S is a set of states, Ai(s) is the ith player's set of actions at state s. P is a probability transition function that describes state transition, conditioned on **past states** and **joint actions**.

An MDP is a one-player Markov game. According to bellman's equation Q* is the normalized sum of the immediate reward obtained at state as for taking action a. The V* of a state is the max Q*(s,a)

In Markov games, player i's Q values are defined over states and action vectors rather than state-action pairs (Greenwald 2003). However, in Markov game, there need not be policy profile which maximize all players' respective rewards simultaneously. So objective to maximize respective reward may not be resulting in a viable policy in a game environment. 

### different value functions can be used to solve Markov game

- Littman's minmax 
- Hu and Wellman's value function according to Nash equilibrium. This generizes the minimax strategies in zero-sum games. This value function need not be well-defined as NE need not be singleton. (Greenwald 2003)

- 4 Correlated Equilibrium value functions (Greenwald 2003). This is also not well-defined. 
