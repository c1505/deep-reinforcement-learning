# Sticky notes
## Option 1: Solve the First Version

The task is episodic, and in order to solve the environment,  your agent must get an average score of +30 over 100 consecutive episodes.


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