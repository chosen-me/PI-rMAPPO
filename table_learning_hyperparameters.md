# Learning Hyperparameters

This file reproduces the **Learning Hyperparameters** table that was moved out of
the manuscript (PI-rMAPPO / IEEE-TVT submission).

| Setting | DQN | DDPG | MAPPO family |
|---|---|---|---|
| Actor learning rate | — | 1e-4 | 7.5e-5 |
| Q-network learning rate | 1e-3 | — | — |
| Critic learning rate | — | 1e-3 | 2.5e-4 |
| Discount $\gamma$ | 0.99 | 0.99 | 0.99 |
| Batch size | 64 | 64 | 128 |
| Target update | every 100 | $\tau = 0.005$ | — |
| Exploration | $\epsilon: 1 \to 0.05$ | $\sigma: 0.30 \to 0.05$ | $\log \sigma_0 = -1.5$ |
| GAE $\lambda$ | — | — | 0.95 |
| PPO epochs | — | — | 8 |
| PPO clip ratio | — | — | 0.20 |
| Entropy coefficient | — | — | 0.004 |
| Value coefficient | — | — | 0.50 |
| Reward scale | 1 | 1 | 0.10 |

**Note.** The MAPPO family includes MAPPO, MAPPO-Lagrangian, Prior-MAPPO, and
PI-rMAPPO. Residual variants additionally use residual scale 0.25 and the
acceleration-channel mask. The MAPPO family uses a rollout batch of 128 because
on-policy PPO updates consume a full rollout buffer, whereas DQN and DDPG draw
minibatches of 64 from a replay buffer; this is the standard batch convention for
each algorithm and does not give any method additional information.

**Additional implementation details (from the manuscript).**
DQN and DDPG use shared local networks and follower-wise replay buffers. The MAPPO
family shares actor size and the PPO and GAE settings, and the MAPPO-Lagrangian
model additionally integrates its cost critic and Lagrange multiplier.
