## Domain Randomization

### Physics
1. OpenAI, "Learning Dexterous In-Hand Manipulation", arXiv:1808.00177, 2018. [[Paper](https://arxiv.org/pdf/1808.00177.pdf)]

	|Parameter                       |Scaling factor range   |Additive term range|
	|--------------------------------|:---------------------:|:-----------------:|
	|object dimensions               |uniform([0.95, 1.05])  |                   |
	|object and robot link masses    |uniform([0.5, 1.5])    |                   |
	|surface friction coefficients   |uniform([0.7, 1.3])    |                   |
	|robot joint damping coefficients|loguniform([0.3, 3.0]) |                   |
	|actuator force gains (P term)   |loguniform([0.75, 1.5])|                   |
	|joint limits                    |                       |$N$(0, 0.15) rad   |
	|gravity vector (each coordinate)|                       |$N$(0, 0.4) $m/s^2$|

2. X. B. Peng, et al., "Sim-to-Real Transfer of Robotic Control with Dynamics Randomization", ICRA, 2018. [[Paper](https://xbpeng.github.io/projects/SimToReal/2018_SimToReal.pdf)] [[Blog](https://blog.openai.com/generalizing-from-simulation/)]

	|Parameter                 |Range                                    |
	|--------------------------|:---------------------------------------:|
	|Link Mass                 |[0.25, 4] x default mass of each link    |
	|Joint Damping             |[0.2, 20] x default damping of each joint|
	|Puck Mass                 |[0.1, 0.4]$kg$                           |
	|Puck Damping              |[0.01, 0.2]$Ns/m$                        |
	|Puck Friction             |[0.1, 5]                                 |
	|Table Height              |[0.73, 0.77]$m$                          |
	|Controller Gains          |[0.5, 2] x default gains                 |
	|Action Timestep $\lambda$ |[125, 1000]$s^{-1}$                      |

3. J. Tan, et al., "Sim-to-Real: Learning Agile Locomotion For Quadruped Robots", RSS, 2018. [[Paper](http://www.roboticsproceedings.org/rss14/p10.pdf)]

	|Parameter        |Lower bound  |Upper bound |
	|-----------------|:-----------:|:----------:|
	|mass             |80%          |120%        |
	|motor friction   |0$Nm$        |0.05$Nm$    |
	|inertia          |50%          |150%        |
	|motor strength   |80%          |120%        |
	|control step     |3$ms$        |20$ms$      |
	|latency          |0$ms$        |40$ms$      |
	|battery voltage  |14.0$V$      |16.8$V$     |
	|contact friction |0.5          |1.25        |
	|IMU bias         |-0.05 radian |0.05 radian |
	|IMU noise (std)  |0 radian     |0.05 radian |

4. L. Pinto, et al., "Robust Adversarial Reinforcement Learning", PMLR, 2018. [[Paper](http://proceedings.mlr.press/v70/pinto17a/pinto17a.pdf)]
    - Robustness check using trained policy by changing mass, friction.

5. A. Rajeswaran, et al., "EPOpt: Leaerning Robust Neural Network Policies Using Model Ensembels", ICLR, 2017. [[Paper](https://openreview.net/pdf?id=SyWvgP5el)]
    - Robustness check using trained policy by changing mass, friction.

	|**Hopper**       |$\mu$ |$\sigma$ |low |high |
	|-----------------|:----:|:-------:|:--:|:---:|
	|mass             |6.0   |1.5      |3.0 |9.0  |
	|ground friction  |2.0   |0.25     |1.5 |2.5  |
	|friction damping |2.5   |1.0      |1.0 |4.0  |
	|armature         |1.0   |0.25     |0.5 |1.5  |
	|**Half-Cheetah** |$\mu$ |$\sigma$ |**low** |**high** |
	|mass             |6.0   |1.5      |3.0 |9.0  |
	|ground friction  |0.5   |0.1      |0.3 |0.7  |
	|friction damping |1.5   |0.5      |0.5 |2.5  |
	|armature         |0.125 |0.04     |0.05|0.2  |

### Vision
