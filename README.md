# UCB_MARL

**Note:** All code and demonstrations are used for our paper:
> Ruyu Luo, Wanli Ni, and Hui Tian, "Multi-Agent Reinforcement Learning for Industrial Data Collection with Mobile Robots" .

In this paper, we present the simulation codes of multi-agent reinforcement learning (MARL) with upper-confidence bound (UCB) exploration.

### Parameter Settings
| Notation     | Simulation Value   | Physical Meaning                                             |
| ------------ | ------------------ | ------------------------------------------------------------ |
| $ M_k $      | $3$                | the number of SNs in each group                              |
| $x _{\max} $ | $30 {\ \rm m}$     | the maximal x-axis size of  the moving area                  |
| $y _{\max} $ | $30 {\ \rm m}$     | the maximal y-axis size of  the moving area                  |
| $H_0$        | $1 {\ \rm m}$      | the antenna height of robots                                 |
| $H_m$        | $ \{0, 1, 2\}$     | the antenna height of SNs                                    |
| $\sigma^2$   | $-100 \ {\rm dBm}$ | the power of the AWGN                                        |
| ${P_{\max}$  | $23 \ {\rm dBm}$   | the maximum transmit power                                   |
| $\beta_{0}$  | $-30 \ {\rm dB}$   | the large-scale channel power gain at the reference distance  $d_0 = 1 \ {\rm m} $ |
| $\alpha$     | $2.2$              | the path loss exponent                                       |
| $G$          | $10 \ {\rm dB}$    | the Rician factor                                            |
| $\Delta_{s}$ | $1.5 \ {\rm m}$    | the grid size                                                |
