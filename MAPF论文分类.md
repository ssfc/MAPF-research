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

