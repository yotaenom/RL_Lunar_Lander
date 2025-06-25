# LunarLander-v3: DQN vs DDQN

![Lunar Lander](https://upload.wikimedia.org/wikipedia/commons/2/2c/OpenAI_gym_logo.svg)

This project implements and compares Deep Q-Network (DQN), Double DQN (DDQN), and an enhanced DDQN_v2 agent to solve the LunarLander-v3 task using OpenAI Gym.

## Project Overview

In the LunarLander-v3 environment, the goal is to **land a rocket safely between two flags**. The agent learns to maximize cumulative reward via trial and error using Reinforcement Learning.

**Environment Details:**
- **State space**: 8-dimensional continuous features
- **Action space**: 4 discrete actions
- **Solved if**: Average reward > 200 over 100 consecutive episodes

---

## Algorithms Implemented

### 1. DQN (Deep Q-Network)
- Uses target network for stability
- Suffers from overestimation bias
- **Solved in**: 379 episodes
- **Avg reward**: ~129.6

### 2. DDQN (Double DQN)
- Separates action selection (policy_net) and evaluation (target_net)
- Reduces overoptimistic Q-value estimates
- **Solved in**: 684 episodes
- **Avg reward**: ~223.1
- More stable and robust than DQN

### 3. DDQN_v2
- Larger memory buffer
- Smaller batch size
- Higher learning rate
- Longer training duration
- **Avg reward**: >250
- **Success rate**: 18/20 runs

---

## Key Components

- **Replay Buffer**: For experience replay
- **Epsilon Decay**: Exploration vs exploitation trade-off
- **Target Network**: Updated periodically using soft update (τ)
- **Hyperparameters**: Tuned per model for optimal performance

---

## Results Summary

| Metric | DQN | DDQN | DDQN_v2 |
|--------|-----|------|----------|
| Episodes to solve | 379 | 684 | ~800 |
| Avg reward | 129.6 | 223.1 | >250 |
| Stability | Spikey | Smooth | Very stable |
| Failures | 4 hard crashes | 1 soft fail | None |
| Training time | ~2.75 min | ~3.8 min | ~5 min |

---

## Files

- `DQN_LunarLander_Training.ipynb` – Standard DQN agent
- `DDQN_LunarLander_Training.ipynb` – Double DQN implementation
- `DDQN_LunarLander_Training_v2.ipynb` – Improved DDQN with tuned hyperparameters
- `Reinforcement Learning Group Project.pdf` – Final project presentation

---

## Insights

- DQN trains faster but suffers from instability and overestimation
- DDQN stabilizes learning by reducing bias
- DDQN_v2 improves reward and success rate with better tuning

---

## Contributors

- Noureldin Sewilam  
- Yotaro Enomoto  
- Samir Barakat