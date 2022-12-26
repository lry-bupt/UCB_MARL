# UCB_MARL

**Note:** All code and demonstrations are used for the submitted paper:

> Ruyu Luo, Wanli Ni, Hui Tian, Julian Cheng, and Kwang-Cheng Chen, "Joint Trajectory and Radio Resource Optimization by Multi-Agent Reinforcement Learning for Autonomous Mobile Robots in Industrial Internet of Things", submitted to IEEE TCom, Dec. 2022.

In this paper, we present the simulation codes of multi-agent reinforcement learning (MARL) with upper-confidence bound (UCB) exploration.



### Parameter Settings

Here are the setting of our simulations.

| Notation     | Simulation Value   | Physical Meaning                                             |
| ------------ | ------------------ | ------------------------------------------------------------ |
| $M_k$      | $3$                | the number of SNs in each group                              |
| $x _{\max} $ | $30 {\ \rm m}$     | the maximal x-axis size of  the moving area                  |
| $y _{\max} $ | $30 {\ \rm m}$     | the maximal y-axis size of  the moving area                  |
| $H_0$        | $1 {\ \rm m}$      | the antenna height of robots                                 |
| $H_m$        | $\{0, 1, 2\}$     | the antenna height of SNs                                    |
| $\sigma^2$   | $-100 \ {\rm dBm}$ | the power of the AWGN                                        |
| $P_{\max}$  | $23 \ {\rm dBm}$   | the maximum transmit power                                   |
| $\beta_{0}$  | $-30 \ {\rm dB}$   | the large-scale channel power gain at the reference distance  $d_0 = 1 \ {\rm m} $ |
| $\alpha$     | $2.2$              | the path loss exponent                                       |
| $G$          | $10 \ {\rm dB}$    | the Rician factor                                            |
| $\Delta_{s}$ | $1.5 \ {\rm m}$    | the grid size                                                |

### Representative visualization results
The visualization of the proposed MARL can be seen in [Visual_MARL](https://github.com/lry-bupt/Visual_MARL).
+ Here are four demonstrations for different stages in the MARL training process.
  + the beginning of training  <img src="https://github.com/lry-bupt/Visual_MARL/blob/main/visualization%20tool/result/demo2.gif" alt="show" height="200" width="200" /> 
  + 800 rounds of training &emsp; <img src="https://github.com/lry-bupt/Visual_MARL/blob/main/visualization%20tool/result/demo3.gif" alt="show" height="200" width="200" />
  + 1600 rounds of training &nbsp; <img src="https://github.com/lry-bupt/Visual_MARL/blob/main/visualization%20tool/result/demo4.gif" alt="show" height="200" width="200" /> 
  + the end of training &emsp;&emsp;&nbsp;<img src="https://github.com/lry-bupt/Visual_MARL/blob/main/visualization%20tool/result/demo1.gif" alt="show" height="200" width="200" />

### Source Codes

Here is a simple introduction to the code used in our paper.

- #### Figure_1_reward_comparison (Reward comparison between different algorithms)

  - Centralized_QL
    - [RL_brain.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_1_reward_comparison/Centralized_QL/RL_brain.py): &nbsp; Centralized tabular Q-learning agent with e-greedy exploration 
    - [main.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_1_reward_comparison/Centralized_QL/main.py): &nbsp;Main code of two robots that train with global information, connections between the environment and learning agents without experience exchange
  - UCB_MARL_environment1
    - [RL_brain.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_1_reward_comparison/UCB_MARL_environment1/RL_brain.py): &nbsp;One learning agent with upper-confidence bound (UCB) exploration
    - [main.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_1_reward_comparison/UCB_MARL_environment1/main.py): &nbsp;Main code of four robots, connections between the environment and learning agents, where two robots without interference at the strictly same environment exchange experience.

  - UCB_MARL_environment2

    - [RL_brain.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_1_reward_comparison/UCB_MARL_environment2/RL_brain.py): &nbsp;One learning agent with upper-confidence bound (UCB) exploration

    - [main.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_1_reward_comparison/UCB_MARL_environment2/main.py): &nbsp;Main code of four robots, connections between the environment and learning agents, where two nearby robots with interference at the same SN deployment exchange experience.



- #### Figure_2_convergence_comparison (Convergence comparison between different $H$)

  - UCB_MARL
    - [RL_brain.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_2_convergence_comparison/UCB_MARL/RL_brain.py): &nbsp;One learning agent with upper-confidence bound (UCB) exploration
    - [main.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_2_convergence_comparison/UCB_MARL/main.py): &nbsp;Main code of six robots, connections between the environment and learning agents

  - e-greedy_MARL

    - [RL_brain.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_2_convergence_comparison/e-greedy_MARL/RL_brain.py): &nbsp;Tabular Q-learning agent with e-greedy exploration

    - [main.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_2_convergence_comparison/e-greedy_MARL/main.py): &nbsp;&nbsp;Main code of two robots that train locally without experience exchange, connections between the environment and learning agents



- #### Figure_3_robot_trajectory (Robot trajectory under different $\kappa$)

  - [RL_brain.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_3_robot_trajectory/RL_brain.py): &nbsp;One learning agent with upper-confidence bound (UCB) exploration
  - [plot_figure.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_3_robot_trajectory/plot_figure.py): &nbsp; The trajectories with different reward policy

  - [robot trajectory.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_3_robot_trajectory/robot trajectory.py): &nbsp; Main code of four robots with experience exchange, connections between the environment and learning agents



- #### Figure_4_relation_between_R_T (Relation between average sum rate and arrival time)

  - [RL_brain.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_4_relation_between_R_T/RL_brain.py): &nbsp;One learning agent with upper-confidence bound (UCB) exploration

  - [main.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_4_relation_between_R_T/main.py): &nbsp; Main code of two robots with experience exchange, connections between the environment and learning agents



- #### Figure_5_R_versus_P (Convergence comparison between different $H$)

  - NOMA
    - [RL_brain.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_5_R_versus_P/NOMA/RL_brain.py): &nbsp;One learning agent with upper-confidence bound (UCB) exploration
    - [main.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_5_R_versus_P/NOMA/main.py): &nbsp; Main code of robots with experience exchange, connections between the environment and learning agents that communicate with non-orthogonal multiple access (NOMA)

  - OMA

    - [RL_brain.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_5_R_versus_P/OMA/RL_brain.py): &nbsp;One learning agent with upper-confidence bound (UCB) exploration

    - [main.py](https://github.com/lry-bupt/UCB_MARL/blob/main/Figure_5_R_versus_P/OMA/main.py): &nbsp;&nbsp; Main code of robots with experience exchange, connections between the environment and learning agents that communicate with orthogonal multiple access (OMA)

### References 

[1] R. Luo, W. Ni and H. Tian, "Visualizing Multi-Agent Reinforcement Learning for Robotic Communication in Industrial IoT Networks," admitted by IEEE INFOCOM Demo, Mar. 2022.

[2] R. Luo, H. Tian and W. Ni, “[Communication-Aware Path Design for Indoor Robots Exploiting Federated Deep Reinforcement Learning](https://ieeexplore.ieee.org/document/9569440),” in Proc. IEEE PIMRC, Helsinki, Finland, Sept. 2021, pp. 1197-1202.

[3] C. Jin et al., “[Is Q-learning Provably Efficient?](https://dl.acm.org/doi/abs/10.5555/3327345.3327395)” in Proc. NeurIPS, Montr´eal, Canada, Dec. 2018, pp. 4868-4878.

