# Sticky notes
## Option 1: Solve the First Version

The task is episodic, and in order to solve the environment,  your agent must get an average score of +30 over 100 consecutive episodes.

# 3/3 Friday
-[x] kick off training with bipedal parameters
-[] check if i am calculating the score correctly
-[]
-[]
-[]
-[]
-[]

* it seems unclear if SAC or TD3 will require less tuning or which one is better.  
    * 




## Run TD3 with reacher environment
* Either be able to update the environment with SB3 
* I get the same error regardless of the environment I run with.  That tells me it has to do with what the stable baselines3 buffer expects
* probably makes sense at least now to not use that buffer
* it is fine if I end up both implementing the buffer manually and implementing the changes that take it from ddpg to td3 in the udacity code.  that means i will just learn more
* the better thing is to act instead of waiting and deciding
-[] run in conda environment 
-[] get actions matching up
-[]


### Differences between DDPG and TD3

* Clipped Double-Q Learning
    * Learns two Q functions instead of one
    * uses the smaller of the two Q values to form targets in the bellman error loss functions
    * code: second q target 
* Delayed policy updates
    * every two q function updates
* target policy smoothing
    * adds noise to the target action to make it harder for the policy to exploit Q-function errors by smoothing out Q along changes in action



-[] Troubleshoot install of sb3 in 
-[]

## Experiment 5. DDPG with bipedal parameters and model from bipedal

## Experiment 2 . DDPG with bipedal parameters
Parameter differences
* Increased buffer size
* added weight decay
### Results
Episode 100	Average Score: 0.17
Episode 200	Average Score: 0.26
Episode 300	Average Score: 0.27
Episode 400	Average Score: 0.30
Episode 500	Average Score: 0.24
Episode 600	Average Score: 0.24
Episode 700	Average Score: 0.22
Episode 800	Average Score: 0.37
Episode 900	Average Score: 0.30
Episode 1000	Average Score: 0.28
### Discussion
* It looks like the results are very similar as before and nowhere near the score I am needing.  
* it is possible that I am not looking at the score correctly.  



# 3/2 Thursday 
-[x] kick off training
-[x] adapt code so training will run without error
-[] consider updating or at least checking torch version
## Experiment 1.  DDPG with pendulum hyperparameters
* Running with no hyperparameter tuning.  commit 9530ce3 .  
### Observations
Episode 100	Average Score: 0.18
Episode 200	Average Score: 0.29
Episode 300	Average Score: 0.30
Episode 400	Average Score: 0.32
Episode 500	Average Score: 0.38
Episode 600	Average Score: 0.33
Episode 700	Average Score: 0.21
Episode 800	Average Score: 0.24
Episode 900	Average Score: 0.27
Episode 1000	Average Score: 0.23

### Thoughts
* Doesn't seem to be learning.  Possibly no better than random chance.  

# 3/1
-[x] get git back to a clean state 
-[] copy code over
-[] figure out why it is states vs state for observations
-[] 
-[] 
-[] 

# 2/28
-[] run training
    -[] copy code over

# 2/27
* The reward after running ddpg pendulum isn't as high as I expected it would be.  
-[] troubleshoot reward with ddpg pendulum
    -[] find out if it actually low for what is expected
        -[] check what i can get with this environment looking at my last implementation, with cleanRL or something else

        -[x] check what the readme and other things say
            * doesn't say anything
    -[] change the gym version to what was originally used in this environment



# Rubric

Training Code

CRITERIA
MEETS SPECIFICATIONS
Training Code

The repository includes functional, well-documented, and organized code for training the agent.

Framework

The code is written in PyTorch and Python 3.

Saved Model Weights

The submission includes the saved model weights of the successful agent.

README

CRITERIA
MEETS SPECIFICATIONS
README.md

The GitHub submission includes a README.md file in the root of the repository.

Project Details

The README describes the the project environment details (i.e., the state and action spaces, and when the environment is considered solved).

Getting Started

The README has instructions for installing dependencies or downloading needed files.

Instructions

The README describes how to run the code in the repository, to train the agent. For additional resources on creating READMEs or using Markdown, see here and here.

Report

CRITERIA
MEETS SPECIFICATIONS
Report

The submission includes a file in the root of the GitHub repository (one of Report.md, Report.ipynb, or Report.pdf) that provides a description of the implementation.

Learning Algorithm

The report clearly describes the learning algorithm, along with the chosen hyperparameters. It also describes the model architectures for any neural networks.

Plot of Rewards

A plot of rewards per episode is included to illustrate that either:

[version 1] the agent receives an average reward (over 100 episodes) of at least +30, or
[version 2] the agent is able to receive an average reward (over 100 episodes, and over all 20 agents) of at least +30.
The submission reports the number of episodes needed to solve the environment.

Ideas for Future Work

The submission has concrete future ideas for improving the agent's performance.