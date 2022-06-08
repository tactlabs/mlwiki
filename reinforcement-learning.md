/ [Home](index.md)

# Reinforcement Learning

Reinforcement learning is an area of Machine Learning. It is about taking suitable action to maximize reward in a particular situation. It is employed by various software and machines to find the best possible behavior or path it should take in a specific situation. Reinforcement learning differs from supervised learning in a way that in supervised learning the training data has the answer key with it so the model is trained with the correct answer itself whereas in reinforcement learning, there is no answer but the reinforcement agent decides what to do to perform the given task. In the absence of a training dataset, it is bound to learn from its experience. 

Terms used in Reinforcement Learning
* Agent(): An entity that can perceive/explore the environment and act upon it.
* Environment(): A situation in which an agent is present or surrounded by. In RL, we assume the stochastic environment, which means it is random in nature.
* Action(): Actions are the moves taken by an agent within the environment.
* State(): State is a situation returned by the environment after each action taken by the agent.
* Reward(): A feedback returned to the agent from the environment to evaluate the action of the agent.
* Policy(): Policy is a strategy applied by the agent for the next action based on the current state.
* Value(): It is expected long-term retuned with the discount factor and opposite to the short-term reward.
* Q-value(): It is mostly similar to the value, but it takes one additional parameter as a current action (a).