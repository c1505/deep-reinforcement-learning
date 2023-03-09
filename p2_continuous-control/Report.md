# Learning Algorithm

* Twin Delayed Deep Deterministic Policy Gradients
    * Paper https://arxiv.org/abs/1802.09477 
    * Successor to Deep Deterministic Policy Gradients
    * Implementation in the paper adapted to use with unity agent environments
    * Off Policy
    * For continuous actions
    * Adds three major tricks
        * clipped double Q-Learning
            * Two Q functions are learned instead of one.  The smaller of the Q-values is used as the target for the Bellman error loss functions.
        * delayed policy update
            * Paper recommends one policy update every two Q-function updates.  It is what is implemented in the code here as well and can be modified by changing the parameter policy_freq . 
        * target policy smoothing
            * Adds noise to the target action.  It makes it harder for the policy to exploit Q-function errors by smoothing out Q along changes in action 

## Hyperparameters

```python
seed = 0                # Sets PyTorch and Numpy seeds
start_timesteps = 25e3  # Time steps initial random policy is used
max_timesteps = 329_329 # Total time steps to run
expl_noise = 0.1        # Gaussian exploration noise
batch_size = 256        # Batch size for both actor and critic
discount = 0.99         # Discount factor
tau = 0.005             # Target network update rate
policy_noise = 0.2      # Noise added to target policy during critic update
noise_clip = 0.5        # Range to clip target policy noise
policy_freq = 2         # Frequency of delayed policy updates
save_model = True       # Save model and optimizer parameters
```
## Neural Network Model Architecture
* Multilayer Perceptron 
* Actor
    * 1 hidden layer
    
* One actor
* Two crtics

https://github.com/sfujim/TD3

# Future Directions
* hyperparemeter tuning
* try the many agents environment
* update with a modern version of ml-agents
* Try different algorithms
    * Soft Actor Critic(SAC) .  Shows similar performance in many continuous action tasks as TD3
    * Truncated Quantile Critics(TQC) . Typically shows better performance than TD3 for continuous actions.  It is more complex than TD3.



# Report Requirements

## Learning Algorithm

The report clearly describes the learning algorithm, along with the chosen hyperparameters. It also describes the model architectures for any neural networks.

## Plot of Rewards

A plot of rewards per episode is included to illustrate that either:

[version 1] the agent receives an average reward (over 100 episodes) of at least +30, or
[version 2] the agent is able to receive an average reward (over 100 episodes, and over all 20 agents) of at least +30.
The submission reports the number of episodes needed to solve the environment.

## Ideas for Future Work

The submission has concrete future ideas for improving the agent's performance.
# requirements end