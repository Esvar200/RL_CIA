# Reinforcement Learning Algorithms Repository

This repository contains implementations of different Reinforcement Learning (RL) algorithms applied to grid-based environments and a Bandit problem. The goal is to showcase various RL techniques such as Value Iteration (Dynamic Programming), Q-Learning, SARSA, and a K-armed Bandit solution. The code is organized into two Jupyter notebooks: `RL_CIA_1.ipynb` for the Bandit problem and `RL_CIA_2.ipynb` for the grid-based problem.

## Table of Contents

1. [Overview](#overview)
2. [RL_CIA_1.ipynb - K-Armed Bandit](#rl_cia_1ipynb---k-armed-bandit)
3. [RL_CIA_2.ipynb - Grid-based Problem](#rl_cia_2ipynb---grid-based-problem)
4. [Benchmarking and Results](#benchmarking-and-results)
5. [Analysis and Comparison](#analysis-and-comparison)

## Overview

This repository includes two primary RL algorithms:

- **K-Armed Bandit Problem** (RL_CIA_1.ipynb): A simple exploration-exploitation scenario where the agent must maximize its reward by selecting one of several slot machines (arms) with different reward distributions.
- **Grid-Based RL Problem** (RL_CIA_2.ipynb): An environment where an agent navigates a grid with obstacles to reach a goal, comparing different algorithms like Value Iteration (Dynamic Programming), Q-Learning, and SARSA.

# RL_CIA Project

This repository contains implementations for two reinforcement learning (RL) problems:

1. **K-Armed Bandit Problem**
2. **Grid-based Problem (with obstacles)**

## RL_CIA_1.ipynb - K-Armed Bandit

This notebook implements the K-Armed Bandit Problem using an off-policy Q-Learning algorithm and an on-policy SARSA algorithm, along with exploration-exploitation strategies (ε-greedy). The agent interacts with multiple arms (machines) to learn which arm provides the maximum reward.

### Key Features:
- Exploration vs Exploitation via ε-greedy.
- Q-Learning (off-policy RL).
- SARSA (on-policy RL).

## RL_CIA_2.ipynb - Grid-based Problem

This notebook focuses on Value Iteration, Q-Learning, and SARSA applied to a GRID_SIZE x GRID_SIZE grid. The agent navigates the grid to reach the goal while avoiding obstacles. Rewards are given for reaching the goal, penalizing obstacles, and slight penalties for each movement.

### Key Features:
- Grid environment with random obstacles and defined start and goal states.
- Reward Function: Rewards for reaching the goal, penalizes obstacles, and penalizes movement.
- Value Iteration (DP): Computes values by iterating over states and actions to converge on optimal state values.
- Q-Learning: Model-free off-policy RL algorithm that updates Q-values by selecting the maximum action value.
- SARSA: On-policy method that updates Q-values based on the policy being followed.

### Benchmarking and Results

#### Time Performance:
- Value Iteration (DP): Faster for small grids, as it’s a systematic approach.
- Q-Learning & SARSA: Can take longer but are more adaptable to different environments, especially scalable to complex problems.

#### Grid Size Comparison:
- For the 25x25 Grid:
  - Value Iteration converged relatively quickly as the grid size is smaller.
  - Q-Learning and SARSA took a little longer due to exploration and convergence to the optimal policy.
- For the 100x100 Grid:
  - Value Iteration took significantly longer, given the increased number of states to evaluate.
  - Q-Learning and SARSA showed more adaptability and scalability, but convergence time was noticeably higher compared to the 25x25 grid due to the larger state space and exploration requirements.

#### Policy Comparison:
- Each algorithm eventually produces a policy that guides the agent from the start state to the goal state. However, the policies from Q-Learning and SARSA can vary based on the exploration settings (ε-greedy).
- Value Iteration produced the optimal policy but was limited in scalability to larger grids.

#### Scalability:
- Value Iteration is best suited for small grids (e.g., 25x25).
- Q-Learning and SARSA are better suited for larger grids (e.g., 100x100) and continuous spaces, especially when enhanced with function approximators like neural networks.

### Analysis and Comparison

This section presents a detailed comparison between the three algorithms:

- **Value Iteration**: Best for small, well-defined environments. It converges quickly for smaller grids like 25x25 but becomes computationally expensive for larger grids like 100x100.
- **Q-Learning**: More flexible, able to adapt to environments with more complexity or continuous states. Q-Learning showed better scalability to larger grids.
- **SARSA**: Offers similar results to Q-Learning but with slightly different behavior due to its on-policy nature. Like Q-Learning, it is more scalable for larger grids, but it was more sensitive to exploration parameters (ε-greedy).

