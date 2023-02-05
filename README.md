## Autonomous Database Papers

Continuously update the autonomous database (AI4DB & DB4AI) papers and source codes based on our past tutorials. Please inform us if there are any great papers missed :)

Table of Contents
=================

* [0. Survey and Tutorial (12)](#0-survey-and-tutorial)
* [1. Database Configuration](#1-database-configuration)
    * [1.1 Knob Tuner (20)](#Knob-Tuner)
    * [1.2 View Advisor (5)](#view-advisor)
    * [1.3 Index Advisor (20)](#index-advisor)
    * [1.4 Partition Advisor (10)](#partition-advisor)
* [2. Query Optimization](#2-query-optimization)
    * [2.1 Query Rewriter (11)](#query-rewriter)
    * [2.2 Cardinality/Cost Estimation (28)](#Cost-Estimation)
    * [2.3 Plan Optimization (11)](#plan-optimization)
    * [2.4 Plan Hinter (3)](#plan-hinter)
* [3. Workload Scheduling (2)](#3-workload-scheduling)
* [4. Database Design](#4-database-design)
    * [4.1 Index and Layout (23)](#index-and-layout)
    * [4.2 Query Execution (2)](#query-execution)
* [5. Database Monitoring (9)](#5-database-monitoring)
* [6. Database Diagnosis](#6-database-diagnosis)
    * [6.1 System Diagnosis (3)](#System-Diagnosis)
    * [6.2 Query Diagnosis (1)](#Query-Diagnosis)
* [7. Training Data Generation](#7-training-data-generation)
    * [7.1 Query Generation (2)](#Query-Generation)
    * [7.2 Data Generation (3)](#Data-Generation)
* [8. AI Techniques](#8-ai-techniques)
    * [8.1 Feature Encoding (5)](#Feature-Encoding)
    * [8.2 Model Transfer (1)](#Model-Transfer) 
* [9. Database Frameworks (14)](#9-database-frameworks)
* [10. Demonstrations](#10-demonstrations)
* [11. Talks](#11-talks)


## 0. Survey and Tutorial

**[Survey | AIDB]** Xuanhe Zhou, Chengliang Chai, Guoliang Li, Ji Sun. Database Meets Artificial Intelligence: A Survey. TKDE, 2020. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/aidb.pdf)]

**[Survey | ML4DB]** Wei Wang, Meihui Zhang, Gang Chen, et al. Database meets deep learning: Challenges and opportunities. SIGMOD Record, 2016. [[paper](https://doi.org/10.1145/3003665.3003669)]

**[Survey | RL4DB]** Qingpeng Cai, Can Cui, Yiyuan Xiong, et al. A Survey on Deep Reinforcement Learning for Data Processing and Analytics. arXive, 2021. [[paper](http://arxiv.org/abs/2108.04526)]

**[Tutorial | AI4DB]** Stratos Idreos, Tim Kraska. From auto-tuning one size fits all to self-designed and learned data-intensive systems. SIGMOD, 2019. [[paper](https://doi.org/10.1145/3299869.3314034)]

**[Tutorial | AI4DB]** Guoliang Li, Xuanhe Zhou, Lei Cao. AI Meets Database: AI4DB and DB4AI. SIGMOD 2021. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/sigmod21-tutorial-paper.pdf)][[slides](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/sigmod21-tutorial-slides.pdf)]

**[Tutorial | AI4DB]** Guoliang Li, Xuanhe Zhou, Lei Cao. Machine Learning for Databases. VLDB 2021. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb21-tutorial-paper.pdf)][[slides](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb21-tutorial-slides.pdf)]

**[Tutorial | AI4Tuning]** 	Jiaheng Lu, Yuxing Chen, Herodotos Herodotou, Shivnath Babu. *Speedup Your Analytics: Automatic Parameter Tuning for Databases and Big Data Systems*, VLDB, 2019. [[paper](http://www.vldb.org/pvldb/vol12/p1970-lu.pdf)][[slides](https://pdfs.semanticscholar.org/a784/25f87ec066c51043380f93502950e044cca3.pdf)]

**[Tutorial | AI4CloudDB]** 	Alekh Jindal, Matteo Interlandi. *Machine Learning for Cloud Data Systems: the Promise , the Progress , and the Path Forward*. VLDB, 2021. [[paper](http://vldb.org/pvldb/vol14/p3202-jindal.pdf)]

**[Tutorial | AI4Tuning]** Zhengtong Yan, Jiaheng Lu, Naresh Chainani, Chunbin Lin. Workload-Aware Performance Tuning for Autonomous DBMSs. ICDE, 2021. [[paper](https://www2.helsinki.fi/sites/default/files/atoms/files/icde_2021_tutorial_latest.pdf)]

**[Tutorial | AI4DBCluster]** 	Brad Glasbergen, Michael Abebe, Khuzaima Daudjee. Tutorial: Adaptive Replication and Partitioning in Data Systems. Middleware, 2018. [[paper](https://cs.uwaterloo.ca/~kdaudjee/AdaptiveTutorial.pdf)]

**[Tutorial | LearnedIndex]** 	Abdullah Al-Mamun, Hao Wu, Walid G. Aref. A Tutorial on Learned Multi-dimensional Indexes. SIGSPATIAL, 2020. [[paper](https://dl.acm.org/doi/10.1145/3397536.3426358)]

**[Tutorial | NLP4DB]**   Immanuel Trummer. From BERT to GPT-3 Codex: Harnessing the Potential of Very Large Language Models for Data Management. VLDB, 2022. [[paper](https://dl.acm.org/doi/pdf/10.14778/3554821.3554896)]

## 1. Database Configuration

### Knob Tuner

#### Heuristic 

**[Rule-based]** PGTune: https://pgtune.leopard.in.ua.

**[Search-based]** OpenTuner: An Extensible Framework for Program Autotuning (PACT, 2014) [[paper](https://dl.acm.org/doi/pdf/10.1145/2628071.2628092)]

**[Search-based]** BestConfig: Tapping the Performance Potential of Systems via Automatic Configuration Tuning (SoCC, 2017) [[paper](https://dl.acm.org/doi/abs/10.1145/3127479.3128605)]

#### BO-based

**[Gaussian Process]** Tuning Database Conﬁguration Parameters with iTuned. (VLDB, 2009) [[paper](https://users.cs.duke.edu/~shivnath/ituned/paper.pdf)]

**[Gaussian Process]** Automatic database management system tuning through large-scale machine learning. (SIGMOD, 2017) [[paper](https://dl.acm.org/doi/pdf/10.1145/3035918.3064029)]

**[Gaussian Process, Featurization]** Black or White? How to Develop an AutoTuner for Memory-based Analytics (SIGMOD, 2020) [[paper](https://dl.acm.org/doi/pdf/10.1145/3318464.3380591)]

**[Gaussian Process, Model Transferring]** ResTune: Resource Oriented Tuning Boosted by Meta-Learning for Cloud Databases (SIGMOD, 2021) [[paper](https://15799.courses.cs.cmu.edu/spring2022/papers/08-knobs3/zhang-sigmod2021.pdf)]

**[Contextual Gaussian Process]** CGPTuner: a Contextual Gaussian Process Bandit Approach for the Automatic Tuning of IT Configurations Under Varying Workload Conditions (VLDB, 2021) [[paper](https://www.cl.cam.ac.uk/~ey204/teaching/ACS/R244_2021_2022/papers/CGPTUNER_VLDB_2021.pdf)]

**[Bounded Gaussian Process]** Towards Dynamic and Safe Configuration Tuning for Cloud Databases (SIGMOD, 2022) [[paper](https://arxiv.org/pdf/2203.14473)]

**[Gaussian Process]** LlamaTune: Sample-Efficient DBMS Configuration Tuning (VLDB, 2022) [[paper](https://arxiv.org/pdf/2203.05128)]

#### DL-based

**[DL]** iBTune: Individualized Buffer Tuning for Large-scale Cloud Databases (VLDB, 2019) [[paper](http://www.vldb.org/pvldb/vol12/p1221-tan.pdf)]

#### RL-based

**[RL]** An End-to-End Automatic Cloud Database Tuning System Using Deep Reinforcement Learning (SIGMOD, 2019) [[paper](https://dl.acm.org/doi/abs/10.1145/3299869.3300085)]

**[RL, Query Encoding]** QTune: A Query-Aware Database Tuning System with Deep Reinforcement Learning (VLDB, 2019) [[paper](https://15799.courses.cs.cmu.edu/spring2022/papers/08-knobs3/p2118-li.pdf)]

**[Light-weight RL]** Universal Database Optimization using Reinforcement Learning (VLDB, 2021) [[paper](http://www.vldb.org/pvldb/vol14/p3402-wang.pdf)]

**[RL, Pre-trained model]** Watuning: A workload-aware tuning system with attention-based deep reinforcement learning. (JCST, 2021) [[paper](https://link.springer.com/article/10.1007/s11390-021-1350-8)]

**[RL, NLP model]** The Case for NLP-Enhanced Database Tuning: Towards Tuning Tools that "Read the Manual" (VLDB, 2021) [[paper](http://vldb.org/pvldb/vol14/p1159-trummer.pdf)]

**[RL, NLP model]** DB-BERT: a Database Tuning Tool that “Reads the Manual” (SIGMOD, 2022) [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3517843)]

**[RL, Genetic algorithm]** HUNTER- An Online Cloud Database Hybrid Tuning System for Personalized Requirements (SIGMOD,2022 ) [[paper](https://scholar.archive.org/work/mhkvbi2uwfdvfb2zhj73brzb6a/access/wayback/https://dl.acm.org/doi/pdf/10.1145/3514221.3517882)]


#### Experiments

An inquiry into machine learning-based automatic configuration tuning services on real-world database management systems (VLDB, 2021) [[paper](https://www.cs.cmu.edu/~./pavlo/papers/p1241-aken.pdf)]

Facilitating Database Tuning with Hyper-Parameter Optimization- A Comprehensive Experimental Evaluation (VLDB, 2021) [[paper](https://15799.courses.cs.cmu.edu/spring2022/papers/09-knobs4/zhang-techreport2021.pdf)]

#### Knob Selection

SARD: A statistical approach for ranking database tuning parameters (ICDEW, 2008) [[paper](https://www-users.cse.umn.edu/~mokbel/papers/SARD.pdf)]

Too Many Knobs to Tune? Towards Faster Database Tuning by Pre-selecting Important Knobs (HotStorage 2020) [[paper](https://www.usenix.org/system/files/hotstorage20_paper_kanellis.pdf)]

Peer-reviewed papers and codes at https://github.com/evolveDB/tuning-survey/blob/main/README.md



### View Advisor

A. Jindal, K. Karanasos, S. Rao, and H. Patel. Selecting subexpressions to materialize at datacenter scale. PVLDB, 11(7):800–812, 2018.[[paper](http://www.vldb.org/pvldb/vol11/p800-jindal.pdf)]

Ahmed, R., Bello, R., Witkowski, A., & Kumar, P. (2020). Automated generation of materialized views in Oracle. VLDB, 2020. [[paper](https://doi.org/10.14778/3415478.3415533)]

Yuan, H., Sun, J., & Li, G. (2020). *Automatic View Generation for Equivalent Subqueries with Deep Learning and Reinforcement Learning*. ICDE, 2020. [[paper](https://doi.org/10.1109/ICDE48307.2020.00133)]

Han, Y., Li, G., Yuan, H., & Sun, J. (n.d.). *An Autonomous Materialized View Management System with Deep Reinforcement Learning*. ICDE, 2021. [[paper](https://doi.org/10.1109/ICDE51399.2021.00217)]

Yue Han, Chengliang Chai, Jiabin Liu, Guoliang Li, Chuangxian Wei, Chaoqun Zhan. Dynamic Materialized View Management using Graph Neural Network. ICDE 2023. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/dynamic-view-icde23.pdf)]



### Index Advisor

**[Experimental Evaluation]** Jan Kossmann, Stefan Halfpap, Marcel Jankrift, Rainer Schlosser: *Magic mirror in my hand, which is the best in the land? An Experimental Evaluation of Index Selection Algorithms.* Proc. VLDB Endow. 13(11): 2382-2395 (2020) [[paper](http://www.vldb.org/pvldb/vol13/p2382-kossmann.pdf)]

**[Heuristic-based, AutoAdmin]** Surajit Chaudhuri, Vivek R. Narasayya: *An Efficient Cost-Driven Index Selection Tool for Microsoft SQL Server.* VLDB 1997: 146-155 [[paper](https://www.vldb.org/conf/1997/P146.PDF)]

**[Heuristic-based, DB2Advis]** Gary Valentin, Michael Zuliani, Daniel C. Zilio, Guy M. Lohman, Alan Skelley: *DB2 Advisor: An Optimizer Smart Enough to Recommend Its Own Indexes.* ICDE 2000: 101-110 [[paper](http://www.cs.toronto.edu/~alan/papers/icde00.pdf)]

**[Heuristic-based, Relaxation]** Nicolas Bruno, Surajit Chaudhuri: Automatic Physical Database Tuning: *A Relaxation-based Approach.* SIGMOD Conference 2005: 227-238 [[paper](https://dl.acm.org/doi/10.1145/1066157.1066184)]

**[Heuristic-based, COLT]** Karl Schnaitter, Serge Abiteboul, Tova Milo, Neoklis Polyzotis: *On-Line Index Selection for Shifting Workloads.* ICDE Workshops 2007: 459-468 [[paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.130.3168&rep=rep1&type=pdf)]

**[Heuristic-based, Extend]** Rainer Schlosser, Jan Kossmann, Martin Boissier: *Efficient Scalable Multi-attribute Index Selection Using Recursive Strategies.* ICDE 2019: 1238-1249 [[paper](http://ieeexplore.ieee.org/document/8731387)]

**[Learning-based, DQN]** Hai Lan, Zhifeng Bao, Yuwei Peng: *An Index Advisor Using Deep Reinforcement Learning.* CIKM 2020: 2105-2108 [[paper](https://doi.org/10.1145/3340531.3412106)]

**[Learning-based, DQN]** Zahra Sadri, Le Gruenwald, Eleazar Leal: *Online Index Selection Using Deep Reinforcement Learning for a Cluster Database.* ICDE Workshops 2020: 158-161 [[paper](https://doi.org/10.1109/ICDEW49219.2020.00035)]

**[Learning-based, DQN]** Gabriel Paludo Licks, Júlia Mara Colleoni Couto, Priscilla de Fátima Miehe, Renata De Paris, Duncan Dubugras A. Ruiz, Felipe Meneguzzi: *SmartIX: A Database Indexing Agent based on Reinforcement Learning.* Appl. Intell. 50(8): 2575-2588 (2020) [[paper](https://link.springer.com/article/10.1007/s10489-020-01674-8)]

**[Learning-based, DQN]** Vishal Sharma, Curtis E. Dyreson, Nicholas Flann: *MANTIS: Multiple Type and Attribute Index Selection using Deep Reinforcement Learning.* IDEAS 2021: 56-64 [[paper](https://dl.acm.org/doi/abs/10.1145/3472163.3472176)]

**[Learning-based, DQN]** Yu Yan, Shun Yao, Hongzhi Wang, Meng Gao: *Index selection for NoSQL database with deep reinforcement learning.* Inf. Sci. 561: 20-30 (2021) [[paper](https://www.sciencedirect.com/science/article/pii/S0020025521000049)]

**[Learning-based, DQN]** Vishal Sharma, Curtis E. Dyreson: *Indexer++: Workload-aware Online Index Tuning with Transformers and Reinforcement Learning.* SAC 2022: 372-380 [[paper](https://dl.acm.org/doi/10.1145/3477314.3507691)]

**[Learning-based, MAB]** R. Malinga Perera, Bastian Oetomo, Benjamin I. P. Rubinstein, Renata Borovica-Gajic: *DBA bandits: Self-driving index tuning under ad-hoc, analytical workloads with safety guarantees.* ICDE 2021: 600-611 [[paper](https://arxiv.org/pdf/2010.09208.pdf)]

**[Learning-based, MAB]** R. Malinga Perera, Bastian Oetomo, Benjamin I. P. Rubinstein, Renata Borovica-Gajic:
*HMAB: Self-Driving Hierarchy of Bandits for Integrated Physical Database Design Tuning.* Proc. VLDB Endow. 16(2): 216-229 (2022) [[paper](https://dl.acm.org/doi/abs/10.14778/3565816.3565824)]

**[Learning-based, MCTS]** Xuanhe Zhou, Luyang Liu, Wenbo Li, Lianyuan Jin, Shifu Li, Tianqing Wang, Jianhua Feng: *AutoIndex: An Incremental Index Management System for Dynamic Workloads.* ICDE 2022: 2196-2208 [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/icde2022-autoindex.pdf)]

**[Learning-based, MCTS]** Wentao Wu, Chi Wang, Tarique Siddiqui, Junxiong Wang, Vivek R. Narasayya, Surajit Chaudhuri, Philip A. Bernstein: *Budget-aware Index Tuning with Reinforcement Learning.* SIGMOD Conference 2022: 1528-1541 [[paper](https://www.microsoft.com/en-us/research/uploads/prod/2022/06/mcts-full.pdf)]

**[Optimization, Learned Cost]** Bailu Ding, Sudipto Das, Ryan Marcus, Wentao Wu, Surajit Chaudhuri, Vivek R. Narasayya: *AI Meets AI: Leveraging Query Executions to Improve Index Recommendations.* SIGMOD Conference 2019: 1241-1258 [[paper](https://doi.org/10.1145/3299869.3324957)]

**[Optimization, Learned Cost]** Jianling Gao, Nan Zhao, Ning Wang, Shuang Hao:
*SmartIndex: An Index Advisor with Learned Cost Estimator*. CIKM 2022: 4853-4856 [[paper](https://dl.acm.org/doi/abs/10.1145/3511808.3557163)]

**[Optimization, Workload Summarization]** Tarique Siddiqui, Saehan Jo, Wentao Wu, Chi Wang, Vivek R. Narasayya, Surajit Chaudhuri:
*ISUM: Efficiently Compressing Large and Complex Workloads for Scalable Index Tuning.* SIGMOD Conference 2022: 660-673 [[paper](https://dl.acm.org/doi/10.1145/3514221.3526152)]

**[Optimization, What-if Call]** Tarique Siddiqui, Wentao Wu, Vivek R. Narasayya, Surajit Chaudhuri:
*DISTILL: Low-Overhead Data-Driven Techniques for Filtering and Costing Indexes for Scalable Index Tuning.* Proc. VLDB Endow. 15(10): 2019-2031 (2022) [[paper](https://dl.acm.org/doi/abs/10.14778/3547305.3547309)]




### Partition Advisor

**[horizontal, DRL]** Benjamin Hilprecht, Carsten Binnig, Uwe Röhm. *Learning a Partitioning Advisor for Cloud Databases*. SIGMOD, 2020. [[paper](https://15799.courses.cs.cmu.edu/spring2022/papers/10-partitioning/hilprecht-sigmod2020.pdf)]

**[horizontal, DRL]** Benjamin Hilprecht, Carsten Binnig, Uwe Röhm. *Towards learning a partitioning advisor with deep reinforcement learning*. aiDM@SIGMOD, 2019. [[paper](https://doi.org/10.1145/3329859.3329876)]

**[horizontal, HybridAlgorithms]** 	Panos Parchas, Yonatan Naamad, Peter Van Bouwel, et al. *Fast and effective distribution-key recommendation for amazon redshift*. PVLDB, 2020. [[paper](https://doi.org/10.14778/3407790.3407834)]

**[horizontal, DataSkip]** Martin Boissier, Kurzynski Daniel. *Workload-driven horizontal partitioning and pruning for large HTAP systems*. ICDE Workshop, 2018. [[paper](https://doi.org/10.1109/ICDEW.2018.00026)]

**[horizontal, GraphPartition]** Carlo Curino, Yang Zhang, Evan P. C. Jones, Samuel Madden. *Schism: a Workload-Driven Approach to Database Replication and Partitioning*. PVLDB, 2010. [[paper](https://doi.org/10.14778/1920841.1920853)]

**[horizontal, Heuristic]** Jun Rao, Chun Zhang, Nimrod Megiddo, Guy M. Lohman. *Automating physical database design in a parallel database*. SIGMOD, 2002. [[paper](https://www.csd.uoc.gr/~hy460/pdf/p558-rao.pdf)]

**[vertical, DRL]** Campero Durand G, Piriyev R, Pinnecke M, et al. *Automated vertical partitioning with deep reinforcement learning*. ADBIS, 2019. [[paper](https://doi.org/10.1007/978-3-030-30278-8_16)]

**[co-partition]** Zamanian, E., Binnig, C., & Salama, A. (2015). *Locality-aware partitioning in parallel database systems*. SIGMOD. [[paper](https://doi.org/10.1145/2723372.2723718)]

**[co-partition]** Rabl, T., & Jacobsen, H. A. (2017). *Query centric partitioning and allocation for partially replicated database systems*. SIGMOD. [[paper](https://doi.org/10.1145/3035918.3064052)]

**[situ]** Olma, M., Karpathiotakis, M., Alagiannis, I., Athanassoulis, M., & Ailamaki, A. (2020). *Adaptive partitioning and indexing for in situ query processing*. VLDB Journal. [[paper](https://doi.org/10.1007/s00778-019-00580-x)]


## 2. Query Optimization

### Query Rewriter 

(note other interesting problems like text2SQL is not within the scope)

**[rewrite rules]** 	Béatrice Finance, Georges Gardarin. A Rule-Based Query Rewriter in an Extensible DBMS. ICDE 1991. [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=131472)]

**[rewrite rules]** 	Hamid Pirahesh, Joseph M. Hellerstein, Waqar Hasan. *Extensible/Rule Based Query Rewrite Optimization in Starburst*. SIGMOD Conference 1992. [[paper](https://sigmodrecord.org/publications/sigmodRecord/9206/pdfs/141484.130294.pdf)]

**[cost/heuristic rewrite]** Rafi Ahmed, Allison W. Lee, Andrew Witkowski, et al. *Cost-Based Query Transformation in Oracle*. VLDB 2006: 1026-1036. [[paper](https://www.researchgate.net/publication/221311318_Cost-Based_Query_Transformation_in_Oracle/link/572bbc5e08aef7c7e2c6b829/download)]

**[heuristic rewrite]** De Araújo, A. H. M., Monteiro, J. M., Antônio, J., De Macêdo, F., Tavares, J. A., Brayner, A., & Lifschitz, S. (2014). *ARe-SQL: An Online, Automatic and Non-Intrusive Approach for Rewriting SQL Queries*. JIDM, 2014. [[paper](https://www.researchgate.net/publication/264081912_ARE-SQL_AN_ONLINE_AUTOMATIC_AND_NON-INTRUSIVE_APPROACH_FOR_REWRITING_SQL_QUERIES)]

**[optimization engine]** Begoli, E., Camacho-Rodríguez, J., Hyde, J., Mior, M. J., & Lemire, D. (2018). *Apache calcite: A foundational framework for optimized query processing over heterogeneous data sources*. SIGMOD, 2018. [[paper](https://doi.org/10.1145/3183713.3190662)]

**[predicate rewrite]** Qi Zhou, Joy Arulraj, Shamkant B. Navathe, William Harris, Jinpeng Wu. *Sia : Optimizing Queries using Learned Predicates*. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3457262)]

**[rewrite strategy]** Xuanhe Zhou, Guoliang Li, Chengliang Chai, Jianhua Feng. *A Learned Query Rewrite System using Monte Carlo Tree Search*. VLDB, 2022. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb22-query-rewrite.pdf)]

**[rewrite rules]** 	Zhaoguo Wang, Zhou Zhou, Yicun Yang, Haoran Ding, Gansen Hu, Ding Ding, Chuzhe Tang, Haibo Chen, Jinyang Li. *WeTune: Automatic Discovery and Verification of Query Rewrite Rules*. SIGMOD Conference 2022: 94-107. [[paper](https://ipads.se.sjtu.edu.cn/_media/publications/wetune_final.pdf)]

**[map-reduce]** 	Partho Sarthi, Kaushik Rajan, Akash Lal, Abhishek Modi, et al. *Generalized Sub-Query Fusion for Eliminating Redundant I/O from Big-Data Queries. OSDI 2020: 209-224*.  [[paper](https://www.usenix.org/system/files/osdi20-sarthi_0.pdf)]

**[streaming]** Wentao Wu, Philip A. Bernstein, Alex Raizman, Christina Pavlopoulou. *Cost-based Query Rewriting Techniques for Optimizing Aggregates Over Correlated Windows*. CoRR abs/2008.12379 (2020)  [[paper](https://www.researchgate.net/profile/Wentao-Wu-2/publication/343986286_Cost-based_Query_Rewriting_Techniques_for_Optimizing_Aggregates_Over_Correlated_Windows/links/5f52ad2e299bf13a31a07101/Cost-based-Query-Rewriting-Techniques-for-Optimizing-Aggregates-Over-Correlated-Windows.pdf)]

**[equivalence]** 	Shumo Chu, Konstantin Weitz, Alvin Cheung, Dan Suciu. *HoTTSQL: proving query rewrites with univalent SQL semantics*. PLDI 2017: 510-524. [[paper](https://doi.org/10.1145/3062341.3062348)]


### Cost Estimation

**[Card, Query-based]** Xiao Hu, Yuxi Liu, Haibo Xiu, Pankaj K. Agarwal, Debmalya Panigrahi, Sudeepa Roy, Jun Yang. *Selectivity Functions of Range Queries are Learnable*. SIGMOD, 2022. [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3517896)]

**[Card, Query-based]** Kipf A, Kipf T, Radke B, et al. Learned cardinalities: Estimating correlated joins with deep learning. CIDR, 2019. [[paper](https://arxiv.org/pdf/1809.00677)]

**[Card, Query-based]** Woltmann L, Hartmann C, Thiele M, et al. Cardinality estimation with local deep learning models. aiDM, 2019. [[paper](https://doi.org/10.1145/3329859.3329875)]

**[Card, Query-based]** Tzoumas K, Deshpande A, Jensen C S. Lightweight graphical models for selectivity estimation without independence assumptions[J]. Proceedings of the VLDB Endowment, 4(11): 852-863, 2011. [[paper](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.228.675&rep=rep1&type=pdf)]

**[Card, Query-based]** Dutt, A., Wang, C., Nazi, A., Kandula, S., Narasayya, V., & Chaudhuri, S. (2018). Selectivity estimation for range predicates using lightweight models. Proceedings of the VLDB Endowment, 12(9), 1044–1057, 2018. [[paper](https://doi.org/10.14778/3329772.3329780)]

**[Card, Query-based]** Hayek, R., & Shmueli, O. (2020). *NN-based Transformation of Any SQL Cardinality Estimator for Handling DISTINCT, AND, OR and NOT*. arXiv， 2020. [[paper](http://arxiv.org/abs/2004.07009)]

**[Card, Data-based]** Lu Y, Kandula S, König A C, et al. Pre-training summarization models of structured datasets for cardinality estimation[J]. Proceedings of the VLDB Endowment, 2021. [[paper](https://dl.acm.org/doi/pdf/10.14778/3494124.3494127?casa_token=v6OMWXKyNM4AAAAA:gN2zqOt0DBvEt7AhW3e26aZSREvTaMWb6f64f9m_Vs4dLcs-18paOgLbX4Mzq1IlJ-ILFl2-nNZXdiI)] 

**[Card, Data-based]** Yang, Z., Liang, E., Kamsetty, A., Wu, C., Duan, Y., Chen, X., … Stoica, I. (2019). Deep Unsupervised Cardinality Estimation. VLDB, 2019. [[paper](https://doi.org/10.14778/3368289.3368294)]

**[Card, Data-based]** Yang, Z., Kamsetty, A., Luan, S., Liang, E., Duan, Y., Chen, X., & Stoica, I. (2020). Neurocard: One cardinality estimator for all tables. *Proceedings of the VLDB Endowment*, *14*(1), 61–73, 2020. [[paper](https://doi.org/10.14778/3421424.3421432)]

**[Card, Data-based]** Zhu R, Wu Z, Han Y, et al. FLAT: Fast, Lightweight and Accurate Method for Cardinality Estimation[J]. arXiv preprint arXiv:2011.09022, 2020. [[paper](https://arxiv.org/pdf/2011.09022)]

**[Card, Data-based]** Wu Z, Shaikhha A, Zhu R, et al. BayesCard: Revitilizing Bayesian Frameworks for Cardinality Estimation. arXiv preprint arXiv: 2012.14743, 2020. [[paper](https://arxiv.org/pdf/2012.14743)]

**[Card, Data-based]** Leis, V., Radke, B., Gubichev, A., Kemper, A., & Neumann, T. (2017). Cardinality estimation done right: Index-based join sampling. CIDR, 2017. [[paper](http://cidrdb.org/cidr2017/papers/p9-leis-cidr17.pdf)]

**[Card, Data-based]** Hilprecht, B., Schmidt, A., Kulessa, M., Molina, A., Kersting, K., & Binnig, C. (2020). DeepDB: Learn from data, not from queries! *Proceedings of the VLDB Endowment*, *13*(7), 992–1005, 2020. [[paper](https://doi.org/10.14778/3384345.3384349)]

**[Card, Data-based]** Zhu, R., Wu, Z., Han, Y., Zeng, K., Pfadler, A., Qian, Z., … Cui, B. (2020). FLAT: Fast, Lightweight and Accurate Method for Cardinality Estimation. VLDB, 2021. [[paper](http://arxiv.org/abs/2011.09022)]

**[Card, Data-based]** Hasan S, Thirumuruganathan S, Augustine J, et al. *Deep learning models for selectivity estimation of multi-attribute queries.* SIGMOD, 2020. [[paper](https://dl.acm.org/doi/pdf/10.1145/3318464.3389741)]

**[Card, Data-based]** Heimel M, Kiefer M, Markl V. Self-tuning, GPU-accelerated kernel density models for multidimensional selectivity estimation. Proceedings of the ACM SIGMOD, 2015. [[paper](https://dl.acm.org/doi/pdf/10.1145/2723372.2749438)]

**[Card, Data-based]** Yongjoo Park, Shucheng Zhong, and Barzan Mozafari. Quicksel: Quick selectivity learning with mixture models. SIGMOD 2020. [[paper](https://arxiv.org/pdf/1812.10568.pdf)]

**[Card, Data-based]** Jiayi Wang, Chengliang Chai, Jiabin Liu, Guoliang Li. FACE: A Normalizing Flow based Cardinality Estimator. VLDB 2022. [[paper](https://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb22-flow-card.pdf)]

**[Card, Data-based]** Yao Lu, Srikanth Kandula, Arnd Christian König, Surajit Chaudhuri. Pre-training summarization models of structured datasets for cardinality estimation. VLDB 2022. [[paper](https://www.vldb.org/pvldb/vol15/p414-lu.pdf)]


**[Card, Query&Data-based]** Wu P, Cong G. A Unified Deep Model of Learning from both Data and Queries for Cardinality Estimation[C]//Proceedings of the 2021 International Conference on Management of Data. 2021: 2009-2022. [[paper](https://arxiv.org/pdf/2107.12295)]

**[Card]** Parimarjan Negi, Ryan C. Marcus, Andreas Kipf, Hongzi Mao, Nesime Tatbul, Tim Kraska, Mohammad Alizadeh. Flow-Loss: Learning Cardinality Estimates That Matter. VLDB Endow, 14(11): 2019-2032, 2021. [[paper](http://www.vldb.org/pvldb/vol14/p2019-negi.pdf)] 

**[Cost]** Marcus, R., & Papaemmanouil, O. (2019). *Plan-Structured Deep Neural Network Models for Query Performance Prediction*. 1733–1746. [[paper](http://arxiv.org/abs/1902.00132)]

**[Cost]** Sun, J., & Li, G. (n.d.). *An End-to-End Learning-based Cost Estimator*. VLDB, 2020. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb2020-learnedcost.pdf)]

**[Cost]** Benjamin Hilprecht, Carsten Binnig. *Zero-Shot Cost Models for
Out-of-the-box Learned Cost Prediction*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p2361-hilprecht.pdf)]


**[ EA&B ]** Wang, X., Qu, C., Wu, W., Wang, J., & Zhou, Q. (2021). Are We Ready For Learned Cardinality Estimation?  Proc. VLDB Endow. 14(9): 1640-1654 (2021). [[paper](http://www.vldb.org/pvldb/vol14/p1640-wang.pdf)]

**[ EA&B ]** Sun, J., Zhang, J., Sun, Z., Li, G., & Tang, N. (n.d.). *Learned Cardinality Estimation : A Design Space Exploration and a Comparative Evaluation [ EA & B ]*. *14*(1). VLDB, 2022. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb22-card-exp.pdf)]

**[ EA&B ]** Yuxing Han, Ziniu Wu, Peizhi Wu, et al. Cardinality Estimation in DBMS: A Comprehensive Benchmark Evaluation Yuxing. VLDB, 2022. [[paper](https://arxiv.org/abs/2109.05877)] 

**[ EA&B ]** Harmouch, H., & Naumann, F. (2018). Cardinality Estimation: An Experimental Survey. *Pvldb*, *11*(4), 4999–512, 2017. [[paper](https://doi.org/10.1145/3164135.3164145)]

### Plan Optimization

**[Parallel MCTS]** Ziyun Wei, Immanuel Trummer. *SkinnerMT: Parallelizing for Efficiency and Robustness in Adaptive Query Processing on Multicore Platforms*. PVLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol16/p905-wei.pdf)]

**[OptimizedRL]** Zongheng Yang, Wei-Lin Chiang, Sifei Luan, Gautam Mittal, Michael Luo, Ion StoicaBalsa. *Learning a Query Optimizer Without Expert Demonstrations*. SIGMOD, 2022  [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3517885)].

Jan Kossmann. *Workload-driven, Lazy Discovery of Data Dependencies for Query Optimization*. CIDR, 2022 [[paper](https://www.cidrdb.org/cidr2022/papers/p70-kossmann.pdf)]

Ron Avnur, Joseph M. Hellerstein. Eddies: Continuously Adaptive Query Processing. SIGMOD, 2000. [[paper](https://dl.acm.org/doi/pdf/10.1145/342009.335420)]

Marcus, R., Negi, P., Mao, H., Zhang, C., Alizadeh, M., Kraska, T., … Tatbul, N. (2018). Neo: A Learned query optimizer. *Proceedings of the VLDB Endowment*, *12*(11), 1705–1718, 2018. [[paper](https://doi.org/10.14778/3342263.3342644)]

Marcus, R., & Papaemmanouil, O. (2018). Deep reinforcement learning for join order enumeration. *Proceedings of the 1st International Workshop on Exploiting Artificial Intelligence Techniques for Data Management, AiDM 2018*, 0–3. [[paper](https://doi.org/10.1145/3211954.3211957)]

Leis, V., Gubichev, A., Mirchev, A., Boncz, P., Kemper, A., & Neumann, T. (2016). How Good Are Query Optimizers, Really? *Proceedings of the VLDB Endowment*, *9*(3), 204–215. [[paper](https://doi.org/10.14778/2850583.2850594)]

Trummer, I., Wang, J., Maram, D., Moseley, S., Jo, S., & Antonakakis, J. (n.d.). SkinnerDB : Regret-Bounded Query Evaluation via Reinforcement Learning. SIGMOD, 2019. [[paper](https://arxiv.org/abs/1901.05152)]

Ding, M., Chen, S., & Manegold, S. (2021). *Progressive Join Algorithms Considering User Preference*. CIDR, 2021. [[paper](http://cidrdb.org/cidr2021/papers/cidr2021_paper02.pdf)]

Yu, X., Li, G., Tang, N. (n.d.). Reinforcement Learning with Tree-LSTM for Join Order Selection. ICDE, 2020. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/icde2020-learnedjoinorder.pdf)]

Chenggang Wu, Alekh Jindal, Saeed Amizadeh, Hiren Patel, Wangchao Le, Shi Qiao, Sriram Rao. Towards a Learning Optimizer for Shared Clouds. Proc. VLDB Endow. 12(3): 210-222, 2018. [[paper](http://www.vldb.org/pvldb/vol12/p210-wu.pdf)]


### Plan Hinter

Pasupuleti, K., Park, M., & Valluri, S. (n.d.). SQL Plan Observability through Hints in Oracle Autonomous Database.

Marcus, R., Negi, P., Mao, H., Tatbul, N., Alizadeh, M., & Kraska, T. (2020). Bao: Making Learned Query Optimization Practical. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3452838)]

Parimarjan Negi, Matteo Interlandi, Ryan Marcus, Mohammad Alizadeh, Tim Kraska, Marc Friedman, Alekh Jindal. Steering Query Optimizers: A Practical Take on Big Data Workloads. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3457568)]

## 3. Workload Scheduling

Ibrahim Sabek, Tenzin Samten Ukyab, Tim Kraska. *LSched: A Workload-Aware Learned Query Scheduler for Analytical Database Systems*. SIGMOD, 2022. [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3526158)] 

Chi Zhang, Ryan Marcus, and et al. Buffer Pool Aware Query Scheduling via Deep Reinforcement Learning. In VLDB, 2020. [[paper](https://arxiv.org/pdf/2007.10568.pdf)] 


## 4. Database Design

### Index and Layout

**[Data Container]** Madden S, Ding J, Kraska T, Sudhir S, Cohen D, Mattson T, Tatbul N. *Self-Organizing Data Containers*. CIDR, 2022. [[paper](https://www.cidrdb.org/cidr2022/papers/p44-madden.pdf)]

**[Learned Index, immutable]** Jiaoyi Zhang, Yihan Gao. *CARMI: A Cache-Aware Learned Index with a Cost-based
Construction Algorithm*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p2679-gao.pdf)]

**[Learned Index, immutable]** Shangyu Wu. *NFL: Robust Learned Index via Distribution Transformation*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p2188-wu.pdf)]

**[Learned Index, immutable]** Kraska, T., Beutel, A., Chi, E. H., Dean, J., & Polyzotis, N. (2018). The case for learned index structures. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, 489–504. [[paper](https://dl.acm.org/doi/10.1145/3183713.3196909)] [[code](https://github.com/learnedsystems/RMI/tree/5fdff45d0929beaccf6bc56f8f4c0d82baf10304)]

**[Learned Index, mutable]** Ding, J., Minhas, U. F., Yu, J., Wang, C., Do, J., Li, Y., Zhang, H., Chandramouli, B., Gehrke, J., Kossmann, D., Lomet, D., & Kraska, T. (2020). ALEX: An Updatable Adaptive Learned Index. *Proceedings of the 2020 ACM SIGMOD International Conference on Management of Data*, 969–984. [[paper]https://dl.acm.org/doi/10.1145/3318464.3389711] [[code](https://github.com/microsoft/ALEX)]

**[Learned Index, mutable]** Galakatos, A., Markovitch, M., Binnig, C., Fonseca, R., & Kraska, T. (2019). Fiting-tree: A data-aware index structure. *Proceedings of the 2019 International Conference on Management of Data*, 1189-1206. [[paper](https://dl.acm.org/doi/abs/10.1145/3299869.3319860)]

**[Learned Index, mutable]** Ferragina, P., & Vinciguerra, G. (2020). The PGM-index : a fully-dynamic compressed learned index with provable worst-case bounds. *The Proceedings of the VLDB Endowment (PVLDB)*, *13*(8), 1162–1175. [[paper](https://dl.acm.org/doi/abs/10.14778/3389133.3389135)]

**[Learned Index, mutable]** Hadian, A., & Heinis, T. (n.d.). MADEX : Learning-augmented Algorithmic Index Structures. *( Regular Papers )*. [[paper](http://www.hadian.org/files/papers/hadian2020madex.pdf)] [[slides](http://www.hadian.org/files/papers/hadian2020madex_slides.pdf)]


**[Learned Index, immutable, multi-d]** Nathan, V., Ding, J., Alizadeh, M., & Kraska, T. (2020). Learning multi-dimensional indexes. *Proceedings of the 2020 ACM SIGMOD International Conference on Management of Data*, 985-1000. [[paper](https://dl.acm.org/doi/10.1145/3318464.3380579)]

**[Learned Index, immutable, multi-d]** Ding, J., Nathan, V., Alizadeh, M., & Kraska, T. (2020). Tsunami: A learned multi-dimensional index for correlated data and skewed workloads. *Proceedings of the VLDB Endowment*, *14*(2), 74-86. [[paper](https://dl.acm.org/doi/abs/10.14778/3425879.3425880)]

**[Learned Index, immutable, multi-d]** Wu, J., Zhang, Y., Chen, S., Wang, J., Chen, Y., & Xing, C. (2021). Updatable Learned Index with Precise Positions. *Proceedings of the VLDB Endowment*, *14*(8), 1276-1288. [[paper](https://arxiv.org/abs/2104.05520)]

**[Learned Index, mutable, multi-d, non-memory]** Li, P., Lu, H., Zheng, Q., Yang, L., & Pan, G. (2020). LISA: A Learned Index Structure for Spatial Data. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, 2119–2133. [[paper](https://doi.org/10.1145/3318464.3389703)]

**[Learned Index, immutable, auto-generated]** Dittrich, J., Nix, J., & Schön, C. (2021). The next 50 years in database indexing or. *The Proceedings of the VLDB Endowment (PVLDB)*, *15*(3), 527–540. [[paper](https://doi.org/10.14778/3494124.3494136)] [[code](https://github.com/BigDataAnalyticsGroup/GENE)]

**[Learned Index, mutable, non-memory]** Lu, B., Ding, J., Lo, E., Minhas, U. F., & Wang, T. (2021). *APEX: A High-Performance Learned Index on Persistent Memory. Proceedings of the VLDB Endowment*, *15*(3), 597–610. [[paper](https://doi.org/10.14778/3494124.3494141)]

**[Learned Index, mutable, concurrency]** Wang, Z., Chen, H., Wang, Y., & Tang, C. (2022). The Concurrent Learned Indexes for Multicore Data Storage. *ACM Transactions on Storage*, *18*(1), 1-35. [[paper](https://dl.acm.org/doi/pdf/10.1145/3478289)] [[code](https://ipads.se.sjtu.edu.cn:1312/opensource/xindex.git)]

**[Learned Index, benchmark]** Anders Hammershøj Jensen, Frederik Lauridsen, Fatemeh Zardbani, Stratos Idreos, Panagiotis Karras. Revisiting Multidimensional Adaptive Indexing [Experiment & Analysis]. EDBT 2021: 469-474. [[paper](https://cs.au.dk/~karras/p46.pdf)] 

**[Learned Index, benchmark]** Marcus, R., Stoian, M., Kipf, A., Misra, S., van Renen, A., Kemper, A., Neumann, T., & Kraska, T. (2020). Benchmarking learned indexes. *The Proceedings of the VLDB Endowment (PVLDB)*, *14*(1), 1–13. [[paper](https://dl.acm.org/doi/10.14778/3421424.3421425)] [[code](https://github.com/learnedsystems/SOSD)]


**[Learned Layout]** Teng Zhang, Jian Tan, Xin Cai, Jianying Wang, Feifei Li, Jianling Sun. *SA-LSM : Optimize Data Layout for LSM-tree Based Storage using Survival Analysis*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p2161-zhang.pdf)]

**[Learned Layout]** Michael Abebe. *Tiresias: Enabling Predictive Autonomous Storate and Indexing*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p3126-abebe.pdf)]

**[Learned Layout]** Jialin Ding, Umar Farooq Minhas, Badrish Chandramouli, et al. *Instance-Optimized Data Layouts for Cloud Analytics Workloads*. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3457270)]

**[Learned Layout]** Yang, Z., Chandramouli, B., Wang, C., Gehrke, J., Li, Y., Minhas, U. F., … Acharya, R. (n.d.). *Qd-tree: Learning Data Layouts for Big Data Analytics*. SIGMOD, 2020. [[paper](https://doi.org/10.1145/3183713.3196909)]

**[Learned Layout]** Liwen Sun, Michael J. Franklin, Sanjay Krishnan, et al. *Fine-grained partitioning for aggressive data skipping*. SIGMOD, 2014. [[paper](https://doi.org/10.1145/2588555.2610515)]

**[Learned Layout]** Bandle, M., Giceva, J., & Neumann, T. (2021). To Partition, or Not to Partition, That is the Join Question in a Real System. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3452831)]

### Query Execution

**[CodeGen]** Immanuel Trummer. CodexDB: Synthesizing Code for Qery Processing from Natural Language Instructions using GPT-3 Codex. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p2921-trummer.pdf)]

Zhang, C., Marcus, R., Kleiman, A., & Papaemmanouil, O. (2020). Buffer Pool Aware Query Scheduling via Deep Reinforcement Learning. AIDB@VLDB, 2020. [[paper](https://arxiv.org/abs/2007.10568)]


## 5. Database Monitoring

**[Trend Prediction]** L. Ma, D. V. Aken, A. Hefny, G. Mezerhane, A. Pavlo, and G. J. Gordon, “Query-based Workload Forecasting for Self-driving Database Management Systems,” in SIGMOD, 2018. [[paper](https://www.pdl.cmu.edu/PDL-FTP/Database/sigmod18-ma.pdf)]

**[Performance Prediction]** Dorn, J., Apel, S., & Siegmund, N. (n.d.). *Mastering Uncertainty in Performance Estimations of Configurable Software Systems*. (3).

**[Performance Prediction]** Marcus, R., & Papaemmanouil, O. (2019). Plan-structured deep neural network models for query performance prediction. *Proceedings of the VLDB Endowment*, *12*(11), 1733–1746. [[paper](https://doi.org/10.14778/3342263.3342646)]

**[Performance Prediction]** Wu, W., Chi, Y., Hacig̈um̈uş, H., & Naughton, J. F. (2013). Towards predicting query execution time for concurrent and dynamic database workloads. *Proceedings of the VLDB Endowment*, *6*(10), 925–936. [[paper](https://doi.org/10.14778/2536206.2536219)]

**[Performance Prediction]** Duggan, J., Papaemmanouil, O., Cetintemel, U., & Upfal, E. (2014). Contender: A resource modeling approach for concurrent query performance prediction. *Advances in Database Technology - EDBT 2014: 17th International Conference on Extending Database Technology, Proceedings*, 109–120. [[paper](https://doi.org/10.5441/002/edbt.2014.11)]

**[Performance Prediction]** Wu, W., Chi, Y., Zhu, S., Tatemura, J., Hacigümüş, H., & Naughton, J. F. (2013). Predicting query execution time: Are optimizer cost models really unusable? *Proceedings - International Conference on Data Engineering*, (1), 1081–1092. [[paper](https://doi.org/10.1109/ICDE.2013.6544899)]

**[Performance Prediction]** Higginson, A. S., Dediu, M., Arsene, O., Paton, N. W., & Embury, S. M. (2020). Database Workload Capacity Planning using Time Series Analysis and Machine Learning. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, 769–783. [[paper](https://doi.org/10.1145/3318464.3386140)]

**[Performance Prediction]** Unterbrunner, P., Giannikis, G., Alonso, G., Fauser, D., & Kossmann, D. (2009). Predictable performance for unpredictable workloads. *Proceedings of the VLDB Endowment*, *2*(1), 706–717. [[paper](https://doi.org/10.14778/1687627.1687707)]

**[Performance Prediction]** Xuanhe Zhou, Ji Sun, Guoliang Li, Jianhua Feng. Query Performance Prediction for Concurrent Queries using Graph Embedding. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb2020-concurrent.pdf)]



## 6. Database Diagnosis

### System Diagnosis

Yoon, D. Y., Niu, N., & Mozafari, B. (2016). DBSherlock: A performance diagnostic tool for transactional databases. *Proceedings of the ACM SIGMOD International Conference on Management of Data*, *26*-*June*-*20*(i), 1599–1614. [[paper](https://web.eecs.umich.edu/~mozafari/php/data/uploads/sigmod_2016.pdf)]

Kalmegh, P., Babu, S., & Roy, S. (2019). iQCAR: inter-Query Contention Analyzer for Data Analytics Frameworks. SIGMOD. [[paper](https://dl.acm.org/doi/10.1145/3299869.3319904)]

Ma, M., Yin, Z., Zhang, S., Wang, S., Zheng, C., & Jiang, X. (2020). Diagnosing Root Causes of Intermittent Slow Queries in Cloud Databases. *PVLDB Endowment.* [[paper](http://www.vldb.org/pvldb/vol13/p1176-ma.pdf)]

### Query Diagnosis

Xiaoze Liu, Zheng Yin, Chao Zhao, et al. PinSQL: Pinpoint Root Cause SQLs to Resolve Performance Issues in Cloud Databases. ICDE 2022. [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9835371)]

## 7. Training Data Generation

### Query Generation

L.Zhang, C.Chai, X.Zhou, and G.Li. Learned sqlgen: Constraint-aware sql generation using reinforcement learning. In SIGMOD, 2022. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/sigmod2022-sqlgen.pdf)]

Liu X, Kong X, Liu L, et al. TreeGAN: syntax-aware sequence generation with generative adversarial networks. In ICDM, 2018. [[paper](http://cn.liuleics.com/uploads/1/4/1/2/14126273/1808.07582.pdf)]

### Data Generation

**[DeepAR]** Jingyi Yang, Peizhi Wu, Gao Cong, Tieying Zhang, Xiao He. *SAM: Database Generation from Query Workloads with Supervised Autoregressive Models*. SIGMOD, 2022. [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3526168)]

Francesco Ventura, Zoi Kaoudi, Jorge-Arnulfo Quiané-Ruiz, Volker Markl. Expand your training limits! Generating training data for ML-based data management. SIGMOD, 2021 [[paper](https://dl.acm.org/doi/pdf/10.1145/3448016.3457286)]

Ju Fan, Tongyu Liu, Guoliang Li, Yuwei Shen, Xiaoyong Du. Relational Data Synthesis using Generative Adversarial Networks: A Design Space Exploration. VLDB 2020. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb2020-datagan.pdf)]

## 8. AI Techniques

### Feature Encoding

**[PlanEncoding]** Yue Zhao, Gao Cong, Jiachen Shi, Chunyan Miao. *QueryFormer: A Tree Transformer Model for Query Plan Representation*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p1658-zhao.pdf)]

**[Plan2Feature]** Debjyoti Paul, Jie Cao, Feifei Li, Vivek Srikumar. *Database Workload Characterization with Query Plan Encoders*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p923-paul.pdf)]

**[WorkloadAsGraph]** Sanjay Agrawal, Eric Chu, Vivek R. Narasayya. Automatic physical design tuning: workload as a sequence. SIGMOD, 2006. [[paper](https://doi.org/10.1145/1142473.1142549)]

**[DataSummary]** Brit Youngmann et al. *Guided Exploration of Data Summaries*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p1798-youngmann.pdf)]

Jiang H, Liu C, Paparrizos J, et al. Good to the Last Bit: Data-Driven Encoding with CodecDB. SIGMOD 2021. [[paper](https://dl.acm.org/doi/pdf/10.1145/3448016.3457283?casa_token=NVcav-WiJuwAAAAA:iYwHvshbC43qeBpObX4d7UYndrtqsfgE2FkI2Pkx43r59YCZJjsvm1C0Qv-M_oESKhZicbJLTIi0WsI)] 


### Model Transfer

Meghdad Kurmanji, Peter Triantafillou. Detect, Distill and Update: Learned DB Systems Facing Out of Distribution Data. SIGMOD, 2022. [[paper](https://arxiv.org/pdf/2210.05508.pdf)]

## 9. Database Frameworks

**[MLTrain]** Lim WS, Butrovich M, Zhang W, Crotty A, Ma L, Xu P, Gehrke J, Pavlo A. *Database Gyms*. CIDR, 2023. [[paper](https://www.cidrdb.org/cidr2023/papers/p27-lim.pdf.)]

**[AcademicDB]** Immanuel L Haffner, Jens Dittrich. *mutable: A Modern DBMS for Research and Fast Prototyping*. CIDR, 2023. [[paper](https://www.cidrdb.org/cidr2023/papers/p41-haffner.pdf.)]

**[ModelValid]** Remmelt Ammerlaan, Gilbert Antonius, Marc Friedman, et al. *PerfGuard: Deploying ML-for-Systems without Performance Regressions, Almost!*. VLDB, 2022. [[[paper](https://vldb.org/pvldb/vol14/p3362-hossain.pdf)]

**[Transferable]** Ziniu Wu, et al. *A Unified Transferable Model for ML-Enhanced DBMS*. CIDR, 2022. [[paper](https://www.cidrdb.org/cidr2022/papers/p6-wu.pdf.)]

**[Transferable]** Benjamin Hilprecht, Carsten Binnig. *One Model to Rule them All: Towards Zero-Shot Learning for Databases*. CIDR, 2022. [[paper](https://www.cidrdb.org/cidr2022/papers/p16-hilprecht.pdf.)]

**[AutoDB]** Pavlo, A., Angulo, G., Arulraj, J., Lin, H., Lin, J., Ma, L., … Zhang, T. (2017). Self-Driving Database Management Systems. CIDR, 2017. [[paper](https://www.pdl.cmu.edu/PDL-FTP/Database/p42-pavlo-cidr17.pdf)]

**[AutoDB]** Li, F. (2018). Cloud native database systems at Alibaba: Opportunities and challenges. *Proceedings of the VLDB Endowment*, 2018. [[paper](https://doi.org/10.14778/3352063.3352141)]

**[AutoDB]** Kraska, T., Alizadeh, M., Beutel, A., Chi, E. H., Ding, J., Kristo, A., … Nathan, V. (2019). SageDB: A learned database system. CIDR, 2019. [[paper](http://www.alexbeutel.com/papers/CIDR2019_SageDB.pdf)]

**[AutoDB]** Li, G., Zhou, X., Li, S. (2019). *XuanYuan: An AI-Native Database*. Data Eng., 2019. [[paper](http://sites.computer.org/debull/A19june/p70.pdf)]

**[AutoDB]** Hilprecht, B., Bang, T., El-Hindi, M., Hättasch, B., Khanna, A., Rehrmann, R., … Binnig, C. (2020). DBMS Fitting: Why should we learn what we already know? Cidr, 2020. [[paper](http://cidrdb.org/cidr2020/papers/p34-hilprecht-cidr20.pdf)]

**[AutoDB]** Ma, L., Zhang, W., Jiao, J., Wang, W., Butrovich, M., Lim, W. S., … Pavlo, A. (2021). *MB2 : Decomposed Behavior Modeling for Self-Driving Database Management Systems*. SIGMOD, 2021. [[paper](https://dl.acm.org/doi/10.1145/3448016.3457276)]

**[AutoDB]** Guoliang Li, Xuanhe Zhou, , Ji Sun, Xiang Yu, Yue Han, Lianyuan Jin, Wenbo Li, Tianqing Wang, Shifu Li. openGauss: An Autonomous Database System. VLDB, 2021. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb21-opengauss.pdf)]


**[NLP]** James Thorne, Majid Yazdani, Marzieh Saeidi, Fabrizio Silvestri, Sebastian Riedel, Alon Y. Levy. From Natural Language Processing to Neural Databases. VLDB, 2021. [[paper](http://www.vldb.org/pvldb/vol14/p1033-thorne.pdf)]

**[Embedding]** Raasveldt, M.. *MonetDBLite: An embedded analytical database*. SIGMOD, 2018. [[paper](https://arxiv.org/pdf/1805.08520.pdf#:~:text=MonetDBLite%20is%20an%20in%2Dprocess,%2C%20R%2C%20Python%20and%20Java.)]


## 10. Demonstrations

**[DB Tuning]** Immanuel Trummer. *Demonstrating DB-BERT: A Database Tuning Tool that "Reads" the Manual*. SIGMOD, 2022. [[paper](https://arxiv.org/pdf/2112.10925.pdf)]

**[DB Tuning]** Luming Sun, Tao Ji, Cuiping Li, Hong Chen. *DeepO: A Learned Query Optimizer*. SIGMOD, 2022. [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3520167)]

**[DB Tuning]** Junxiong Wang, Immanuel Trummer, Debabrota Basu. *Demonstrating UDO: A Unified Approach for Optimizing Transaction Code, Physical Design, and System Parameters via Reinforcement Learning*. SIGMOD, 2021. [[paper](https://dl.acm.org/doi/abs/10.1145/3448016.3452754)]

**[O&M Platform]** Xuanhe Zhou, Lianyuan Jin, Ji Sun, Xinyang Zhao, Xiang Yu, Shifu Li, Tianqing Wang, Kun Li, luyang liu. *DBMind: A Self-Driving Platform in openGauss*. VLDB, 2021. [[paper](http://vldb.org/pvldb/vol14/p2743-zhou.pdf)] [[website](https://www.dbmind.cn/)] 


**[DB Tuning]** Bohan Zhang, Dana Van Aken, Justin Wang, Tao Dai, Shuli Jiang, Jacky Lao, Siyuan Sheng, Andrew Pavlo, Geoffrey J. Gordon. *A Demonstration of the ottertune automatic database management system tuning service*. VLDB, 2018. [[paper](http://www.vldb.org/pvldb/vol11/p1910-zhang.pdf)]


## 11. Talks

**[AutoDB]** 	Andy Pavlo, Matthew Butrovich, Lin Ma, Prashanth Menon, Wan Shen Lim, Dana Van Aken, William Zhang. *Make Your Database System Dream of Electric Sheep : Towards Self-Driving Operation*. VLDB, 2021. [[paper](https://vldb.org/pvldb/vol14/p3211-pavlo.pdf)]

**[AutoDB]** Tim Kraska. *Towards instance-optimized data systems*. VLDB, 2021. [[paper](http://vldb.org/pvldb/vol14/p3222-kraska.pdf)]

**[AutoDB]** Guoliang Li. *AI-Native Database*. VLDB, 2021.
