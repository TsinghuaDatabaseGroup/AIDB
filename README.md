## AI4DB & DB4AI-Papers

Continuously update the AI4DB & DB4AI (ML4DB & DB4ML) papers and source codes based on our past tutorials. Please inform us if there are any great papers missed :) 



Table of Contents
=================

* [0. Survey & Tutorial](#0-system-&-tutorial)
* [1. Database Configuration](#1-database-configuration)
	* [1.1 Knob Tuner](#Knob-Tuner)
	* [1.2 View Advisor](#view-advisor)
	* [1.3 Index Advisor](#index-advisor)
	* [1.4 Query Rewriter](#query-rewriter)
	* [1.5 Partition Advisor](#partition-advisor)
* [2. Query Optimization](#2-query-optimization)
	* [2.1 Cardinality/Cost Estimation](#Cost-Estimation)
	* [2.2 Join Enumerator](#Join-Enumerator)
	* [2.3 Plan Hinter](#plan-hinter)
* [3. Database Design](#3-database-design)
	* [3.1 Physical Design](#physical-design)
	* [3.2 Query Execution](#query-execution)
* [4. Database Monitoring](#4-database-monitoring)
* [5. Database Diagnosis](#5-database-diagnosis)
	* [5.1 System Diagnosis](#System-Diagnosis)
	* [5.2 Query Diagnosis](#Query-Diagnosis)
* [6. Autonomous Database](#6-autonomous-database)
* [7. Demonstrations](#7-demonstrations)
* [8. Talks](#8-talks)



## 0. Survey & Tutorial

**[Survey]** Xuanhe Zhou, Chengliang Chai, Guoliang Li, Ji Sun. Database Meets AI: A Survey. IEEE Transactions on Knowledge and Data Engineering (TKDE), 2020. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/aidb.pdf)]

**[Survey]** Wang, W., Zhang, M., Chen, G., Jagadish, H. V., Ooi, B. C., & Tan, K. L. (2016). Database meets deep learning: Challenges and opportunities. SIGMOD, 2016. [[paper](https://doi.org/10.1145/3003665.3003669)] 

**[Survey]** Cai, Q., Cui, C., Xiong, Y., Xie, Z., & Zhang, M. (2021). A Survey on Deep Reinforcement Learning for Data Processing and Analytics, 2021. [[paper](http://arxiv.org/abs/2108.04526)]

**[Tutorial]** Idreos, S., & Kraska, T. (2019). From auto-tuning one size fits all to self-designed and learned data-intensive systems. Proceedings of the ACM SIGMOD International Conference on Management of Data, 2054–2059. [[paper](https://doi.org/10.1145/3299869.3314034)] 

**[Tutorial]** Guoliang Li, Xuanhe Zhou, Lei Cao. AI Meets Database: AI4DB and DB4AI. SIGMOD 2021. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/sigmod21-tutorial-paper.pdf)] [[slides](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/sigmod21-tutorial-slides.pdf)]

**[Tutorial]** Guoliang Li, Xuanhe Zhou, Lei Cao. Machine Learning for Databases. VLDB 2021. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb21-tutorial-paper.pdf)] [[slides](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb21-tutorial-slides.pdf)]

**[Tutorial]** Lu, J., Chen, Y., Herodotou, H., Babu, S. (2019). *Speedup Your Analytics : Automatic Parameter Tuning for Databases and Big Data Systems*, VLDB, 2019. [[paper](http://www.vldb.org/pvldb/vol12/p1970-lu.pdf)] [[slides](https://pdfs.semanticscholar.org/a784/25f87ec066c51043380f93502950e044cca3.pdf)]

**[Tutorial]** Jindal, A., & Interlandi, M. (n.d.). *Machine Learning for Cloud Data Systems : the Promise , the Progress , and the Path Forward*. VLDB, 2021. [[paper](http://vldb.org/pvldb/vol14/p3202-jindal.pdf)] 



## 1. Database Configuration

### Knob Tuner

**[DB]** Zhang, J., Liu, Y., Zhou, K., Li, G., Xiao, Z., Cheng, B., … Li, Z. (2019). An end-to-end automatic cloud database tuning system using deep reinforcement learning. SIGMOD, 2019. [[paper](https://doi.org/10.1145/3299869.3300085)]

**[DB]** Aken, D. Van, Pavlo, A., Gordon, G. J., & Zhang, B. (2017). Automatic database management system tuning through large-scale machine learning. SIGMOD, 2017. [[paper](https://doi.org/10.1145/3035918.3064029)]

**[DB]** Li, G., Zhou, X., Gao, B., & Li, S. (2019). *QTune: A Query-Aware Database Tuning System with Deep Reinforcement Learning*. VLDB, 2019. [[paper](http://www.vldb.org/pvldb/vol12/p2118-li.pdf)] 

**[DB]** Zhang, X., Tan, J., & Cui, B. (n.d.). *ResTune : Resource Oriented Tuning Boosted by Meta-Learning for Cloud Databases*. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3457291)]

**[DB]** Tan, J., Zhang, T., Li, F., Chen, J., Zheng, Q., & Zhang, P. (2019). iBTune : Individualized Buffer Tuning for Large-scale Cloud Databases. VLDB, 2021. [[paper](http://www.vldb.org/pvldb/vol12/p1221-tan.pdf)]

**[DB]** Van Aken, D., Yang, D., Brillard, S., Fiorino, A., Zhang, B., Bilien, C., & Pavlo, A. (2021). An inquiry into machine learning-based automatic configuration tuning services on real-world database management systems. VLDB,  2021. [[paper](https://doi.org/10.14778/3450980.3450992)]

**[DB]** Thummala, V., & Babu, S. (2010). iTuned: A tool for configuring and visualizing database parameters. SIGMOD, 2010. [[paper](https://doi.org/10.1145/1807167.1807327)]

**[DB]** Zhu, Y., Liu, J., Guo, M., Bao, Y., & Ma, W. (2017). *BestConfig : Tapping the Performance Potential of Systems via Automatic Configuration Tuning*, SoCC, 2017. [[paper](https://doi.org/10.1145/3127479.3128605)]

**[KV Store]** Jiake Ge, Ynagfeng Chai, Yunpeng Chai. *A Workload-aware Tuning System of Key-Value Stores with Attention-Based Deep Reinforcement Learning 1*. (n.d.). JCST, 2021.

**[Spark]** Gallinucci, E., & Golfarelli, M. (2019). *SparkTune : tuning Spark SQL through query cost modeling*. EDBT, 546–549. [[paper](https://openproceedings.org/2019/conf/edbt/EDBT19_paper_226.pdf)]

**[Spark]** Kunjir, M., & Babu, S. (2020). *Black or White? How to Develop an AutoTuner for Memory-based Analytics [Extended Version]*. SIGMOD, 2020. [[paper](https://doi.org/10.1145/3318464.3380591)]

**[SSD]** Kakaraparthy, A., & Kroth, B. P. (n.d.). *Optimizing Databases by Learning Hidden Parameters of Solid State Drives*. VLDB, 2019. [[paper](http://www.vldb.org/pvldb/vol13/p519-kakaraparthy.pdf)]

**[IT Stack]** Cereda, S., Doni, S., & Milano, P. (n.d.). *CGPTuner : a Contextual Gaussian Process Bandit Approach for the Automatic Tuning of IT Configurations Under Varying Workload Conditions*. VLDB, 2021. [[paper](https://doi.org/10.14778/3457390.3457404)] 

**[App]** Xu, Q., Hu, Y. C., & Jindal, A. (2020). *App Parameter Energy Profiling: Optimizing App Energy Drain by Finding Tunable App Parameters*. arXiv, 2020. [[paper](http://arxiv.org/abs/2009.12156)]

### View Advisor

A. Jindal, K. Karanasos, S. Rao, and H. Patel. Selecting subexpressions to materialize at datacenter scale. PVLDB, 11(7):800–812, 2018.[[paper](http://www.vldb.org/pvldb/vol11/p800-jindal.pdf)]

Ahmed, R., Bello, R., Witkowski, A., & Kumar, P. (2020). Automated generation of materialized views in Oracle. VLDB, 2020. [[paper](https://doi.org/10.14778/3415478.3415533)]

Yuan, H., Sun, J., & Li, G. (2020). *Automatic View Generation for Equivalent Subqueries with Deep Learning and Reinforcement Learning*. ICDE, 2020. [[paper](https://doi.org/10.1109/ICDE48307.2020.00133)]

Han, Y., Li, G., Yuan, H., & Sun, J. (n.d.). *An Autonomous Materialized View Management System with Deep Reinforcement Learning*. ICDE, 2021. [[paper](https://doi.org/10.1109/ICDE51399.2021.00217)]

### Index Advisor

Agrawal, S., Bruno, N., Chaudhuri, S., & Narasayya, V. (2006). AutoAdmin : Self-Tuning Database Systems Technology 2 Physical Database Design Tuning. *Data Engineering*, 2006. [[paper]()]

Sadri, Z., & Gruenwald, L. (2020). *Online Index Selection Using Deep Reinforcement Learning for a Cluster Database*. ICDE Workshop, 2020. [[paper](https://doi.org/10.1109/ICDEW49219.2020.00035)]

Kossmann, J., Halfpap, S., Jankrift, M., & Schlosser, R. (2020). Magic mirror in my hand, which is the best in the land? An experimental  evaluation of index selection algorithms. VLDB, 2020. [[paper](http://www.vldb.org/pvldb/vol13/p2382-kossmann.pdf)]

Ding, B., Das, S., Marcus, R., Wu, W., Chaudhuri, S., & Narasayya, V. R. (2019). AI meets AI: Leveraging query executions to improve index recommendations. SIGMOD, 2019. [[paper](https://doi.org/10.1145/3299869.3324957)]

Borovica-gajic, R., Perera, M., Oetomo, B., & Rubinstein, B. I. P. (2019). *DBA bandits : Self-driving physical design tuning under ad-hoc workloads with safety guarantees*. arXiv, 2019. [[paper](https://arxiv.org/pdf/2010.09208.pdf)]

Paludo, G., Julia, L., Couto, C., Fátima, P. De, & Renata, M. (n.d.). *S MART IX : A database indexing agent based on reinforcement learning*. 2020. [[paper](https://link.springer.com/article/10.1007/s10489-020-01674-8)]

Hai Lan, Zhifeng Bao, Yuwei Peng. An Index Advisor Using Deep Reinforcement Learning. CIKM, 2020. [[paper](https://doi.org/10.1145/3340531.3412106)]

Vishal Sharma, Curtis E. Dyreson, Nicholas Flann. MANTIS: Multiple Type and Attribute Index Selection using Deep Reinforcement Learning. IDEAS, 2021. [[paper](https://dl.acm.org/doi/abs/10.1145/3472163.3472176)]


### Query Rewriter

**[performance]** Pirahesh, H., & Hellerstein, J. M. (1992). Extensible / Rule Based Query Rewrite Optimization in Starburst. SIGMOD, 1992. [[paper](https://doi.org/10.1145/130283.130294)]

**[performance]** De Araújo, A. H. M., Monteiro, J. M., Antônio, J., De Macêdo, F., Tavares, J. A., Brayner, A., & Lifschitz, S. (2014). *ARe-SQL: An Online, Automatic and Non-Intrusive Approach for Rewriting SQL Queries*. JIDM, 2014.

**[performance]** Begoli, E., Camacho-Rodríguez, J., Hyde, J., Mior, M. J., & Lemire, D. (2018). Apache calcite: A foundational framework for optimized query processing over heterogeneous data sources. SIGMOD, 2018. [[paper](https://doi.org/10.1145/3183713.3190662)]

**[performance]** Wu, W., Bernstein, P. A., Raizman, A., & Pavlopoulou, C. (2020). *Cost-based Query Rewriting Techniques for Optimizing Aggregates Over Correlated Windows*. arXiv, 2020. [[paper](http://arxiv.org/abs/2008.12379)]

**[performance]** Wu, J. (2021). *Sia : Optimizing Queries using Learned Predicates*. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3457262)]

**[performance]** Xuanhe Zhou, Guoliang Li, Chengliang Chai, Jianhua Feng. A Learned Query Rewrite System using Monte Carlo Tree Search. VLDB, 2022. [paper]

**[redundancy]** Sarthi, P., Rajan, K., Lal, A., Jain, P., Liu, M., Gosalia, A., & Kalikar, S. (2020). *Generalized Sub-Query Fusion for Eliminating Redundant I / O from Big-Data Queries*. OSDI, 2020. [[paper](https://www.usenix.org/conference/osdi20/presentation/sarthi)]

**[equivalence]** Chu, S., Weitz, K., Cheung, A., & Suciu, D. (2017). HoTTSQL: Proving query rewrites with univalent SQL semantics. *ACM SIGPLAN Notices*, *52*(6), 510–524. [[paper](https://doi.org/10.1145/3062341.3062348)]

### Partition Advisor

**[horizontal]** Boissier, M., & Daniel, K. (2018). Workload-driven horizontal partitioning and pruning for large HTAP systems. *Proceedings - IEEE 34th International Conference on Data Engineering Workshops, ICDEW 2018*, (April 2018), 116–121. [[paper](https://doi.org/10.1109/ICDEW.2018.00026)]

**[horizontal]** Agrawal, S., Chu, E., & Narasayya, V. (2006). Automatic physical design tuning: Workload as a sequence. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, 683–694. [[paper](https://doi.org/10.1145/1142473.1142549)]

**[horizontal]** Curino, C., Jones, E., Zhang, Y., & Madden, S. (2010). Schism: A workload-driven approach to database replication and partitioning. *Proceedings of the VLDB Endowment*, *3*(1), 48–57. [[paper](https://doi.org/10.14778/1920841.1920853)]

**[horizontal]** Bandle, M., Giceva, J., & Neumann, T. (2021). To Partition, or Not to Partition, That is the Join Question in a Real System. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3452831)]

**[horizontal]** Parchas, P., Naamad, Y., Van Bouwel, P., Faloutsos, C., & Petropoulos, M. (2020). Fast and effective distribution-key recommendation for amazon redshift. *Proceedings of the VLDB Endowment*, *13*(11), 2411–2423. [[paper](https://doi.org/10.14778/3407790.3407834)]

**[horizontal]** Hilprecht, B., Binnig, C., & Röhm, U. (2019). Towards learning a partitioning advisor with deep reinforcement learning. *Proceedings of the ACM SIGMOD International Conference on Management of Data*. [[paper](https://doi.org/10.1145/3329859.3329876)]

**[co-partition]** Zamanian, E., Binnig, C., & Salama, A. (2015). Locality-aware partitioning in parallel database systems. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, *2015*-*May*, 17–30. [[paper](https://doi.org/10.1145/2723372.2723718)]

**[co-partition]** Rabl, T., & Jacobsen, H. A. (2017). Query centric partitioning and allocation for partially replicated database systems. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, *Part F1277*, 315–330. [[paper](https://doi.org/10.1145/3035918.3064052)]

**[situ]** Olma, M., Karpathiotakis, M., Alagiannis, I., Athanassoulis, M., & Ailamaki, A. (2020). Adaptive partitioning and indexing for in situ query processing. *VLDB Journal*, *29*(1), 569–591. [[paper](https://doi.org/10.1007/s00778-019-00580-x)]

Sun, L., Franklin, M. J., Krishnan, S., & Xin, R. S. (2014). Fine-grained partitioning for aggressive data skipping. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, 1115–1126. [[paper](https://doi.org/10.1145/2588555.2610515)]



## 2. Query Optimization

### Cost Estimation

**[Card, Query-based]** Kipf A, Kipf T, Radke B, et al. Learned cardinalities: Estimating correlated joins with deep learning. CIDR, 2019. [[paper](https://arxiv.org/pdf/1809.00677)]

**[Card, Query-based]** Woltmann L, Hartmann C, Thiele M, et al. Cardinality estimation with local deep learning models. aiDM, 2019. [[paper](https://doi.org/10.1145/3329859.3329875)]

**[Card, Query-based]** Tzoumas K, Deshpande A, Jensen C S. Lightweight graphical models for selectivity estimation without independence assumptions[J]. Proceedings of the VLDB Endowment, 4(11): 852-863, 2011. [[paper](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.228.675&rep=rep1&type=pdf)]

**[Card, Query-based]** Hayek, R., & Shmueli, O. (2020). *NN-based Transformation of Any SQL Cardinality Estimator for Handling DISTINCT, AND, OR and NOT*. arXiv， 2020. [[paper](http://arxiv.org/abs/2004.07009)]

**[Card, Data-based]** Zhu R, Wu Z, Han Y, et al. FLAT: Fast, Lightweight and Accurate Method for Cardinality Estimation[J]. arXiv preprint arXiv:2011.09022, 2020. [[paper](https://arxiv.org/pdf/2011.09022)]

**[Card, Data-based]** Yang, Z., Kamsetty, A., Luan, S., Liang, E., Duan, Y., Chen, X., & Stoica, I. (2020). Neurocard: One cardinality estimator for all tables. *Proceedings of the VLDB Endowment*, *14*(1), 61–73, 2020. [[paper](https://doi.org/10.14778/3421424.3421432)]

**[Card, Data-based]** Wu Z, Shaikhha A, Zhu R, et al. BayesCard: Revitilizing Bayesian Frameworks for Cardinality Estimation. arXiv preprint arXiv: 2012.14743, 2020. [[paper](https://arxiv.org/pdf/2012.14743)]

**[Card, Data-based]** Leis, V., Radke, B., Gubichev, A., Kemper, A., & Neumann, T. (2017). Cardinality estimation done right: Index-based join sampling. CIDR, 2017. [[paper](http://cidrdb.org/cidr2017/papers/p9-leis-cidr17.pdf)]

**[Card, Data-based]** Hilprecht, B., Schmidt, A., Kulessa, M., Molina, A., Kersting, K., & Binnig, C. (2020). DeepDB: Learn from data, not from queries! *Proceedings of the VLDB Endowment*, *13*(7), 992–1005, 2020. [[paper](https://doi.org/10.14778/3384345.3384349)]

**[Card, Data-based]** Yang, Z., Liang, E., Kamsetty, A., Wu, C., Duan, Y., Chen, X., … Stoica, I. (2019). Deep Unsupervised Cardinality Estimation. VLDB, 2019. [[paper](https://doi.org/10.14778/3368289.3368294)]

**[Card, Data-based]** Dutt, A., Wang, C., Nazi, A., Kandula, S., Narasayya, V., & Chaudhuri, S. (2018). Selectivity estimation for range predicates using lightweight models. Proceedings of the VLDB Endowment, 12(9), 1044–1057, 2018. [[paper](https://doi.org/10.14778/3329772.3329780)]

**[Card, Data-based]** Zhu, R., Wu, Z., Han, Y., Zeng, K., Pfadler, A., Qian, Z., … Cui, B. (2020). FLAT: Fast, Lightweight and Accurate Method for Cardinality Estimation. VLDB, 2021. [[paper](http://arxiv.org/abs/2011.09022)]

**[Card, Data-based]** Hasan S, Thirumuruganathan S, Augustine J, et al. *Deep learning models for selectivity estimation of multi-attribute queries.* SIGMOD, 2020. [[paper](https://dl.acm.org/doi/pdf/10.1145/3318464.3389741)]

**[Card, Data-based]** Heimel M, Kiefer M, Markl V. Self-tuning, GPU-accelerated kernel density models for multidimensional selectivity estimation. Proceedings of the ACM SIGMOD, 2015. [[paper](https://dl.acm.org/doi/pdf/10.1145/2723372.2749438)]

**[Card, Data-based]** Jiayi Wang, Chengliang Chai, Jiabin Liu, Guoliang Li. FACE: A Normalizing Flow based Cardinality Estimator. VLDB 2022. [[paper](https://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb22-flow-card.pdf)]

**[Card, Query&Data-based]** Wu P, Cong G. A Unified Deep Model of Learning from both Data and Queries for Cardinality Estimation[C]//Proceedings of the 2021 International Conference on Management of Data. 2021: 2009-2022. [[paper](https://arxiv.org/pdf/2107.12295)]

**[Card]** Parimarjan Negi, Ryan C. Marcus, Andreas Kipf, Hongzi Mao, Nesime Tatbul, Tim Kraska, Mohammad Alizadeh. Flow-Loss: Learning Cardinality Estimates That Matter. VLDB Endow, 14(11): 2019-2032, 2021. [[paper](http://www.vldb.org/pvldb/vol14/p2019-negi.pdf)] 

**[Cost]** Marcus, R., & Papaemmanouil, O. (2019). *Plan-Structured Deep Neural Network Models for Query Performance Prediction*. 1733–1746. [[paper](http://arxiv.org/abs/1902.00132)]

**[Cost]** Sun, J., & Li, G. (n.d.). *An End-to-End Learning-based Cost Estimator*. VLDB, 2020. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb2020-learnedcost.pdf)]

**[ EA&B ]** Wang, X., Qu, C., Wu, W., Wang, J., & Zhou, Q. (2020). Are We Ready For Learned Cardinality Estimation? In *Proceedings of ACM Conference (Conference’17)* (Vol. 1). [[paper](http://arxiv.org/abs/2012.06743)]

**[ EA&B ]** Sun, J., Zhang, J., Sun, Z., Li, G., & Tang, N. (n.d.). *Learned Cardinality Estimation : A Design Space Exploration and a Comparative Evaluation [ EA & B ]*. *14*(1). VLDB, 2022. [[paper](http://arxiv.org/abs/2012.06743)]

**[ EA&B ]** Yuxing Han, Ziniu Wu, Peizhi Wu, et al. Cardinality Estimation in DBMS: A Comprehensive Benchmark Evaluation Yuxing. VLDB, 2022. [[paper](https://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb22-card-exp.pdf)]  

**[ EA&B ]** Harmouch, H., & Naumann, F. (2018). Cardinality Estimation: An Experimental Survey. *Pvldb*, *11*(4), 4999–512, 2017. [[paper](https://doi.org/10.1145/3164135.3164145)]

### Join Enumerator

Marcus, R., Negi, P., Mao, H., Zhang, C., Alizadeh, M., Kraska, T., … Tatbul, N. (2018). Neo: A Learned query optimizer. *Proceedings of the VLDB Endowment*, *12*(11), 1705–1718, 2018. [[paper](https://doi.org/10.14778/3342263.3342644)]

Marcus, R., & Papaemmanouil, O. (2018). Deep reinforcement learning for join order enumeration. *Proceedings of the 1st International Workshop on Exploiting Artificial Intelligence Techniques for Data Management, AiDM 2018*, 0–3. [[paper](https://doi.org/10.1145/3211954.3211957)]

Leis, V., Gubichev, A., Mirchev, A., Boncz, P., Kemper, A., & Neumann, T. (2016). How Good Are Query Optimizers, Really? *Proceedings of the VLDB Endowment*, *9*(3), 204–215. [[paper](https://doi.org/10.14778/2850583.2850594)]

Trummer, I., Wang, J., Maram, D., Moseley, S., Jo, S., & Antonakakis, J. (n.d.). SkinnerDB : Regret-Bounded Query Evaluation via Reinforcement Learning. SIGMOD, 2019. [[paper](https://arxiv.org/abs/1901.05152)]

Ding, M., Chen, S., & Manegold, S. (2021). *Progressive Join Algorithms Considering User Preference. CIDR, 2021. [[paper](http://cidrdb.org/cidr2021/papers/cidr2021_paper02.pdf)]

Yu, X., Li, G., Tang, N. (n.d.). Reinforcement Learning with Tree-LSTM for Join Order Selection. ICDE, 2020. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/icde2020-learnedjoinorder.pdf)]


Chenggang Wu, Alekh Jindal, Saeed Amizadeh, Hiren Patel, Wangchao Le, Shi Qiao, Sriram Rao. Towards a Learning Optimizer for Shared Clouds. Proc. VLDB Endow. 12(3): 210-222, 2018. [[paper](http://www.vldb.org/pvldb/vol12/p210-wu.pdf)]

### Plan Hinter

Pasupuleti, K., Park, M., & Valluri, S. (n.d.). SQL Plan Observability through Hints in Oracle Autonomous Database.

Marcus, R., Negi, P., Mao, H., Tatbul, N., Alizadeh, M., & Kraska, T. (2020). Bao: Making Learned Query Optimization Practical. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3452838)]

Parimarjan Negi, Matteo Interlandi, Ryan Marcus, Mohammad Alizadeh, Tim Kraska, Marc Friedman, Alekh Jindal. Steering Query Optimizers: A Practical Take on Big Data Workloads. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3457568)]



## 3. Database Design

### Physical Design

**[Learned Index, mutable]** Galakatos, A., Markovitch, M., Binnig, C., Fonseca, R., & Kraska, T. (2019). Fiting-tree: A data-aware index structure. *Proceedings of the 2019 International Conference on Management of Data*, 1189-1206. [[paper](https://dl.acm.org/doi/abs/10.1145/3299869.3319860)]

**[Learned Index, mutable]** Ferragina, P., & Vinciguerra, G. (2020). The PGM-index : a fully-dynamic compressed learned index with provable worst-case bounds. *The Proceedings of the VLDB Endowment (PVLDB)*, *13*(8), 1162–1175. [[paper](https://dl.acm.org/doi/abs/10.14778/3389133.3389135)]

**[Learned Index, mutable]** Hadian, A., & Heinis, T. (n.d.). MADEX : Learning-augmented Algorithmic Index Structures. *( Regular Papers )*. [[paper](http://www.hadian.org/files/papers/hadian2020madex.pdf)] [[slides](http://www.hadian.org/files/papers/hadian2020madex_slides.pdf)]

**[Learned Index, immutable]** Kraska, T., Beutel, A., Chi, E. H., Dean, J., & Polyzotis, N. (2018). The case for learned index structures. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, 489–504. [[paper](https://doi.org/10.1145/3183713.3196909)]

**[Learned Index, immutable, multi-d]** Nathan, V., Ding, J., Alizadeh, M., & Kraska, T. (2020). Learning multi-dimensional indexes. *Proceedings of the 2020 ACM SIGMOD International Conference on Management of Data*, 985-1000. [[paper](https://dl.acm.org/doi/10.1145/3318464.3380579)]

**[Learned Index, immutable, multi-d]** Ding, J., Nathan, V., Alizadeh, M., & Kraska, T. (2020). Tsunami: A learned multi-dimensional index for correlated data and skewed workloads. *Proceedings of the VLDB Endowment*, *14*(2), 74-86. [[paper](https://dl.acm.org/doi/abs/10.14778/3425879.3425880)]

**[Learned Index, immutable, multi-d]** Wu, J., Zhang, Y., Chen, S., Wang, J., Chen, Y., & Xing, C. (2021). Updatable Learned Index with Precise Positions. *Proceedings of the VLDB Endowment*, *14*(8), 1276-1288. [[paper](https://arxiv.org/abs/2104.05520)]

Anders Hammershøj Jensen, Frederik Lauridsen, Fatemeh Zardbani, Stratos Idreos, Panagiotis Karras. Revisiting Multidimensional Adaptive Indexing [Experiment & Analysis]. EDBT 2021: 469-474. [[paper](https://cs.au.dk/~karras/p46.pdf)] 

**[Learned Layout]** Yang, Z., Chandramouli, B., Wang, C., Gehrke, J., Li, Y., Minhas, U. F., … Acharya, R. (n.d.). *Qd-tree : Learning Data Layouts for Big Data Analytics*. SIGMOD, 2020. [[paper](https://doi.org/10.1145/3183713.3196909)]

### Query Execution

Zhang, C., Marcus, R., Kleiman, A., & Papaemmanouil, O. (2020). Buffer Pool Aware Query Scheduling via Deep Reinforcement Learning. AIDB@VLDB, 2020. [[paper](https://arxiv.org/abs/2007.10568)]



## 4. Database Monitoring

**[Performance Prediction]** Dorn, J., Apel, S., & Siegmund, N. (n.d.). *Mastering Uncertainty in Performance Estimations of Configurable Software Systems*. (3).

**[Performance Prediction]** Marcus, R., & Papaemmanouil, O. (2019). Plan-structured deep neural network models for query performance prediction. *Proceedings of the VLDB Endowment*, *12*(11), 1733–1746. [[paper](https://doi.org/10.14778/3342263.3342646)]

**[Performance Prediction]** Wu, W., Chi, Y., Hacig̈um̈uş, H., & Naughton, J. F. (2013). Towards predicting query execution time for concurrent and dynamic database workloads. *Proceedings of the VLDB Endowment*, *6*(10), 925–936. [[paper](https://doi.org/10.14778/2536206.2536219)]

**[Performance Prediction]** Duggan, J., Papaemmanouil, O., Cetintemel, U., & Upfal, E. (2014). Contender: A resource modeling approach for concurrent query performance prediction. *Advances in Database Technology - EDBT 2014: 17th International Conference on Extending Database Technology, Proceedings*, 109–120. [[paper](https://doi.org/10.5441/002/edbt.2014.11)]

**[Performance Prediction]** Wu, W., Chi, Y., Zhu, S., Tatemura, J., Hacigümüş, H., & Naughton, J. F. (2013). Predicting query execution time: Are optimizer cost models really unusable? *Proceedings - International Conference on Data Engineering*, (1), 1081–1092. [[paper](https://doi.org/10.1109/ICDE.2013.6544899)]

**[Performance Prediction]** Higginson, A. S., Dediu, M., Arsene, O., Paton, N. W., & Embury, S. M. (2020). Database Workload Capacity Planning using Time Series Analysis and Machine Learning. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, 769–783. [[paper](https://doi.org/10.1145/3318464.3386140)]

**[Performance Prediction]** Unterbrunner, P., Giannikis, G., Alonso, G., Fauser, D., & Kossmann, D. (2009). Predictable performance for unpredictable workloads. *Proceedings of the VLDB Endowment*, *2*(1), 706–717. [[paper](https://doi.org/10.14778/1687627.1687707)]

**[Performance Prediction]** Xuanhe Zhou, Ji Sun, Guoliang Li, Jianhua Feng. Query Performance Prediction for Concurrent Queries using Graph Embedding. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb2020-concurrent.pdf)]



## 5. Database Diagnosis

### System Diagnosis

Yoon, D. Y., Niu, N., & Mozafari, B. (2016). DBSherlock: A performance diagnostic tool for transactional databases. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, *26*-*June*-*20*(i), 1599–1614. [[paper](https://web.eecs.umich.edu/~mozafari/php/data/uploads/sigmod_2016.pdf)]

Kalmegh, P., Babu, S., & Roy, S. (2019). iQCAR: inter-Query Contention Analyzer for Data Analytics Frameworks. SIGMOD. [[paper](https://dl.acm.org/doi/10.1145/3299869.3319904)]

Ma, M., Yin, Z., Zhang, S., Wang, S., Zheng, C., & Jiang, X. (2020). Diagnosing Root Causes of Intermittent Slow Queries in Cloud Databases. *PVLDB Endowment.* [[paper](http://www.vldb.org/pvldb/vol13/p1176-ma.pdf)]

### Query Diagnosis



## 6. Autonomous Database

**[AutoDB]** Pavlo, A., Angulo, G., Arulraj, J., Lin, H., Lin, J., Ma, L., … Zhang, T. (2017). Self-Driving Database Management Systems. CIDR, 2017. [[paper](https://www.pdl.cmu.edu/PDL-FTP/Database/p42-pavlo-cidr17.pdf)]

**[NLP]** James Thorne, Majid Yazdani, Marzieh Saeidi, Fabrizio Silvestri, Sebastian Riedel, Alon Y. Levy. From Natural Language Processing to Neural Databases. VLDB, 2021. [[paper](http://www.vldb.org/pvldb/vol14/p1033-thorne.pdf)]

**[Embedding]** Raasveldt, M. (2018). MonetDBLite: An embedded analytical database. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, 1837–1838. [[paper](https://arxiv.org/pdf/1805.08520.pdf#:~:text=MonetDBLite%20is%20an%20in%2Dprocess,%2C%20R%2C%20Python%20and%20Java.)]

**[AutoDB]** Li, F. (2018). Cloud native database systems at Alibaba: Opportunities and challenges. *Proceedings of the VLDB Endowment*, 2018. [[paper](https://doi.org/10.14778/3352063.3352141)]

**[AutoDB]** Kraska, T., Alizadeh, M., Beutel, A., Chi, E. H., Ding, J., Kristo, A., … Nathan, V. (2019). SageDB: A learned database system. CIDR, 2019. [[paper](http://www.alexbeutel.com/papers/CIDR2019_SageDB.pdf)]

**[AutoDB]** Li, G., Zhou, X., Li, S. (2019). *XuanYuan: An AI-Native Database*. Data Eng., 2019. [[paper](http://sites.computer.org/debull/A19june/p70.pdf)]

**[AutoDB]** Hilprecht, B., Bang, T., El-Hindi, M., Hättasch, B., Khanna, A., Rehrmann, R., … Binnig, C. (2020). DBMS Fitting: Why should we learn what we already know? Cidr, 2020. [[paper](http://cidrdb.org/cidr2020/papers/p34-hilprecht-cidr20.pdf)]

**[AutoDB]** Guoliang Li, Xuanhe Zhou, , Ji Sun, Xiang Yu, Yue Han, Lianyuan Jin, Wenbo Li, Tianqing Wang, Shifu Li. openGauss: An Autonomous Database System. VLDB, 2021. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb21-opengauss.pdf)]

**[AutoDB]** Ma, L., Zhang, W., Jiao, J., Wang, W., Butrovich, M., Lim, W. S., … Pavlo, A. (2021). *MB2 : Decomposed Behavior Modeling for Self-Driving Database Management Systems*. SIGMOD, 2021. [[paper](https://dl.acm.org/doi/10.1145/3448016.3457276)]



## 7. Demonstrations

**[DB Tuning]** Zhang, B., Van Aken, D., Wang, J., Dai, T., Jiang, S., Lao, J., . A Demonstration of the ottertune automatic database management system tuning service. VLDB, 1910–1913. [[paper](http://www.vldb.org/pvldb/vol11/p1910-zhang.pdf)]

**[DB Tuning]** Junxiong Wang, Immanuel Trummer, Debabrota Basu. Demonstrating UDO: A Unified Approach for Optimizing Transaction Code, Physical Design, and System Parameters via Reinforcement Learning. SIGMOD, 2021. [[paper](https://dl.acm.org/doi/abs/10.1145/3448016.3452754)]

**[AutoDB]** Xuanhe Zhou, Lianyuan Jin, Ji Sun, Xinyang Zhao, Xiang Yu, Shifu Li, Tianqing Wang, Kun Li, luyang liu. DBMind: A Self-Driving Platform in openGauss. [[paper](http://vldb.org/pvldb/vol14/p2743-zhou.pdf)] [[website](https://www.dbmind.cn/)] 



## 8. Talks

**[AutoDB]** Pavlo, A., Butrovich, M., Ma, L., Menon, P., Lim, W. S., Aken, D. Van, & Zhang, W. (n.d.). *Make Your Database System Dream of Electric Sheep : Towards Self-Driving Operation*. VLDB, 2021. [[paper](https://vldb.org/pvldb/vol14/p3211-pavlo.pdf)]

**[AutoDB]** Kraska, T.. Towards instance-optimized data systems. VLDB, 2021. [[paper](http://vldb.org/pvldb/vol14/p3222-kraska.pdf)]

**[AutoDB]** Guoliang Li. AI-Native Database. VLDB, 2021.
