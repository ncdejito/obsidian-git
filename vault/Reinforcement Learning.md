[[Machine Learning]]
# Concern
Reinforcement learning aims to solve complex problems by training models to make decisions in dynamic environments to maximize rewards. 

Advantages of reinforcement learning include 
* solving intricate problems unsolvable by conventional methods, 
* correcting training errors
* handling non-deterministic environments, 
* flexibility in problem-solving, and 
* the ability to combine with other techniques like deep learning for enhanced performance

# Key components

Agent: The learner or decision-maker that interacts with the environment and takes actions to maximize the cumulative reward

Environment: The world that the agent interacts with, providing states, actions, and rewards

Policy: A mapping from states to actions that determines the agent's behavior. The policy is what the agent learns to optimize

Reward: A scalar feedback signal from the environment that the agent tries to maximize through its actions. The reward defines the goal of the RL problem

Value Function: Represents the long-term expected reward from a given state. The agent learns the value function to predict the future rewards and guide its decision-making

Environment Model: An optional component that models the environment's dynamics, allowing the agent to plan and simulate future outcomes

# How
These components work together as follows:
1. The agent observes the current state of the environment.
2. The agent selects an action based on its current policy.
3. The environment responds by transitioning to a new state and providing a reward.
4. The agent updates its policy, value function, and/or environment model to improve future decisions and maximize cumulative reward.

This cycle of interaction, feedback, and learning allows the agent to discover the optimal behavior through trial-and-error

# References

[Introduction by David Silver](https://youtube.com/playlist?list=PLqYmG7hTraZDM-OYHWgPebj2MfCFzFObQ&si=_v95K7g6UCToQ2eX)

Introduction to RL by Sutton and Barto - seminal work

Rl baselines
https://github.com/DLR-RM/stable-baselines3

used in Robotics

- [https://introduction-to-autonomous-robots.github.io/](https://introduction-to-autonomous-robots.github.io/)

Stef recommended Reinforcement Learning
https://huyenchip.com/2023/05/02/rlhf.html

Rewardbench
https://www.linkedin.com/posts/natolambert_excited-to-share-something-that-weve-needed-activity-7176257375597731842-EIW7?utm_source=share&utm_medium=member_android

central importance of Bellman's Equation for RL
- provides a recursive relationship between value of states or state action pairs and the expected rewards obtained from those states

Open problems in RL
https://www.linkedin.com/posts/jazib-ahmad-450_artificialintelligence-machinelearning-llms-activity-7106969647526150145-A1Kq?utm_source=share&utm_medium=member_android

Rl in robotics
https://arxiv.org/abs/2102.02915

Rl topics
https://www.theconstructsim.com/robotigniteacademy_learnros/ros-courses-library/reinforcement-learning-for-robotics/

Github/Pearl - production ready reinforcement learning
https://github.com/facebookresearch/Pearl

Qtable
[An Introduction to Q-Learning: A Tutorial For Beginners | DataCamp](https://www.datacamp.com/tutorial/introduction-q-learning-beginner-tutorial)

Simple deep q learning
https://github.com/rushter/MLAlgorithms/tree/master/mla%2Frl

Muzero paper - geohot said this is the road to l5 self driving autonomy

Classic model based reinforcement learning
https://www.linkedin.com/posts/activity-7147134285957799936-SKGt?utm_source=share&utm_medium=member_android

For cleaning robots it could be one square small reward, all squares many reward
- source quora

Path planning for cleaning robots paper

Example based learning translation