[//]: # (Image References)

[image1]: average_over_100.png "Average reward over last 100 episodes"

[image2]: reward_per_episode.png "Reward Per episode"


# Learning Algorithm
Twin Delayed Deep Deterministic Policy Gradients (TD3)
TD3 is an off-policy actor-critic algorithm used for environments with continuous action spaces. It is an extension of the Deep Deterministic Policy Gradients (DDPG) algorithm and is described in the paper Fujimoto et al., 2018. TD3 uses three key tricks to improve performance: clipped double Q-learning, delayed policy update, and target policy smoothing.

* Clipped double Q-learning: Two Q-functions are learned instead of one, and the minimum Q-value is used as the target for the Bellman error loss functions. This reduces overestimation bias and improves stability.

* Delayed policy update: TD3 updates the policy less frequently than the Q-functions to reduce overfitting to the current Q-values. The paper recommends one policy update every two Q-function updates.

* Target policy smoothing: TD3 adds noise to the target action, which makes it harder for the policy to exploit Q-function errors by smoothing out Q along changes in action. This improves exploration and reduces the impact of overfitting to the current Q-values.

The neural network architectures used in TD3 are fully connected.  There is one actor, two Q-networks (critics), and one target network. Pytorch is used for the implementation and each neural network has 3 layers.  The target network is slowly updated for stability. The following hyperparameters were used in the implementation:


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

# Plot of Rewards
![Average reward over last 100 episodes][image1]
![Reward per Episode][image2]

The environment is considered solved when the average rewards for the previous 100 episodes is greater than 30.  This environment is solved by episode 200.

# Future Directions

Some ideas for future work include:

* Hyperparameter tuning to improve performance further
* Trying the multi-agent environment
* Updating with a modern version of ML-Agents
* Trying different algorithms such as Soft Actor Critic (SAC) or Truncated Quantile Critics (TQC) which have shown similar or better performance than TD3 for continuous action tasks.