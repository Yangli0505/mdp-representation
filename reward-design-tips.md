# Reward Design

## Learning-based method

+ Inverse RL (expert demonstration) --> to learn reward function, then do RL
+ Behavior cloning --> to fit the expert policy
+ Human supervised--> https://arxiv.org/abs/1706.03741

## Hand-crafted method

**Main Reward**
+ Related to the `main events`, like `reaching the goals`. Usually positive values.
+ Make sure the main events are explored with enough samples. Sometimes, the probability of positive samples is very low through random exploration.

**Subgoals and Auxiliary Reward\Credit Assignment**

+ Auxiliary rewards are assigned when `reaching a subgoal`, which usually have smaller values than `main reward`
+ It is desirable to **assign reward after taking each action**
+ To define **directly-related state variable** in observation space for each auxiliary reward
+ Check the **relative values of all reward terms, and avoid too large or too small values** (very important)

**Shaping Reward**

+ To define a potential function for reward
+ The `desirable potential function` is proved to be the `value function`
+ For reaching goal problem, the potential function is `r= -a * dist_to_target`

## Other methods

+ GA --> Genetic Programming for Reward Function Search
+ Bayes --> Inverse Reward Design
+ Gradient Ascent --> Reward Design via Online Gradient Ascent


## Issues  

**Sparse Reward Problem**
+ Only `main events` are rewarded, i.e., only assign rewards for reaching the targets
+ There exist no efficient signals that can make agent learn before reaching the goals, i.e., lack of auxiliary reward
+ Solution
  + Exploitation of positive samples
  + Use GA to learn policy

<image src="images/sparse-reward.png" width="40%" height ="40%"/>

**Abnormal Agent Behavior**

+ Risky, this happens due to `lack of penalty on risk events`
+ Greedy, move forward and then go back, since it gets more cumulative rewards than reaching the goals. In this case, assigning a penalty to this greedy behavior is needed. It is better to **assign negative values, i.e., the penalty for the auxiliary rewards**.
+ Timid: this happens when `cumulative penalties` are more than the rewards of `main rewards`, which makes the agent stay still to avoid penalities, lost in suboptimal
