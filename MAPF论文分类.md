MAPF研究方向

### **1. 动态环境下的Lifelong MAPF与实时性优化**

- **核心问题**：在持续接收新任务（如仓储系统）或环境动态变化时，如何实时更新路径规划，避免全局重规划带来的计算开销。
- **创新方向**：
  - **滚动时域冲突消解（Rolling-Horizon Collision Resolution）**：分时间窗口处理冲突，仅优化当前窗口内的路径，平衡实时性与全局最优性。
  - **增量式规划与任务队列管理**：结合任务优先级动态调整路径，支持大规模（>1000智能体）场景下的高效调度6。
- **参考论文**：
  - *"Lifelong Multi-Agent Path Finding in Large-Scale Warehouses"* (AAAI 2022) 

#### Lifelong/Continuous MAPF 在动态与高密度场景下的扩展**

*研究内容：*
– 针对持续性任务下的MAPF（即不断为每个智能体分配新目标），探讨如何在有限规划时间内处理大量智能体或极高密度场景；
– 研究缓解局部拥堵、短视行为以及执行不确定性等问题的方法。
*参考论文：*

[arxiv.org](https://arxiv.org/abs/2404.16162)

 “Scaling Lifelong Multi-Agent Path Finding to More Realistic Settings: Research Challenges and Opportunities” (arXiv, 2024)



**2. 基于优先级搜索的MAPF算法及其理论分析**
*研究内容：*
– 探索不依赖于固定全序优先级，而是在部分优先级空间中系统性地搜索冲突解决方案，提升规划效率和解质量；
– 分析此类方法在完整性和最优性方面的理论界限，为优先规划方法提供更深的理论支持。
*参考论文：*

[arxiv.org](https://arxiv.org/abs/1812.06356)

 “Searching with Consistent Prioritization for Multi-Agent Path Finding” (arXiv, 2018)



3.基于SAT的MAPF问题

**Sub-Optimal SAT-Based Approach to Multi-Agent Path-Finding Problem**

多智能体寻路问题（MAPF）是指在一个无向图中，给定一组智能体，每个智能体都有自己的起点和终点。任务是为每个智能体找到一条路径，使得它们在移动过程中不发生碰撞，并且尽量减少一个给定的目标函数。目标函数通常有两种：路径总和和最大时间。路径总和是指所有智能体到达终点所需的时间步数之和，最大时间是指最后一个到达终点的智能体所需的时间步数。这两种目标函数反映了不同的应用场景，比如节省能源或者提高效率。寻找最优解的算法通常分为两类：基于搜索的算法和基于编译的算法。基于搜索的算法是针对路径总和目标而开发和测试的，而基于编译的算法是利用布尔可满足性（SAT）等已知问题来解决最大时间目标。这篇文章旨在弥合这两种目标函数之间的差距，提出了一个新的基于SAT的MAPF求解器，可以直接优化路径总和目标函数。作者还借鉴了一些基于搜索算法中有效的技术，如多值决策图（MDD）和独立检测（ID），并且设计了一个有界次优的基于SAT的求解器。作者通过实验比较了他们提出的方法与其他最优或次优算法在不同领域上的表现，并证明了他们提出的方法在许多情况下具有优势。



### **4. 结合机器学习与启发式搜索的混合算法**

- **核心问题**：传统算法（如CBS）在大规模场景下效率受限，如何通过机器学习优化搜索策略。
- **创新方向**：
  - **机器学习引导的大邻域搜索（ML-Guided LNS）**：利用强化学习动态调整邻域选择策略，快速修复低质量解7。
  - **启发式函数的在线学习**：在搜索过程中实时更新启发式权重，提升路径质量与求解速度6。
- **参考论文**：
  - *"Anytime Multi-Agent Path Finding via Machine Learning-Guided Large Neighborhood Search"* (AAAI 2022) 7
  - *"EECBS: A Bounded-Suboptimal Search for Multi-Agent Path Finding"* (AAAI 2022)

# 经典MAPF (one-shot MAPF)

## 1. 精确算法和有界次优算法

### 1.1 CBS及其变种

CBS及其变种ECBS（有界次优）, ICBS, CBSH等。适用于少量agent。

找一下随即重启的文章。/////////////

论文：

Barer, Max, et al. "Suboptimal variants of the conflict-based search algorithm for the multi-agent pathfinding problem." *Proceedings of the international symposium on combinatorial Search*. Vol. 5. No. 1. 2014.

Boyarski, Eli, et al. "Icbs: The improved conflict-based search algorithm for multi-agent pathfinding." *Proceedings of the International Symposium on Combinatorial Search*. Vol. 6. No. 1. 2015.

代码：https://github.com/Jiaoyang-Li/CBSH2-RTC

### 1.2 非CBS算法

Branch-and-cut-and-price, operator decomposition + independence detection, increasing cost tree search, Safe Interval Path Planning

Lam, Edward, et al. "Branch-and-cut-and-price for multi-agent path finding." *Computers & Operations Research* 144 (2022): 105809.

Standley, Trevor. "Finding optimal solutions to cooperative pathfinding problems." *Proceedings of the AAAI conference on artificial intelligence*. Vol. 24. No. 1. 2010.

Sharon, Guni, et al. "The increasing cost tree search for optimal multi-agent pathfinding." *Artificial intelligence* 195 (2013): 470-495.

Phillips, Mike, and Maxim Likhachev. "Sipp: Safe interval path planning for dynamic environments." *2011 IEEE international conference on robotics and automation*. IEEE, 2011.

## 2. 无界次优算法

### 2.1 基于优先级（规则）的算法

PP, PBS, push & swap, PIBT等。属于无界次优算法。适用于快速求解大量agent。

论文：

Ma, Hang, et al. "Searching with consistent prioritization for multi-agent path finding." *Proceedings of the AAAI conference on artificial intelligence*. Vol. 33. No. 01. 2019.

Van Den Berg, Jur P., and Mark H. Overmars. "Prioritized motion planning for multiple robots." *2005 IEEE/RSJ International Conference on Intelligent Robots and Systems*. IEEE, 2005.

Luna, Ryan, and Kostas E. Bekris. "Push and swap: Fast cooperative path-finding with completeness guarantees." *IJCAI*. Vol. 11. 2011.

Okumura, Keisuke, et al. "Priority inheritance with backtracking for iterative multi-agent path finding." *Artificial Intelligence* 310 (2022): 103752.

Chen, Zhe, et al. "Traffic flow optimisation for lifelong multi-agent path finding." *Proceedings of the AAAI Conference on Artificial Intelligence*. Vol. 38. No. 18. 2024.

有前途///////////////////

代码：

### 2.2 大邻域搜索

MAPF-LNS, MAPF-LNS2. 适用于anytime场景。

论文：

Li, Jiaoyang, et al. "Anytime multi-agent path finding via large neighborhood search." *International Joint Conference on Artificial Intelligence 2021*. Association for the Advancement of Artificial Intelligence (AAAI), 2021.

Chan, Shao-Hung, et al. "Anytime Multi-Agent Path Finding using Operation Parallelism in Large Neighborhood Search." *arXiv preprint arXiv:2402.01961* (2024).

有前途////////////////

代码：

## 3. 融合机器学习

论文：

Huang, Taoan, et al. "Anytime multi-agent path finding via machine learning-guided large neighborhood search." *Proceedings of the AAAI Conference on Artificial Intelligence*. Vol. 36. No. 9. 2022.

Huang, Taoan, Bistra Dilkina, and Sven Koenig. "Learning node-selection strategies in bounded suboptimal conflict-based search for multi-agent path finding." *International joint conference on autonomous agents and multiagent systems (AAMAS)*. 2021.

Zhang, Shuyang, et al. "Learning a priority ordering for prioritized planning in multi-agent path finding." *Proceedings of the International Symposium on Combinatorial Search*. Vol. 15. No. 1. 2022.

Phan, Thomy, et al. "Adaptive anytime multi-agent path finding using bandit-based large neighborhood search." *Proceedings of the AAAI Conference on Artificial Intelligence*. Vol. 38. No. 16. 2024.

Kirilenko, Daniil, et al. "Transpath: Learning heuristics for grid-based pathfinding via transformers." *Proceedings of the AAAI Conference on Artificial Intelligence*. Vol. 37. No. 10. 2023.

## 4. 使用其他NP问题求解器

SAT求解器

论文：

Surynek, Pavel, et al. "Sub-optimal sat-based approach to multi-agent path-finding problem." *Proceedings of the International Symposium on Combinatorial Search*. Vol. 9. No. 1. 2018.

Surynek, Pavel, et al. "Migrating Techniques from Search-Based Multi-Agent Path Finding Solvers to SAT-Based Approach." *Journal of Artificial Intelligence Research* 73 (2022): 553-618.

# MAPF with Delay Probabilities

带有延迟概率的MAPF问题。

论文：

Ma, Hang, TK Satish Kumar, and Sven Koenig. "Multi-agent path finding with delay probabilities." *Proceedings of the AAAI Conference on Artificial Intelligence*. Vol. 31. No. 1. 2017.

Atzmon, Dor, et al. "Robust multi-agent path finding and executing." *Journal of Artificial Intelligence Research* 67 (2020): 549-579.

# Anonymous MAPF

将智能体移动到一组目标顶点，但哪个智能体达到哪个目标并不重要（Kloder和Hutchinson 2006；Yu和LaValle 2013）。从另一个角度看这种MAPF变体，可以将其视为每个智能体可以被分配到任何目标的MAPF问题，但必须是智能体和目标之间的一对一映射。

论文：

Yu, Jingjin, and Steven M. LaValle. "Multi-agent path planning and network flow." *Algorithmic Foundations of Robotics X: Proceedings of the Tenth Workshop on the Algorithmic Foundations of Robotics*. Berlin, Heidelberg: Springer Berlin Heidelberg, 2013.

Ali, Zain Alabedeen, and Konstantin Yakovlev. "Improved anonymous multi-agent path finding algorithm." *Proceedings of the AAAI Conference on Artificial Intelligence*. Vol. 38. No. 16. 2024.

# MAPD (life-long MAPF)

不断有取送货任务下发。

论文：

Ma, Hang, et al. "Lifelong multi-agent path finding for online pickup and delivery tasks." *arXiv preprint arXiv:1705.10868* (2017).

Li, Jiaoyang, et al. "Lifelong multi-agent path finding in large-scale warehouses." Proceedings of the AAAI Conference on Artificial Intelligence. Vol. 35. No. 13. 2021.

Hönig, Wolfgang, et al. "Conflict-based search with optimal task assignment." *Proceedings of the International Joint Conference on Autonomous Agents and Multiagent Systems*. 2018.

代码：