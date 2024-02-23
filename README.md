
## Researches and Practices in Autonomous Databases

<p align="center">
    【English | <a href="README-Chinese.md">中文</a>】
</p>


Continuously update the *autonomous database works* based on our past tutorials.

Kindly let us know if we have missed any great papers. Thank you!

Conference deadlines: https://github.com/ccfddl/ccf-deadlines

(Note *conference postponement* may not be promptly synchronized, so just consider it as a reference.)

Table of Contents
=================

* [0. Survey and Tutorial (16)](#0-survey-and-tutorial)
* [1. Database Configuration](#1-database-configuration)
    * [1.1 Knob Tuner (21)](#knob-tuner)
    * [1.2 View Advisor (9)](#view-advisor)
    * [1.3 Index Advisor (23)](#index-advisor)
    * [1.4 Partition Advisor (11)](#partition-advisor)
    * [1.5 Hybrid Advisor (2)](#hybrid-advisor)
* [2. Query Optimization](#2-query-optimization)
    * [2.1 Query Rewriter (13)](#query-rewriter)
    * [2.2 Cardinality Estimation (34)](#cardinality-estimation)
    * [2.3 Cost Estimation (3)](#cost-estimation)
    * [2.4 Plan Optimization (22)](#plan-optimization)
* [3. Workload Scheduling (2)](#3-workload-scheduling)
* [4. Database Design](#4-database-design)
    * [4.1 Learned Index (30)](#index)
    * [4.2 Learned Layout (6)](#layout)
    * [4.3 Query Execution (3)](#query-execution)
* [5. Database Monitoring (9)](#5-database-monitoring)
* [6. Database Diagnosis](#6-database-diagnosis)
    * [6.1 System Diagnosis (7)](#system-and-kernel-causes)
    * [6.2 Query Diagnosis (1)](#bottleneck-queries)
* [7. General Techniques](#7-general-techniques)
    * [7.1 Feature Engineering for DB (6)](#feature-engineering-for-db)
    * [7.2 Feature Engineering for AI (6)](#feature-engineering-for-ai)
    * [7.3 Model Transfer (1)](#model-transfer) 
    * [7.4 Query And Data Generation (5)](#query-and-data-generation)
* [8. Database Frameworks (16)](#8-database-frameworks)
* [9. Demonstrations (13)](#9-demonstrations)
* [S1. LLM x DB (32)](#s1-large-language-models-meet-database)
* [S2. AI Resources (5)](#s2-ai-paper-and-code-list)
* [S3. Data And SQLs (3)](#s3-open-datasets-and-sqls)


---
*Great talks you should not miss >>*

***Make Your Database System Dream of Electric Sheep : Towards Self-Driving Operation.*** Andy Pavlo, Matthew Butrovich, Lin Ma, et al. [[link](https://vldb.org/pvldb/vol14/p3211-pavlo.pdf)]


***Towards instance-optimized data systems.*** Tim Kraska. [[link](http://vldb.org/pvldb/vol14/p3222-kraska.pdf)]


***AI-Native Database.*** Guoliang Li. [[link](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/aidb-slides.pdf)]

***From BERT to GPT-3 Codex: Harnessing the Potential of Very Large Language Models for Data Management.*** Immanuel Trummer. [[link](https://drive.google.com/file/d/1U-2j8oi5au3nuYwPIlhnno7c6UNDfifl/view)]


***Retrieval-based Language Models and Applications.*** Akari Asai,	Sewon Min,	Zexuan Zhong,	Danqi Chen. [[link](https://acl2023-retrieval-lm.github.io/)]

---

## 0. Survey and Tutorial

### Survey

**Database meets deep learning: Challenges and opportunities.** ![](https://img.shields.io/badge/-ai4db-Informational)

*Wei Wang, Meihui Zhang, Gang Chen, et al.  SIGMOD Record, 2016.* [[paper](https://doi.org/10.1145/3003665.3003669)]


**Database Meets Artificial Intelligence: A Survey.** ![](https://img.shields.io/badge/-ai4db-Informational) ![](https://img.shields.io/badge/-db4ai-informational)

*Xuanhe Zhou, Chengliang Chai, Guoliang Li, et al. TKDE, 2020.* [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/aidb.pdf)]

**A Survey on Advancing the DBMS Query Optimizer: Cardinality Estimation, Cost Model, and Plan Enumeration.** ![](https://img.shields.io/badge/-learned_optimizer-orange)

*Hai Lan, Zhifeng Bao, Yuwei Peng. Data Science and Engineering, 2021.* [[paper](https://link.springer.com/article/10.1007/s41019-020-00149-7)]

**A Survey on Deep Reinforcement Learning for Data Processing and Analytics.** ![](https://img.shields.io/badge/-rl4db-Informational)

*Qingpeng Cai, Can Cui, Yiyuan Xiong, et al. TKDE, 2022.* [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9723570)]


**Self-Driving Database Papers (CMU Spring Course)**. 2022. ![](https://img.shields.io/badge/-ai4db-Informational)

https://15799.courses.cs.cmu.edu/spring2022/schedule.html


**Automatic Database Knob Tuning: A Survey.** ![](https://img.shields.io/badge/-learned_knob_tuning-brown)

*Xinyang Zhao, Xuanhe Zhou, Guoliang Li. TKDE, 2023.* [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/tuning-survey.pdf)] [[code](https://github.com/evolveDB/tuning-survey)]


### Tutorial

**From auto-tuning one size fits all to self-designed and learned data-intensive systems.** ![](https://img.shields.io/badge/-ai4db-Informational)

*Stratos Idreos, Tim Kraska. SIGMOD, 2019.*  [[paper](https://doi.org/10.1145/3299869.3314034)]


**Speedup Your Analytics: Automatic Parameter Tuning for Databases and Big Data Systems.** ![](https://img.shields.io/badge/-learned_tuning-brown)

*Jiaheng Lu, Yuxing Chen, Herodotos Herodotou, Shivnath Babu. VLDB, 2019.*  [[paper](http://www.vldb.org/pvldb/vol12/p1970-lu.pdf)] [[slides](https://pdfs.semanticscholar.org/a784/25f87ec066c51043380f93502950e044cca3.pdf)]


**Tutorial: Adaptive Replication and Partitioning in Data Systems.** ![](https://img.shields.io/badge/-auto_db_cluster-Informational)

*Brad Glasbergen, Michael Abebe, Khuzaima Daudjee. Middleware, 2018.*  [[paper](https://cs.uwaterloo.ca/~kdaudjee/AdaptiveTutorial.pdf)]


**A Tutorial on Learned Multi-dimensional Indexes.** ![](https://img.shields.io/badge/-learned_index-black)

*Abdullah Al-Mamun, Hao Wu, Walid G. Aref. SIGSPATIAL, 2020.*  [[paper](https://dl.acm.org/doi/10.1145/3397536.3426358)]


**AI Meets Database: AI4DB and DB4AI.** ![](https://img.shields.io/badge/-ai4db-Informational) ![](https://img.shields.io/badge/-db4ai-informational)

*Guoliang Li, Xuanhe Zhou, Lei Cao. SIGMOD, 2021.*  [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/sigmod21-tutorial-paper.pdf)] [[slides](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/sigmod21-tutorial-slides.pdf)]


**Machine Learning for Databases.** ![](https://img.shields.io/badge/-ai4db-Informational)

*Guoliang Li, Xuanhe Zhou, Lei Cao. VLDB, 2021.*  [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb21-tutorial-paper.pdf)][[slides](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb21-tutorial-slides.pdf)]


**Machine Learning for Cloud Data Systems: the Promise, the Progress, and the Path Forward.** ![](https://img.shields.io/badge/-learned_cloud_db-Informational)

*Alekh Jindal, Matteo Interlandi. VLDB, 2021.*  [[paper](http://vldb.org/pvldb/vol14/p3202-jindal.pdf)]


**Workload-Aware Performance Tuning for Autonomous DBMSs.** ![](https://img.shields.io/badge/-learned_tuning-brown)

*Zhengtong Yan, Jiaheng Lu, Naresh Chainani, et al. ICDE, 2021.*  [[paper](https://www2.helsinki.fi/sites/default/files/atoms/files/icde_2021_tutorial_latest.pdf)]


**Learned Query Optimizer: At the Forefront of AI-Driven Databases.** ![](https://img.shields.io/badge/-learned_optimizer-orange)

*Zhu, Rong, Ziniu Wu, Chengliang Chai, et al. EDBT, 2022.*  [[paper](https://openproceedings.org/2022/conf/edbt/tutorial-1.pdf)]


**From BERT to GPT-3 Codex: Harnessing the Potential of Very Large Language Models for Data Management.** ![](https://img.shields.io/badge/-llm4db-Informational)

*Immanuel Trummer. VLDB, 2022.*  [[paper](https://dl.acm.org/doi/pdf/10.14778/3554821.3554896)]


## 1. Database Configuration

### Knob Tuner

#### Heuristic 

PGTune: https://pgtune.leopard.in.ua. ![](https://img.shields.io/badge/-rule-green) 

**OpenTuner: An Extensible Framework for Program Autotuning** ![](https://img.shields.io/badge/-search-yellowgreen)   

*Ansel J, Kamil S, Veeramachaneni K, et al. PACT, 2014.* [[paper](https://dl.acm.org/doi/pdf/10.1145/2628071.2628092)] 

**BestConfig: Tapping the Performance Potential of Systems via Automatic Configuration Tuning** ![](https://img.shields.io/badge/-search-yellowgreen)  

*Zhu Y, Liu J, Guo M, et al. SoCC, 2017.* [[paper](https://dl.acm.org/doi/abs/10.1145/3127479.3128605)]

**BestConfig: Tapping the Performance Potential of Systems via Automatic Configuration Tuning** ![](https://img.shields.io/badge/-search-yellowgreen)  

*Zhu Y, Liu J, Guo M, et al. SoCC, 2017.* [[paper](https://dl.acm.org/doi/abs/10.1145/3127479.3128605)]

**An Efficient Transfer Learning Based Configuration Adviser for Database Tuning** ![](https://img.shields.io/badge/-knob_ranking-yellowgreen) ![](https://img.shields.io/badge/-search_space_transferring-8cfff3)

*Xinyi Zhang, Hong Wu, Yang Li, et al. VLDB, 2023.* [[paper](https://www.vldb.org/pvldb/vol17/p539-zhang.pdf)]

---

#### BO-based

**Tuning Database Conﬁguration Parameters with iTuned** ![](https://img.shields.io/badge/-gaussian_process-orange)    

*Duan, S., Thummala, V., & Babu, S. VLDB, 2009.* [[paper](https://users.cs.duke.edu/~shivnath/ituned/paper.pdf)]

**Automatic database management system tuning through large-scale machine learning** ![](https://img.shields.io/badge/-gaussian_process-orange)  

*Van Aken D, Pavlo A, Gordon G J, et al. SIGMOD, 2017.* [[paper](https://dl.acm.org/doi/pdf/10.1145/3035918.3064029)]

**Black or White? How to Develop an AutoTuner for Memory-based Analytics** ![](https://img.shields.io/badge/-gaussian_process-orange) ![](https://img.shields.io/badge/-Featurization-9cf)   

*Kunjir M, Babu S. SIGMOD, 2020.* [[paper](https://dl.acm.org/doi/pdf/10.1145/3318464.3380591)]

**ResTune: Resource Oriented Tuning Boosted by Meta-Learning for Cloud Databases** ![](https://img.shields.io/badge/-gaussian_process-orange) ![](https://img.shields.io/badge/-Model_Transferring-8cfff3)

*Zhang X, Wu H, Chang Z, et al. SIGMOD, 2021.* [[paper](https://15799.courses.cs.cmu.edu/spring2022/papers/08-knobs3/zhang-sigmod2021.pdf)]

**CGPTuner: a Contextual Gaussian Process Bandit Approach for the Automatic Tuning of IT Configurations Under Varying Workload Conditions** ![](https://img.shields.io/badge/-contextual_gaussian_process-orange)   

*Cereda S, Valladares S, Cremonesi P, et al. VLDB, 2021.* [[paper](https://www.cl.cam.ac.uk/~ey204/teaching/ACS/R244_2021_2022/papers/CGPTUNER_VLDB_2021.pdf)]

**Towards Dynamic and Safe Configuration Tuning for Cloud Databases** ![](https://img.shields.io/badge/-bounded_gaussian_process-orange)  

*Zhang X, Wu H, Li Y, et al. SIGMOD, 2022.* [[paper](https://arxiv.org/pdf/2203.14473)]

**LlamaTune: Sample-Efficient DBMS Configuration Tuning** ![](https://img.shields.io/badge/-gaussian_process-orange)  

*Kanellis K, Ding C, Kroth B, et al. VLDB, 2022.* [[paper](https://arxiv.org/pdf/2203.05128)]

---

#### DL-based

**iBTune: Individualized Buffer Tuning for Large-scale Cloud Databases**

*Jian Tan, Tieying Zhang, Feifei Li, et al. VLDB, 2019.* [[paper](http://www.vldb.org/pvldb/vol12/p1221-tan.pdf)]

---

#### RL-based

**An End-to-End Automatic Cloud Database Tuning System Using Deep Reinforcement Learning** 

*Ji Zhang, Yu Liu, Ke Zhou, Guoliang Li, et al. SIGMOD, 2019.* [[paper](https://dl.acm.org/doi/abs/10.1145/3299869.3300085)]

**QTune: A Query-Aware Database Tuning System with Deep Reinforcement Learning** ![](https://img.shields.io/badge/-query_encoding-blue)  

*Li G, Zhou X, Li S, et al. VLDB, 2019.* [[paper](https://15799.courses.cs.cmu.edu/spring2022/papers/08-knobs3/p2118-li.pdf)]

**Watuning: A workload-aware tuning system with attention-based deep reinforcement learning** ![](https://img.shields.io/badge/-pre_trained-grey)

*Ge J K, Chai Y F, Chai Y P.  JCST, 2021.* [[paper](https://link.springer.com/article/10.1007/s11390-021-1350-8)]

**The Case for NLP-Enhanced Database Tuning: Towards Tuning Tools that "Read the Manual"** ![](https://img.shields.io/badge/-llm-f5f5dc)  

*Trummer I. VLDB, 2021.* [[paper](http://vldb.org/pvldb/vol14/p1159-trummer.pdf)]

**DB-BERT: a Database Tuning Tool that “Reads the Manual”** ![](https://img.shields.io/badge/-llm-f5f5dc)  

*Trummer I. SIGMOD, 2022.* [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3517843)]

**HUNTER- An Online Cloud Database Hybrid Tuning System for Personalized Requirements** 

*Cai B, Liu Y, Zhang C, et al. SIGMOD, 2022.* [[paper](https://scholar.archive.org/work/mhkvbi2uwfdvfb2zhj73brzb6a/access/wayback/https://dl.acm.org/doi/pdf/10.1145/3514221.3517882)]

---

#### Knob Selection

**SARD: A statistical approach for ranking database tuning parameters**

*Debnath B K, Lilja D J, Mokbel M F. ICDE Workshops 2008.*  [[paper](https://www-users.cse.umn.edu/~mokbel/papers/SARD.pdf)]

**Too Many Knobs to Tune? Towards Faster Database Tuning by Pre-selecting Important Knobs**

*Kanellis K, Alagappan R, Venkataraman S. HotStorage 2020.* [[paper](https://www.usenix.org/system/files/hotstorage20_paper_kanellis.pdf)]

---

#### Benefit Estimation

**IWEK: An Interpretable What-If Estimator for Database Knobs** ![](https://img.shields.io/badge/-random_forest-orange)   ![](https://img.shields.io/badge/-transfer-8cfff3)  

*Yu Yan, Hongzhi Wang, Jian Geng, et al. arXiv 2023.* [[paper](https://arxiv.org/pdf/2307.16115.pdf)] 

---

#### Experiments

**An inquiry into machine learning-based automatic configuration tuning services on real-world database management systems**

*Van Aken D, Yang D, Brillard S, et al. VLDB, 2021.* [[paper](https://www.cs.cmu.edu/~./pavlo/papers/p1241-aken.pdf)]

**Facilitating Database Tuning with Hyper-Parameter Optimization- A Comprehensive Experimental Evaluation**

*Zhang X, Chang Z, Li Y, et al. VLDB, 2022.* [[paper](https://15799.courses.cs.cmu.edu/spring2022/papers/09-knobs4/zhang-techreport2021.pdf)]

<br>


### View Advisor

**Selecting subexpressions to materialize at datacenter scale**

*A. Jindal, K. Karanasos, S. Rao, and H. Patel. PVLDB, 11(7):800–812, 2018.* [[paper](http://www.vldb.org/pvldb/vol11/p800-jindal.pdf)]

**Automated generation of materialized views in Oracle**

*Ahmed, R., Bello, R., Witkowski, A., & Kumar, P. (2020). VLDB, 2020.* [[paper](https://doi.org/10.14778/3415478.3415533)]


**Computation reuse in analytics job service at microsoft**

*Jindal, A., Qiao, S., Patel, H., Yin, Z., Di, J., Bag, M., Friedman, M., Lin, Y., Karanasos, K. and Rao, S., SIGMOD, 2018 (pp. 191-203).* [[paper](https://dl.acm.org/doi/abs/10.1145/3183713.3190656)]

**Automatic View Generation for Equivalent Subqueries with Deep Learning and Reinforcement Learning**

*Yuan, H., Sun, J., & Li, G. (2020). ICDE, 2020.* [[paper](https://doi.org/10.1109/ICDE48307.2020.00133)]

**An Autonomous Materialized View Management System with Deep Reinforcement Learning**

*Han, Y., Li, G., Yuan, H., & Sun, J. ICDE, 2021.* [[paper](https://doi.org/10.1109/ICDE51399.2021.00217)]

**AutoView: An Autonomous Materialized View Management System with Encoder-Reducer**

Han, Y., Li, G., Yuan, H. and Sun, J., TKDE, 2022. [[paper](https://ieeexplore.ieee.org/abstract/document/9744426/)]

**Dynamic Materialized View Management using Graph Neural Network**

*Yue Han, Chengliang Chai, Jiabin Liu, Guoliang Li, Chuangxian Wei, Chaoqun Zhan. ICDE 2023.* [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/dynamic-view-icde23.pdf)]

**A novel coral reefs optimization algorithm for materialized view selection in data warehouse environments**

*Azgomi, H. and Sohrabi, M.K., Applied Intelligence, 2019, 49, pp.3965-3989.* [[paper](https://link.springer.com/article/10.1007/s10489-019-01481-w)]


**DBSP: Automatic Incremental View Maintenance for Rich Query Languages**

*Mihai Budiu, Tej Chajed, Frank McSherry, et al. VLDB, 2023.* [[paper](https://www.vldb.org/pvldb/vol16/p1601-budiu.pdf)]

<br>

### Index Advisor

#### Preprocessing

 ![](https://img.shields.io/badge/-workload_compression-purple) [ISUM] **ISUM: Efficiently Compressing Large and Complex Workloads for Scalable Index Tuning**  ![](https://img.shields.io/badge/-index_aware-blue)
 
*Siddiqui, Tarique and Jo, Saehan and Wu, Wentao and Wang, Chi and Narasayya, Vivek and Chaudhuri, Surajit. SIGMOD, 2022* [[paper](https://www.microsoft.com/en-us/research/uploads/prod/2022/04/ISUM-ExtendedVersion.pdf)] 


![](https://img.shields.io/badge/-workload_compression-purple) [GSUM] **Primitives for workload summarization and implications for SQL**  ![](https://img.shields.io/badge/-index_agnostic-yellow)

*Chaudhuri, Surajit and Narasayya, Vivek and Ganesan, Prasanna. VLDB, 2023* [[paper](https://www.bing.com/ck/a?!&&p=e01a9d95f910866cJmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTAwOA&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&u=a1aHR0cHM6Ly93d3cudmxkYi5vcmcvY29uZi8yMDAzL3BhcGVycy9TMjJQMDIucGRm&ntb=1)] 


![](https://img.shields.io/badge/-workload_compression-purple) [QB5000] **Query-based workload forecasting for self-driving database management systems**  ![](https://img.shields.io/badge/-workload_compression-yellowgreen) ![](https://img.shields.io/badge/-index_agnostic-yellow) ![](https://img.shields.io/badge/-query_clustering-green)

*Ma, Lin and Van Aken, Dana and Hefny, Ahmed and Mezerhane, Gustavo and Pavlo, Andrew and Gordon, Geoffrey J. SIGMOD, 2018* [[paper](https://www.bing.com/ck/a?!&&p=28b344982a71d559JmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTIzMQ&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=Query-based+workload+forecasting+for+self-driving+database+management+systems&u=a1aHR0cHM6Ly93ZWIuZWVjcy51bWljaC5lZHUvfmxpbm1hY3NlL3B1YmxpY2F0aW9ucy8yMDE4LmZvcmVjYXN0aW5nLnNpZ21vZC5wZGY&ntb=1)] 


![](https://img.shields.io/badge/-workload_compression-purple)  **Compressing sql workloads**  ![](https://img.shields.io/badge/-index_agnostic-yellow) ![](https://img.shields.io/badge/-query_clustering-green)

*Chaudhuri, Surajit and Gupta, Ashish Kumar and Narasayya, Vivek. SIGMOD, 2022* [[paper](https://www.bing.com/ck/a?!&&p=6b800d696b3d4e5aJmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTE5Mw&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=Compressing+sql+workloads&u=a1aHR0cHM6Ly93d3cubWljcm9zb2Z0LmNvbS9lbi11cy9yZXNlYXJjaC93cC1jb250ZW50L3VwbG9hZHMvMjAwMi8wNi9TaWcwMi1XQy5wZGY&ntb=1)] 


![](https://img.shields.io/badge/-workload_compression-purple) **Comprehensive and efficient workload compression**   ![](https://img.shields.io/badge/-index_agnostic-yellow) ![](https://img.shields.io/badge/-greedy_selection-green) 

*Deep, Shaleen and Gruenheid, Anja and Koutris, Paraschos and Naughton, Jeffrey and Viglas, Stratis. VLDB, 2020* [[paper](https://www.bing.com/ck/a?!&&p=f48d32f30cba6aa4JmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTI0Mw&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=Comprehensive+and+efficient+workload+compression&u=a1aHR0cHM6Ly92bGRiYXJjLm9yZy9wdmxkYi92b2wxNC9wNDE4LWRlZXAucGRm&ntb=1)] 


![](https://img.shields.io/badge/-workload_compression-purple) [AutoIndex] **Autoindex: An incremental index management system for dynamic workloads**   ![](https://img.shields.io/badge/-index_agnostic-yellow)  ![](https://img.shields.io/badge/-templating_and_LRU-green)

*Zhou, Xuanhe and Liu, Luyang and Li, Wenbo and Jin, Lianyuan and Li, Shifu and Wang, Tianqing and Feng, Jianhua. ICDE, 2022* [[paper](https://www.bing.com/ck/a?!&&p=2eb543751e1f45c0JmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTE5Ng&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=Autoindex%3a+An+incremental+index+management+system+for+dynamic+workloads&u=a1aHR0cHM6Ly9kYmdyb3VwLmNzLnRzaW5naHVhLmVkdS5jbi9saWdsL3BhcGVycy9pY2RlMjAyMi1hdXRvaW5kZXgucGRm&ntb=1)] 


![](https://img.shields.io/badge/-feature_representation-blue) **Ai meets ai: Leveraging query executions to improve index recommendations**   ![](https://img.shields.io/badge/-DNN_and_Random_Forest-green)

*Ding, Bailu and Das, Sudipto and Marcus, Ryan and Wu, Wentao and Chaudhuri, Surajit and Narasayya, Vivek R. SIGMOD, 2019* [[paper](https://www.bing.com/ck/a?!&&p=f316aa373db264d0JmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTIxNA&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=Ai+meets+ai%3a+Leveraging+query+executions+to+improve+index+recommendations&u=a1aHR0cHM6Ly9wYWdlcy5jcy53aXNjLmVkdS9-d2VudGFvd3UvcGFwZXJzL3NpZ21vZDE5LWF1dG8taW5kZXhpbmcucGRm&ntb=1)] 


![](https://img.shields.io/badge/-feature_representation-blue) **Automatic view generation with deep learning and reinforcement learning**   ![](https://img.shields.io/badge/-LSTM-green)

*Yuan, Haitao and Li, Guoliang and Feng, Ling and Sun, Ji and Han, Yue. ICDE, 2020* [[paper](https://www.bing.com/ck/a?!&&p=3769b7e1fd57022bJmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTIxNA&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=Automatic+view+generation+with+deep+learning+and+reinforcement+learning&u=a1aHR0cHM6Ly9kYmdyb3VwLmNzLnRzaW5naHVhLmVkdS5jbi9saWdsL3BhcGVycy9pY2RlMjAyMC1sZWFybmVkdmlldy5wZGY&ntb=1)] 


![](https://img.shields.io/badge/-feature_representation-blue) [SmartIndex] **SmartIndex: An Index Advisor with Learned Cost Estimator**   ![](https://img.shields.io/badge/-LSTM_GCN_ResNet-green)

*Gao, Jianling and Zhao, Nan and Wang, Ning and Hao, Shuang. CIKM, 2022* [[paper](https://dl.acm.org/doi/pdf/10.1145/3511808.3557163)] [[code](https://github.com/JerryGao818/Index_selection_with_learned_estimator)] 


![](https://img.shields.io/badge/-feature_representation-blue) [QueryFormer] **QueryFormer: a tree transformer model for query plan representation**   ![](https://img.shields.io/badge/-Tree_Transformer-green)

*Zhao, Yue and Cong, Gao and Shi, Jiachen and Miao, Chunyan. VLDB, 2022* [[paper](https://dl.acm.org/doi/pdf/10.14778/3529337.3529349)] [[code](https://www.bing.com/ck/a?!&&p=3329458fd937365eJmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTIwNg&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=QueryFormer%3a+a+tree+transformer+model+for+query+plan+representation&u=a1aHR0cHM6Ly9naXRodWIuY29tL3Vlc3RjLXRhbmd5aWhlbmcvcXVlcnlmb3JtZXI&ntb=1)] 


 ![](https://img.shields.io/badge/-feature_representation-blue) [SWIRL] **SWIRL: Selection of Workload-aware Indexes using Reinforcement Learning**  ![](https://img.shields.io/badge/-bag_of_operator-green)   ![](https://img.shields.io/badge/-latent_semantic_index_model-yellow) 
 
*Kossmann, Jan and Kastius, Alexander and Schlosser, Rainer. EDBT, 2022* [[paper](https://www.bing.com/ck/a?!&&p=0b35e4290c4ba0adJmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTE5MQ&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=SWIRL%3a+Selection+of+Workload-aware+Indexes+using+Reinforcement+Learning&u=a1aHR0cHM6Ly9vcGVucHJvY2VlZGluZ3Mub3JnLzIwMjIvY29uZi9lZGJ0L3BhcGVyLTM3LnBkZg&ntb=1)] [[code](https://www.bing.com/ck/a?!&&p=cdf5e3d44367b3bcJmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTIxNA&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=SWIRL%3a+Selection+of+Workload-aware+Indexes+using+Reinforcement+Learning&u=a1aHR0cHM6Ly9naXRodWIuY29tL2h5cmlzZS9ybF9pbmRleF9zZWxlY3Rpb24&ntb=1)] 


 ![](https://img.shields.io/badge/-feature_representation-blue) [Indexer++] **Indexer++ workload-aware online index tuning with transformers and reinforcement learning**  ![](https://img.shields.io/badge/-RoBERTa-green) ![](https://img.shields.io/badge/-T_SNE-yellow)
 
*Sharma, Vishal and Dyreson, Curtis. SIGAPP, 2022* [[paper](https://www.bing.com/ck/a?!&&p=e1afe298caf3fbf1JmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTE4Mw&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=Indexer%2b%2b+workload-aware+online+index+tuning+with+transformers+and+reinforcement+learning&u=a1aHR0cHM6Ly9kbC5hY20ub3JnL2RvaS9wZGYvMTAuMTE0NS8zNDc3MzE0LjM1MDc2OTE&ntb=1)] 


![](https://img.shields.io/badge/-feature_representation-blue) [LIB] **Learned Index Benefits: Machine Learning Based Index Performance Estimation**   ![](https://img.shields.io/badge/-Set_Transformer-green)

*Shi, Jiachen and Cong, Gao and Li, Xiao-Li. VLDB, 2022* [[paper](https://dl.acm.org/doi/pdf/10.14778/3565838.3565848)] [[code](https://www.bing.com/ck/a?!&&p=14cd0ddb44d6c124JmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zNDY3ZGRjMS0yZmMwLTYyMzctM2E0Ny1jZTJiMmUzYTYzZGYmaW5zaWQ9NTIzNg&ptn=3&ver=2&hsh=3&fclid=3467ddc1-2fc0-6237-3a47-ce2b2e3a63df&psq=Learned+Index+Benefits%3a+Machine+Learning+Based+Index+Performance+Estimation&u=a1aHR0cHM6Ly9naXRodWIuY29tL0pDLVNoaS9MZWFybmVkLUluZGV4LUJlbmVmaXRz&ntb=1)] 



 ![](https://img.shields.io/badge/-candidate_generation-orange) [AIM] **AIM: A practical approach to automated index management for SQL databases** 
 
*Yadav, Ritwik and Valluri, Satyanarayana R. and Zaït, Mohamed. ICDE, 2023* [[paper](https://www.vldb.org/conf/1997/P146.PDF)] 





#### Offline Index Tuning

![](https://img.shields.io/badge/-Experimental-red) **Magic mirror in my hand, which is the best in the land? An Experimental Evaluation of Index Selection Algorithms** ![](https://img.shields.io/badge/-heuristics-yellowgreen)      
*Kossmann, Jan and Halfpap, Stefan and Jankrift, Marcel and Schlosser, Rainer. VLDB, 2020.* [[paper](http://www.vldb.org/pvldb/vol13/p2382-kossmann.pdf)] 

 ![](https://img.shields.io/badge/-LP-purple)  **Exact and approximate algorithms for the index selection problem in physical database design**  ![](https://img.shields.io/badge/-branch_and_cut-green)
 
*Caprara, Alberto and Fischetti, Matteo and Maio, Dario. TKDE, 1995* [[paper](https://www.academia.edu/10160281/Exact_and_Approximate_Algorithms_for_the_Index_Selection_Problem_in_Physical_Database_Design)] 


 ![](https://img.shields.io/badge/-LP-purple)  **A branch-and-cut algorithm for a generalization of the uncapacitated facility location problem**  ![](https://img.shields.io/badge/-branch_and_cut-green)
 
*Caprara, Alberto and Gonz{\'a}lez, JJ. Top, 1996* [[paper](https://link.springer.com/article/10.1007/bf02568608)] 


 ![](https://img.shields.io/badge/-LP-purple)  **Separating lifted odd-hole inequalities to solve the index selection problem**  ![](https://img.shields.io/badge/-branch_and_cut-green)
 
*Caprara, Alberto and Gonz{\'a}lez, Juan Jos{\'e} Salazar. Discrete Applied Mathematics, 1999* [[paper](https://www.academia.edu/10903910/Separating_Lifted_Odd_hole_Inequalities_to_Solve_the_Index_Selection_Problem)] 


 ![](https://img.shields.io/badge/-LP-purple)  [papadomanolakis2007integer] ****  ![](https://img.shields.io/badge/-LP_solver-green)
 
** [[paper]()] 


 ![](https://img.shields.io/badge/-DFS-purple)  **The optimal selection of secondary indices for files**  ![](https://img.shields.io/badge/--)
 
*Mario Schkolnick. Information Systems, 1975* [[paper](https://figshare.com/articles/journal_contribution/The_optimal_selection_of_secondary_indices_for_files/6610724/1/files/12102875.pdf)] 


 ![](https://img.shields.io/badge/-DP-blue)  **Intelligent Index Tuning Approach for Relational Databases**  
 
*Qiu, Tao and Wang, Bin and Shu, Zhaowei and Zhao, Zhibo and Song, Ziwen and Zhong, Yanhui. Journal of Software, 2020* [[paper](https://kns.cnki.net/kcms2/article/abstract?v=xFzLC8E_KjFaB-CZazP6wJjOtv-2WmnS1dlFbs215fbK_ycawiuz2UB3hAyYGeu_q_i454q4u7SENxszChJs8NX0wC1Mayun31a93X_S1zDMfF6y8RR-YMh2-sXbv8w-ICPXscSiAq04_ysaHJfJaQ==&uniplatform=NZKPT&language=CHS)] 


 ![](https://img.shields.io/badge/-DP-blue)  **CedarAdvisor: A load-adaptive automatic indexing recommendation tool**  
 
*Yang, Wencan and Hu, Huiqi and Duan, Huichao and Hu, Yaoyi and Qian, Weining. Journal of East China Normal University (Natural Science), 2020* [[paper](https://kns.cnki.net/kcms2/article/abstract?v=xFzLC8E_KjHzYy-GL4ZZyt6rjdGysJfZQ2JK_cU0VoKlZGkbil-_YD7GpdhxA5ZCFKIi9luSK1xK1outuBYrkuExIzifMI6NxnelRnHBZsnEJlAhl99-jTdL7wB2IJjoFI7-VOCaFzWKEEUgJ_4EPA==&uniplatform=NZKPT&language=CHS)] 


 ![](https://img.shields.io/badge/-Heuristic-Orange) [AutoAdmin] **An efficient, cost-driven index selection tool for Microsoft SQL server**  
 
*Chaudhuri, Surajit and Narasayya, Vivek R. VLDB 1997* [[paper](http://www.vldb.org/conf/1997/P146.PDF)] 


 ![](https://img.shields.io/badge/-Heuristic-Orange)  [DB2Advis] **DB2 advisor: An optimizer smart enough to recommend its own indexes**  
 
*Valentin, Gary and Zuliani, Michael and Zilio, Daniel C and Lohman, Guy and Skelley, Alan. ICDE, 2000* [[paper](https://www.bing.com/ck/a?!&&p=08e4abb7b92dc6a6JmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zOTA4NTgzYi1hNGIzLTY5NTItMjhhMC00YTVjYTU5ZDY4MWEmaW5zaWQ9NTIwMw&ptn=3&ver=2&hsh=3&fclid=3908583b-a4b3-6952-28a0-4a5ca59d681a&psq=DB2+advisor%3a+An+optimizer+smart+enough+to+recommend+its+own+indexes&u=a1aHR0cHM6Ly93d3cuY3MudG9yb250by5lZHUvfmFsYW4vcGFwZXJzL2ljZGUwMC5wZGY&ntb=1)] 



 ![](https://img.shields.io/badge/-Heuristic-Orange)  [Extend] **Efficient scalable multi-attribute index selection using recursive strategies**  
 
*Schlosser, Rainer and Kossmann, Jan and Boissier, Martin. ICDE, 2019* [[paper](https://www.bing.com/ck/a?!&&p=a7a6f59969709befJmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zOTA4NTgzYi1hNGIzLTY5NTItMjhhMC00YTVjYTU5ZDY4MWEmaW5zaWQ9NTIxMA&ptn=3&ver=2&hsh=3&fclid=3908583b-a4b3-6952-28a0-4a5ca59d681a&psq=Efficient+scalable+multi-attribute+index+selection+using+recursive+strategies&u=a1aHR0cHM6Ly93d3cucmVzZWFyY2hnYXRlLm5ldC9wcm9maWxlL01hcnRpbi1Cb2lzc2llci9wdWJsaWNhdGlvbi8zMzI1Mjk0NTdfRWZmaWNpZW50X1NjYWxhYmxlX011bHRpLUF0dHJpYnV0ZV9JbmRleF9TZWxlY3Rpb25fVXNpbmdfUmVjdXJzaXZlX1N0cmF0ZWdpZXMvbGlua3MvNWNiZWQ2MDA0NTg1MTU2Y2Q3YWI2OGY1L0VmZmljaWVudC1TY2FsYWJsZS1NdWx0aS1BdHRyaWJ1dGUtSW5kZXgtU2VsZWN0aW9uLVVzaW5nLVJlY3Vyc2l2ZS1TdHJhdGVnaWVzLnBkZg&ntb=1)] 



 ![](https://img.shields.io/badge/-Heuristic-Orange)   **On the selection of an optimal set of indexes**  
 
*Ip, Maggie Y. L. and Saxton, Lawrence V. and Raghavan, Vijay V.. IEEE Transactions on Software Engineering, 1983* [[paper](https://www.computer.org/csdl/journal/ts/1983/02/01703030/13rRUzphDzm)] 


 ![](https://img.shields.io/badge/-Heuristic-Orange)   **Index selection for databases: A hardness study and a principled heuristic solution**  
 
*Chaudhuri, Surajit and Datar, Mayur and Narasayya, Vivek. TKDE, 2004* [[paper](https://www.computer.org/csdl/journal/tk/2004/11/k1313/13rRUx0xPnf)] 


 ![](https://img.shields.io/badge/-Heuristic-Orange)  [Drop] **Index selection in relational databases**  
 
*Whang, Kyu-Young. Foundation of Data Organization, 1983* [[paper](https://www.bing.com/ck/a?!&&p=5e89fa294af0e081JmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zOTA4NTgzYi1hNGIzLTY5NTItMjhhMC00YTVjYTU5ZDY4MWEmaW5zaWQ9NTIyMQ&ptn=3&ver=2&hsh=3&fclid=3908583b-a4b3-6952-28a0-4a5ca59d681a&psq=Index+selection+in+relational+databases&u=a1aHR0cHM6Ly9saW5rLnNwcmluZ2VyLmNvbS9jb250ZW50L3BkZi8xMC4xMDA3Lzk3OC0xLTQ2MTMtMTg4MS0xXzQxLnBkZg&ntb=1)] 


 ![](https://img.shields.io/badge/-Heuristic-Orange)  [Relaxation] **Automatic physical database tuning: A relaxation-based approach**  
 
*Bruno, Nicolas and Chaudhuri, Surajit. SIGMOD, 2005* [[paper](https://www.bing.com/ck/a?!&&p=b8c7cb40b67a2308JmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zOTA4NTgzYi1hNGIzLTY5NTItMjhhMC00YTVjYTU5ZDY4MWEmaW5zaWQ9NTE4Ng&ptn=3&ver=2&hsh=3&fclid=3908583b-a4b3-6952-28a0-4a5ca59d681a&psq=Automatic+physical+database+tuning%3a+A+relaxation-based+approach&u=a1aHR0cHM6Ly93d3cubWljcm9zb2Z0LmNvbS9lbi11cy9yZXNlYXJjaC93cC1jb250ZW50L3VwbG9hZHMvMjAwNS8wMS9uZXdkdGEucGRm&ntb=1)] 


 ![](https://img.shields.io/badge/-Heuristic-Orange)   **Index merging**  
 
*Chaudhuri, S. and Narasayya, V.. ICDE, 1999* [[paper](https://ieeexplore.ieee.org/document/754945)] 


 ![](https://img.shields.io/badge/-Heuristic-Orange)   **On a new approach to the index selection problem using mining algorithms**  
 
*Ameri, Parinaz and Meyer, J{\"o}rg and Streit, Achim. Big Data, 2015* [[paper](https://ieeexplore.ieee.org/document/7364084)] 


 ![](https://img.shields.io/badge/-Heuristic-Orange)   **Semi-automatic index tuning: Keeping dbas in the loop**  ![](https://img.shields.io/badge/-WFIT-green) 
 
*Schnaitter, Karl and Polyzotis, Neoklis. VLDB, 2012* [[paper](https://dl.acm.org/doi/pdf/10.14778/2140436.2140444)] 


 ![](https://img.shields.io/badge/-Heuristic-Orange)   **Automatic index selection for large-scale datalog computation**  
 
*Suboti{\'c}, Pavle and Jordan, Herbert and Chang, Lijun and Fekete, Alan and Scholz, Bernhard. VLDB, 2018* [[paper](https://www.bing.com/ck/a?!&&p=8cda915901b9dd66JmltdHM9MTcwODY0NjQwMCZpZ3VpZD0zOTA4NTgzYi1hNGIzLTY5NTItMjhhMC00YTVjYTU5ZDY4MWEmaW5zaWQ9NTE4Mw&ptn=3&ver=2&hsh=3&fclid=3908583b-a4b3-6952-28a0-4a5ca59d681a&psq=Automatic+index+selection+for+large-scale+datalog+computation&u=a1aHR0cHM6Ly93d3cudmxkYi5vcmcvcHZsZGIvdm9sMTIvcDE0MS1zdWJvdGljLnBkZg&ntb=1)] 


 ![](https://img.shields.io/badge/-Heuristic-Orange)   ****  
 
** [[paper]()] 
 ![](https://img.shields.io/badge/-Heuristic-Orange)   ****  
 
** [[paper]()] 
 ![](https://img.shields.io/badge/-Heuristic-Orange)   ****  
 
** [[paper]()] 
 ![](https://img.shields.io/badge/-Heuristic-Orange)   ****  
 
** [[paper]()] 
 ![](https://img.shields.io/badge/-Heuristic-Orange)   ****  
 
** [[paper]()] 
---

#### Online Index Tuning


---

#### Index Benefit Estimation



---

#### Industry Papers



---

#### Adaptive Indexing





<br>

**[EA & B]** Jan Kossmann, Stefan Halfpap, Marcel Jankrift, Rainer Schlosser: *Magic mirror in my hand, which is the best in the land? An Experimental Evaluation of Index Selection Algorithms.* Proc. VLDB Endow. 13(11): 2382-2395 (2020) [[paper](http://www.vldb.org/pvldb/vol13/p2382-kossmann.pdf)]

**[Industry, Microsoft Azure]** Sudipto Das, Miroslav Grbic, Igor Ilic, Isidora Jovandic, Andrija Jovanovic, Vivek R. Narasayya, Miodrag Radulovic, Maja Stikic, Gaoxiang Xu, Surajit Chaudhuri: *Automatically Indexing Millions of Databases in Microsoft Azure SQL Database.* SIGMOD Conference 2019: 666-679 [[paper](https://www.microsoft.com/en-us/research/uploads/prod/2019/02/autoindexing_azuredb.pdf)]

**[Industry, Meta]** Ritwik Yadav, Satyanarayana R. Valluri, Mohamed Zait: *AIM: A practical approach to automated index management for SQL databases*. ICDE 2023 [[paper](https://research.facebook.com/micro_site/url/?click_from_context_menu=true&country=CN&destination=https%3A%2F%2Fresearch.facebook.com%2Ffile%2F215595724407039%2FAIM_SRT_Update.pdf&event_type=click&last_nav_impression_id=0CS9zArYOjQEk5cnm&max_percent_page_viewed=36&max_viewport_height_px=961&max_viewport_width_px=1912&orig_http_referrer=https%3A%2F%2Fwww.google.com%2F&orig_request_uri=https%3A%2F%2Fresearch.facebook.com%2Fpublications%2Faim-a-practical-approach-to-automated-index-management-for-sql-databases%2F&region=apac&scrolled=false&session_id=0e6eXwoLiqjYPPnEb&site=mc_research)]

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

**[Optimization, Learned Cost]** Jiachen Shi, Gao Cong, Xiaoli Li: Learned Index Benefits: Machine Learning Based Index Performance Estimation. Proc. VLDB Endow. 15(13): 3950-3962 (2022) [[paper](https://www.vldb.org/pvldb/vol15/p3950-shi.pdf)]

**[Optimization, Learned Cost]** Jianling Gao, Nan Zhao, Ning Wang, Shuang Hao:
*SmartIndex: An Index Advisor with Learned Cost Estimator*. CIKM 2022: 4853-4856 [[paper](https://dl.acm.org/doi/abs/10.1145/3511808.3557163)]

**[Optimization, Workload Summarization]** Tarique Siddiqui, Saehan Jo, Wentao Wu, Chi Wang, Vivek R. Narasayya, Surajit Chaudhuri:
*ISUM: Efficiently Compressing Large and Complex Workloads for Scalable Index Tuning.* SIGMOD Conference 2022: 660-673 [[paper](https://dl.acm.org/doi/10.1145/3514221.3526152)]

**[Optimization, What-if Call]** Tarique Siddiqui, Wentao Wu, Vivek R. Narasayya, Surajit Chaudhuri:
*DISTILL: Low-Overhead Data-Driven Techniques for Filtering and Costing Indexes for Scalable Index Tuning.* Proc. VLDB Endow. 15(10): 2019-2031 (2022) [[paper](https://dl.acm.org/doi/abs/10.14778/3547305.3547309)]

<br>

### Partition Advisor

**Automating physical database design in a parallel database.** ![](https://img.shields.io/badge/-horizontal-brown) 

*Jun Rao, Chun Zhang, Nimrod Megiddo, Guy M. Lohman. SIGMOD, 2002.* [[paper](https://www.csd.uoc.gr/~hy460/pdf/p558-rao.pdf)]


**Schism: a Workload-Driven Approach to Database Replication and Partitioning.** ![](https://img.shields.io/badge/-horizontal-brown)

*Carlo Curino, Yang Zhang, Evan P. C. Jones, Samuel Madden. PVLDB, 2010.* [[paper](https://doi.org/10.14778/1920841.1920853)]


**Locality-aware partitioning in parallel database systems.**

*Erfan Zamanian, Carsten Binnig, Abdallah Salama. SIGMOD, 2015.* [[paper](https://doi.org/10.1145/2723372.2723718)]


**Query centric partitioning and allocation for partially replicated database systems.**

*Tilmann Rabl, Hans-Arno Jacobsen. SIGMOD, 2017.* [[paper](https://doi.org/10.1145/3035918.3064052)]

**Workload-driven horizontal partitioning and pruning for large HTAP systems.** ![](https://img.shields.io/badge/-horizontal-brown)  ![](https://img.shields.io/badge/-data_skip-yellow) 

*Martin Boissier, Kurzynski Daniel. ICDE Workshop, 2018.* [[paper](https://doi.org/10.1109/ICDEW.2018.00026)]


**Towards learning a partitioning advisor with deep reinforcement learning.**  ![](https://img.shields.io/badge/-horizontal-brown)  ![](https://img.shields.io/badge/-RL-yellow) 

*Benjamin Hilprecht, Carsten Binnig, Uwe Röhm. aiDM@SIGMOD, 2019.* [[paper](https://doi.org/10.1145/3329859.3329876)]


**Automated vertical partitioning with deep reinforcement learning**. ![](https://img.shields.io/badge/-vertical-green)

*Campero Durand G, Piriyev R, Pinnecke M, et al. ADBIS, 2019.* [[paper](https://doi.org/10.1007/978-3-030-30278-8_16)]


**Fast and effective distribution-key recommendation for amazon redshift.**  ![](https://img.shields.io/badge/-horizontal-brown)  ![](https://img.shields.io/badge/-algorithm_set-yellow) 

*Panos Parchas, Yonatan Naamad, Peter Van Bouwel, et al. PVLDB, 2020.* [[paper](https://doi.org/10.14778/3407790.3407834)]


**Adaptive partitioning and indexing for in situ query processing.** ![](https://img.shields.io/badge/-situ-blue)

*Olma, M., Karpathiotakis, M., Alagiannis, I., Athanassoulis, et al. VLDB Journal.* [[paper](https://doi.org/10.1007/s00778-019-00580-x)]


**Learning a Partitioning Advisor for Cloud Databases.**  ![](https://img.shields.io/badge/-horizontal-brown)  ![](https://img.shields.io/badge/-RL-yellow) 

*Benjamin Hilprecht, Carsten Binnig, Uwe Röhm. SIGMOD, 2020.* [[paper](https://15799.courses.cs.cmu.edu/spring2022/papers/10-partitioning/hilprecht-sigmod2020.pdf)]


**Grep: A Graph Learning Based Database Partitioning System.**  ![](https://img.shields.io/badge/-horizontal-brown)  ![](https://img.shields.io/badge/-GNN-orange) 

*Xuanhe Zhou, Guoliang Li, Jianhua Feng, et al. SIGMOD, 2023.* [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/grep.pdf)] [[demo](https://github.com/TsinghuaDatabaseGroup/AI4DBCode/tree/master/DatabasePartition)]

<br>

### Hybrid Advisor

**Universal Database Optimization using Reinforcement Learning**

*Wang J, Trummer I, Basu D. VLDB, 2021.* [[paper](http://www.vldb.org/pvldb/vol14/p3402-wang.pdf)]


**A Unified and Efficient Coordinating Framework for Autonomous DBMS Tuning**

*Xinyi Zhang, Zhuo Chang, HONG WU, et al. SIGMOD, 2023.* [[paper](https://arxiv.org/abs/2303.05710)]



## 2. Query Optimization

### Query Rewriter 

(note other interesting problems like [text2SQL](https://github.com/yechens/NL2SQL) are not within the scope)

#### Traditional

**[Rewrite Rules]** 	Béatrice Finance, Georges Gardarin. A Rule-Based Query Rewriter in an Extensible DBMS. ICDE 1991. [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=131472)]

**[Rewrite Rules]** 	Hamid Pirahesh, Joseph M. Hellerstein, Waqar Hasan. *Extensible/Rule Based Query Rewrite Optimization in Starburst*. SIGMOD Conference 1992. [[paper](https://sigmodrecord.org/publications/sigmodRecord/9206/pdfs/141484.130294.pdf)]

**[Cost/Heuristic Rewrite]** Rafi Ahmed, Allison W. Lee, Andrew Witkowski, et al. *Cost-Based Query Transformation in Oracle*. VLDB 2006: 1026-1036. [[paper](https://www.researchgate.net/publication/221311318_Cost-Based_Query_Transformation_in_Oracle/link/572bbc5e08aef7c7e2c6b829/download)]

**[Heuristic Rewrite]** De Araújo, A. H. M., Monteiro, J. M., Antônio, J., De Macêdo, F., Tavares, J. A., Brayner, A., & Lifschitz, S. (2014). *ARe-SQL: An Online, Automatic and Non-Intrusive Approach for Rewriting SQL Queries*. JIDM, 2014. [[paper](https://www.researchgate.net/publication/264081912_ARE-SQL_AN_ONLINE_AUTOMATIC_AND_NON-INTRUSIVE_APPROACH_FOR_REWRITING_SQL_QUERIES)]

**[Semantic Equivalence]** 	Shumo Chu, Konstantin Weitz, Alvin Cheung, Dan Suciu. *HoTTSQL: proving query rewrites with univalent SQL semantics*. PLDI 2017: 510-524. [[paper](https://doi.org/10.1145/3062341.3062348)]

**[Optimization Engine]** Begoli, E., Camacho-Rodríguez, J., Hyde, J., Mior, M. J., & Lemire, D. (2018). *Apache calcite: A foundational framework for optimized query processing over heterogeneous data sources*. SIGMOD, 2018. [[paper](https://doi.org/10.1145/3183713.3190662)]

**[Map-Reduce Rewrite]** 	Partho Sarthi, Kaushik Rajan, Akash Lal, Abhishek Modi, et al. *Generalized Sub-Query Fusion for Eliminating Redundant I/O from Big-Data Queries. OSDI 2020: 209-224*.  [[paper](https://www.usenix.org/system/files/osdi20-sarthi_0.pdf)]

**[Streaming]** Wentao Wu, Philip A. Bernstein, Alex Raizman, Christina Pavlopoulou. *Cost-based Query Rewriting Techniques for Optimizing Aggregates Over Correlated Windows*. CoRR abs/2008.12379 (2020)  [[paper](https://www.researchgate.net/profile/Wentao-Wu-2/publication/343986286_Cost-based_Query_Rewriting_Techniques_for_Optimizing_Aggregates_Over_Correlated_Windows/links/5f52ad2e299bf13a31a07101/Cost-based-Query-Rewriting-Techniques-for-Optimizing-Aggregates-Over-Correlated-Windows.pdf)]

**[Program Synthesis]** Rui Dong, Jie Liu, Yuxuan Zhu, Cong Yan, Barzan Mozafari, Xinyu Wang. *SlabCity: Whole-Query Optimization Using Program Synthesis*. VLDB, 2023: 3151-3164. [[paper](https://www.vldb.org/pvldb/vol16/p3151-dong.pdf)]

**[Rewrite Rules]** 	Zhaoguo Wang, Zhou Zhou, Yicun Yang, Haoran Ding, Gansen Hu, Ding Ding, Chuzhe Tang, Haibo Chen, Jinyang Li. *WeTune: Automatic Discovery and Verification of Query Rewrite Rules*. SIGMOD Conference 2022: 94-107. [[paper](https://ipads.se.sjtu.edu.cn/_media/publications/wetune_final.pdf)]

**[Rewrite Rules]** 	Qiushi Bai, Sadeem Alsudais, Chen Li. *QueryBooster: Improving SQL Performance Using Middleware Services for Human-Centered Query Rewriting*. VLDB, 2023. [[paper](https://arxiv.org/pdf/2305.08272.pdf)]


#### Learning-based

**[Predicate Rewrite]** Qi Zhou, Joy Arulraj, Shamkant B. Navathe, William Harris, Jinpeng Wu. *Sia : Optimizing Queries using Learned Predicates*. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3457262)]

**[Rewrite Strategy]** Xuanhe Zhou, Guoliang Li, Chengliang Chai, Jianhua Feng. *A Learned Query Rewrite System using Monte Carlo Tree Search*. VLDB, 2022. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb22-query-rewrite.pdf)]


### Cardinality Estimation

**[Card, Query-based]** Dutt, A., Wang, C., Nazi, A., Kandula, S., Narasayya, V., & Chaudhuri, S. (2018). Selectivity estimation for range predicates using lightweight models. Proceedings of the VLDB Endowment, 12(9), 1044–1057, 2018. [[paper](https://doi.org/10.14778/3329772.3329780)]

**[Card, Query-based]** Kipf A, Kipf T, Radke B, et al. Learned cardinalities: Estimating correlated joins with deep learning. CIDR, 2019. [[paper](https://arxiv.org/pdf/1809.00677)]

**[Card, Query-based]** Woltmann L, Hartmann C, Thiele M, et al. Cardinality estimation with local deep learning models. aiDM, 2019. [[paper](https://doi.org/10.1145/3329859.3329875)]

**[Card, Query-based]** Hayek, R., & Shmueli, O. (2020). *NN-based Transformation of Any SQL Cardinality Estimator for Handling DISTINCT, AND, OR and NOT*. arXiv， 2020. [[paper](http://arxiv.org/abs/2004.07009)]

**[Card, Query-based]** Tzoumas K, Deshpande A, Jensen C S. Lightweight graphical models for selectivity estimation without independence assumptions[J]. Proceedings of the VLDB Endowment, 4(11): 852-863, 2011. [[paper](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.228.675&rep=rep1&type=pdf)]

**[Card, Query-based]** Xiao Hu, Yuxi Liu, Haibo Xiu, Pankaj K. Agarwal, Debmalya Panigrahi, Sudeepa Roy, Jun Yang. *Selectivity Functions of Range Queries are Learnable*. SIGMOD, 2022. [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3517896)]

**[Card, Query-based, Adaptability]** Beibin Li, Yao Lu, Srikanth Kandula: Warper: Efficiently Adapting Learned Cardinality Estimators to Data and Workload Drifts. SIGMOD Conference 2022: 1920-1933 [[paper](https://dl.acm.org/doi/10.1145/3514221.3526179)]

**[Card, Query-based, Robust Encoding & Training]** Negi, Parimarjan, Ziniu Wu, Andreas Kipf, Nesime Tatbul, Ryan Marcus, Sam Madden, Tim Kraska, and Mohammad Alizadeh: Robust Query Driven Cardinality Estimation under Changing Workloads. VLDB, 2023. [[paper](https://www.vldb.org/pvldb/vol16/p1520-negi.pdf)]

**[Card, Data-based]** Leis, V., Radke, B., Gubichev, A., Kemper, A., & Neumann, T. (2017). Cardinality estimation done right: Index-based join sampling. CIDR, 2017. [[paper](http://cidrdb.org/cidr2017/papers/p9-leis-cidr17.pdf)]

**[Card, Data-based]** Yang, Z., Liang, E., Kamsetty, A., Wu, C., Duan, Y., Chen, X., … Stoica, I. (2019). Deep Unsupervised Cardinality Estimation. VLDB, 2019. [[paper](https://doi.org/10.14778/3368289.3368294)]

**[Card, Data-based]** Yang, Z., Kamsetty, A., Luan, S., Liang, E., Duan, Y., Chen, X., & Stoica, I. (2020). Neurocard: One cardinality estimator for all tables. *Proceedings of the VLDB Endowment*, *14*(1), 61–73, 2020. [[paper](https://doi.org/10.14778/3421424.3421432)]

**[Card, Data-based]** Zhu R, Wu Z, Han Y, et al. FLAT: Fast, Lightweight and Accurate Method for Cardinality Estimation[J]. arXiv preprint arXiv:2011.09022, 2020. [[paper](https://arxiv.org/pdf/2011.09022)]

**[Card, Data-based]** Wu Z, Shaikhha A, Zhu R, et al. BayesCard: Revitilizing Bayesian Frameworks for Cardinality Estimation. arXiv preprint arXiv: 2012.14743, 2020. [[paper](https://arxiv.org/pdf/2012.14743)]

**[Card, Data-based]** Hilprecht, B., Schmidt, A., Kulessa, M., Molina, A., Kersting, K., & Binnig, C. (2020). DeepDB: Learn from data, not from queries! VLDB, *13*(7), 992–1005, 2020. [[paper](https://doi.org/10.14778/3384345.3384349)]

**[Card, Data-based]** Yongjoo Park, Shucheng Zhong, and Barzan Mozafari. Quicksel: Quick selectivity learning with mixture models. SIGMOD 2020. [[paper](https://arxiv.org/pdf/1812.10568.pdf)]

**[Card, Data-based]** Lu Y, Kandula S, König A C, et al. Pre-training summarization models of structured datasets for cardinality estimation[J]. Proceedings of the VLDB Endowment, 2021. [[paper](https://dl.acm.org/doi/pdf/10.14778/3494124.3494127?casa_token=v6OMWXKyNM4AAAAA:gN2zqOt0DBvEt7AhW3e26aZSREvTaMWb6f64f9m_Vs4dLcs-18paOgLbX4Mzq1IlJ-ILFl2-nNZXdiI)] 

**[Card, Data-based]** Zhu, R., Wu, Z., Han, Y., Zeng, K., Pfadler, A., Qian, Z., … Cui, B. (2020). FLAT: Fast, Lightweight and Accurate Method for Cardinality Estimation. VLDB, 2021. [[paper](http://arxiv.org/abs/2011.09022)]

**[Card, Data-based]** Jiayi Wang, Chengliang Chai, Jiabin Liu, Guoliang Li. FACE: A Normalizing Flow based Cardinality Estimator. VLDB 2022. [[paper](https://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb22-flow-card.pdf)]

**[Card, Data-based]** Yao Lu, Srikanth Kandula, Arnd Christian König, Surajit Chaudhuri. Pre-training summarization models of structured datasets for cardinality estimation. VLDB 2022. [[paper](https://www.vldb.org/pvldb/vol15/p414-lu.pdf)]

**[Card, Query&Data-based]** Wu P, Cong G. A Unified Deep Model of Learning from both Data and Queries for Cardinality Estimation. SIGMOD. 2021: 2009-2022. [[paper](https://arxiv.org/pdf/2107.12295)]

**[Card]** Parimarjan Negi, Ryan C. Marcus, Andreas Kipf, Hongzi Mao, Nesime Tatbul, Tim Kraska, Mohammad Alizadeh. Flow-Loss: Learning Cardinality Estimates That Matter. VLDB Endow, 14(11): 2019-2032, 2021. [[paper](http://www.vldb.org/pvldb/vol14/p2019-negi.pdf)] 

**[Card, Model Selection]** Jintao Zhang, Chao Zhang, Guoliang Li, Chengliang Chai. *AutoCE: An Accurate and Efficient Model Advisor for Learned Cardinality Estimation*. ICDE, 2023.  [[paper](https://github.com/jt-zhang/jt-zhang.github.io/raw/master/files/AutoCE_camera_ready_icde23.pdf)]

**[Card]** Xiaoye Miao, Yangyang Wu, Jiazhen Peng, et al. Efficient and Effective Cardinality Estimation for Skyline Family. SIGMOD, 2023. [[paper](https://dl.acm.org/doi/10.1145/3588958)]

**[Card]** Ziniu Wu, Parimarjan Negi, Mohammad Alizadeh, Tim Kraska, Samuel Madden. FactorJoin: A New Cardinality Estimation Framework for Join Queries. SIGMOD, 2023. [[paper](https://dl.acm.org/doi/10.1145/3588721)]

**[Card, Query-based]** Fang Wang, Xiao Yan, Man Lung Yiu, Shuai Li, Zunyao Mao, and Bo Tang. Speeding Up End-to-end Query Execution via Learning-based Progressive Cardinality Estimation. SIGMOD, 2023. [[paper](https://dl.acm.org/doi/pdf/10.1145/3588708)]

**[ EA&B ]** Wang, X., Qu, C., Wu, W., Wang, J., & Zhou, Q. (2021). Are We Ready For Learned Cardinality Estimation?  Proc. VLDB Endow. 14(9): 1640-1654 (2021). [[paper](http://www.vldb.org/pvldb/vol14/p1640-wang.pdf)]

**[ EA&B ]** Sun, J., Zhang, J., Sun, Z., Li, G., & Tang, N. (n.d.). *Learned Cardinality Estimation : A Design Space Exploration and a Comparative Evaluation [ EA & B ]*. *14*(1). VLDB, 2022. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb22-card-exp.pdf)]

**[ EA&B ]** Yuxing Han, Ziniu Wu, Peizhi Wu, et al. Cardinality Estimation in DBMS: A Comprehensive Benchmark Evaluation Yuxing. VLDB, 2022. [[paper](https://arxiv.org/abs/2109.05877)] 

**[ EA&B ]** Kyoungmin Kim, Jisung Jung, In Seo, Wook-Shin Han, Kangwoo Choi, Jaehyok Chong: Learned Cardinality Estimation: An In-depth Study. SIGMOD Conference 2022: 1214-1227 [[paper](https://dl.acm.org/doi/abs/10.1145/3514221.3526154)]

**[ EA&B ]** Harmouch, H., & Naumann, F. (2018). Cardinality Estimation: An Experimental Survey. *Pvldb*, *11*(4), 4999–512, 2017. [[paper](https://doi.org/10.1145/3164135.3164145)]

**[ EA&B, Data Update ]** Meghdad Kurmanji, Eleni Triantafillou, Peter Triantafillou. Machine Unlearning in Learned Databases: An Experimental Analysis. *SIGMOD, 2024.* [[paper](https://arxiv.org/pdf/2311.17276.pdf)] [[code](https://github.com/meghdadk/DB_unlearning)]

### Cost Estimation

**[Cost]** Marcus, R., & Papaemmanouil, O. (2019). *Plan-Structured Deep Neural Network Models for Query Performance Prediction*. 1733–1746. [[paper](http://arxiv.org/abs/1902.00132)]

**[Cost]** Sun, J., & Li, G. (n.d.). *An End-to-End Learning-based Cost Estimator*. VLDB, 2020. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb2020-learnedcost.pdf)]

**[Cost]** Benjamin Hilprecht, Carsten Binnig. *Zero-Shot Cost Models for
Out-of-the-box Learned Cost Prediction*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p2361-hilprecht.pdf)]

### Plan Optimization

**Continuously Adaptive Query Processing**

*Ron Avnur, Joseph M. Hellerstein. Eddies. SIGMOD, 2000.* [[paper](https://dl.acm.org/doi/pdf/10.1145/342009.335420)]

**How Good Are Query Optimizers, Really?** ![](https://img.shields.io/badge/benchmark-blue) 

*Leis, V., Gubichev, A., Mirchev, A., Boncz, P., Kemper, A., & Neumann, T. Proceedings of the VLDB Endowment (2016), 9(3), 204–215.* [[paper](https://doi.org/10.14778/2850583.2850594)]

**Neo: A Learned query optimizer** ![](https://img.shields.io/badge/RL-blue) 

*Marcus, R., Negi, P., Mao, H., Zhang, C., Alizadeh, M., Kraska, T., … Tatbul, N. (2018). Proceedings of the VLDB Endowment*, *12*(11), 1705–1718, 2018. [[paper](https://doi.org/10.14778/3342263.3342644)]

**Deep reinforcement learning for join order enumeration**

*Marcus, R., & Papaemmanouil, O. (2018). Proceedings of the 1st International Workshop on Exploiting Artificial Intelligence Techniques for Data Management, AiDM 2018*, 0–3. [[paper](https://doi.org/10.1145/3211954.3211957)]

**SkinnerDB : Regret-Bounded Query Evaluation via Reinforcement Learning** ![](https://img.shields.io/badge/MCTS-blue) 

*Trummer, I., Wang, J., Maram, D., Moseley, S., Jo, S., & Antonakakis, J. (n.d.). SIGMOD, 2019.* [[paper](https://arxiv.org/abs/1901.05152)]

**Progressive Join Algorithms Considering User Preference**

*Ding, M., Chen, S., & Manegold, S. (2021). CIDR, 2021.* [[paper](http://cidrdb.org/cidr2021/papers/cidr2021_paper02.pdf)]

**Reinforcement Learning with Tree-LSTM for Join Order Selection**

*Yu, X., Li, G., Tang, N. (n.d.). ICDE, 2020.* [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/icde2020-learnedjoinorder.pdf)]

**Towards a Learning Optimizer for Shared Clouds**

*Chenggang Wu, Alekh Jindal, Saeed Amizadeh, Hiren Patel, Wangchao Le, Shi Qiao, Sriram Rao. Proc. VLDB Endow. 12(3): 210-222, 2018.* [[paper](http://www.vldb.org/pvldb/vol12/p210-wu.pdf)]

**SQL Plan Observability through Hints in Oracle Autonomous Database**

*Pasupuleti, K., Park, M., & Valluri, S. (n.d.).*

**Bao: Making Learned Query Optimization Practical** ![](https://img.shields.io/badge/optimizer_knobs-blue) 

*Marcus, R., Negi, P., Mao, H., Tatbul, N., Alizadeh, M., & Kraska, T. (2020). SIGMOD, 2021.* [[paper](https://doi.org/10.1145/3448016.3452838)]

**Steering Query Optimizers: A Practical Take on Big Data Workloads**

*Parimarjan Negi, Matteo Interlandi, Ryan Marcus, Mohammad Alizadeh, Tim Kraska, Marc Friedman, Alekh Jindal. SIGMOD, 2021.* [[paper](https://doi.org/10.1145/3448016.3457568)]

**SkinnerMT: Parallelizing for Efficiency and Robustness in Adaptive Query Processing on Multicore Platforms**

*Ziyun Wei, Immanuel Trummer. PVLDB, 2022.* [[paper](https://www.vldb.org/pvldb/vol16/p905-wei.pdf)]

**Learning a Query Optimizer Without Expert Demonstrations**

*Zongheng Yang, Wei-Lin Chiang, Sifei Luan, Gautam Mittal, Michael Luo, Ion Stoica. Balsa. SIGMOD, 2022*  [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3517885)]

**Workload-driven, Lazy Discovery of Data Dependencies for Query Optimization**

*Jan Kossmann. CIDR, 2022* [[paper](https://www.cidrdb.org/cidr2022/papers/p70-kossmann.pdf)]

**LOGER: A Learned Optimizer towards Generating Efficient and Robust Query Execution Plans** ![](https://img.shields.io/badge/gnn-blue) 

*Tianyi Chen, Jun Gao, Hedui Chen, and Yaofeng Tu. PVLDB, 2023.* [[paper](https://www.vldb.org/pvldb/vol16/p1777-gao.pdf)]

**BASE: Bridging the Gap between Cost and Latency for Query Optimization** ![](https://img.shields.io/badge/hybrid_cost_latency-blue) 

*Chen, Xu, Zhen Wang, Shuncheng Liu, et al.* [[paper](https://zheng-kai.com/paper/vldb_2023_chen.pdf)]

**COOOL: A Learning-To-Rank Approach for SQL Hint Recommendations** ![](https://img.shields.io/badge/relative_cost-blue) 

*Xu, Xianghong, Zhibing Zhao, Tieying Zhang, et al.* [[paper](https://arxiv.org/pdf/2304.04407.pdf)]

**Lero: A Learning-to-Rank Query Optimizer** ![](https://img.shields.io/badge/rank-blue) 

*Rong Zhu, Wei Chen, Bolin Ding, Xingguang Chen, Andreas Pfadler, Ziniu Wu, Jingren Zhou. VLDB 2023.* [[paper](https://www.vldb.org/pvldb/vol16/p1466-zhu.pdf)]

**Cost-based or Learning-based? A Hybrid Query Optimizer for Query Plan Selection** ![](https://img.shields.io/badge/uncertainty-blue) 

*Xiang Yu, Chengliang Chai, Guoliang Li, Jiabin Liu. VLDB 2023.* [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/optimizer-vldb23.pdf)]

**Leveraging Query Logs and Machine Learning for Parametric Query Optimization** 

*Kapil Vaidya, Anshuman Dutt, Vivek Narasayya, Surajit Chaudhuri. VLDB 2022.* [[paper](https://dl.acm.org/doi/pdf/10.14778/3494124.3494126)]

**Kepler: Robust Learning for Parametric Query Optimization** ![](https://img.shields.io/badge/perturbation-blue) 

*Lyric Doshi, Vincent Zhuang, Gaurav Jain, Ryan C Marcus, Haoyu Huang, Deniz Altınbüken, Eugene Brevdo, Campbell Fraser. SIGMOD 2023.*[[paper](https://dl.acm.org/doi/10.1145/3588963)]

**LEON: A New Framework for ML-Aided Query Optimization** ![](https://img.shields.io/badge/ML--aided-blue)

*Xu Chen, Haitian Chen, Zibo Liang, Shuncheng Liu, Jinghong Wang, Kai Zeng, Han Su, and Kai Zheng.*[[paper](https://www.vldb.org/pvldb/vol16/p2261-chen.pdf)]

## 3. Workload Scheduling

Ibrahim Sabek, Tenzin Samten Ukyab, Tim Kraska. *LSched: A Workload-Aware Learned Query Scheduler for Analytical Database Systems*. SIGMOD, 2022. [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3526158)] 

Chi Zhang, Ryan Marcus, and et al. Buffer Pool Aware Query Scheduling via Deep Reinforcement Learning. In VLDB, 2020. [[paper](https://arxiv.org/pdf/2007.10568.pdf)] 


## 4. Database Design

### Index
#### One-dimensional Index

**[1-D, Immutable]** Kraska, T., Beutel, A., Chi, E. H., Dean, J., & Polyzotis, N. (2018). *The case for learned index structures*. SIGMOD, 2018. [[paper](https://dl.acm.org/doi/10.1145/3183713.3196909)] [[code](https://github.com/learnedsystems/RMI/tree/5fdff45d0929beaccf6bc56f8f4c0d82baf10304)]

**[1-D, Mutable]** Galakatos, A., Markovitch, M., Binnig, C., Fonseca, R., & Kraska, T. (2019). *Fiting-tree: A data-aware index structure*. SIGMOD, 2019. [[paper](https://dl.acm.org/doi/abs/10.1145/3299869.3319860)]

**[1-D, Mutable, Secondary]** Wu, Y., Yu, J., Tian, Y., Sidle, R., Barber, R. (2019). *Designing succinct secondary indexing mechanism by exploiting column correlations*. SIGMOD 2019. [[paper](https://dl.acm.org/doi/pdf/10.1145/3299869.3319861)]

**[1-D, Mutable]** Ferragina, P., & Vinciguerra, G. (2020). *The PGM-index : a fully-dynamic compressed learned index with provable worst-case bounds*. VLDB, 2020. [[paper](https://dl.acm.org/doi/abs/10.14778/3389133.3389135)]

**[1-D, Mutable]** Ding, J., Minhas, U. F., Yu, J., Wang, C., Do, J., Li, Y., Zhang, H., Chandramouli, B., Gehrke, J., Kossmann, D., Lomet, D., & Kraska, T. (2020). *ALEX: An Updatable Adaptive Learned Index*. SIGMOD, 2020. [[paper](https://dl.acm.org/doi/10.1145/3318464.3389711)] [[code](https://github.com/microsoft/ALEX)]

**[1-D, Mutable, Persistent]** Lu, B., Ding, J., Lo, E., Minhas, U. F., & Wang, T. (2021). *APEX: A High-Performance Learned Index on Persistent Memory*. VLDB, 2021. [[paper](https://doi.org/10.14778/3494124.3494141)]

**[1-D, Immutable, Auto-generated]** Dittrich, J., Nix, J., & Schön, C. (2021). *The next 50 Years in Database Indexing or: The Case for Automatically Generated Index Structures*. VLDB, 2021. [[paper](https://doi.org/10.14778/3494124.3494136)] [[code](https://github.com/BigDataAnalyticsGroup/GENE)]

**[1-D, Mutable, Concurrency]** Li, P., Hua, Y., Jia, J., Zuo, P. (2021). *FINEdex: A Fine-grained Learned Index Scheme for Scalable and Concurrent Memory Systems*. VLDB, 2021. [[paper](https://www.vldb.org/pvldb/vol15/p321-hua.pdf)]

**[1-D, Mutable]** Wu, J., Zhang, Y., Chen, S., Wang, J., Chen, Y., Xing, C. (2021). *Updatable learned index with precise positions*. VLDB, 2021. [[paper](http://vldb.org/pvldb/vol14/p1276-wu.pdf)]

**[1-D, Mutable]** Ma, C., Yu, X., Li, Y., Meng, X., & Maoliniyazi, A. (2022). *FILM: A Fully Learned Index for Larger-Than-Memory Databases*. VLDB, 2022. [[paper](https://dl.acm.org/doi/pdf/10.14778/3570690.3570704)]

**[1-D, Mutable, Concurrency]** Wang, Z., Chen, H., Wang, Y., & Tang, C. (2022). *The Concurrent Learned Indexes for Multicore Data Storage*. ACM Transactions on Storage, 18(1), 1-35. [[paper](https://dl.acm.org/doi/pdf/10.1145/3478289)] [[code](https://ipads.se.sjtu.edu.cn:1312/opensource/xindex.git)]

**[1-D, Mutable]** Jiaoyi Zhang, Yihan Gao. (2022). *CARMI: A Cache-Aware Learned Index with a Cost-based Construction Algorithm*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p2679-gao.pdf)]

**[1-D, Mutable]** Shangyu Wu. (2022). *NFL: Robust Learned Index via Distribution Transformation*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p2188-wu.pdf)]

**[1-D, Mutable, Persistent]** Zhang, Z., Chu, Z., Jin, P., Luo, Y., Xie, X., Wan, S., Luo, Y., Wu, X., Zou, P., Zheng, C., Wu, G., Rudoff. A. (2022). *PLIN: A Persistent Learned Index for Non-Volatile Memory with High Performance and Instant Recovery*. VLDB, 2022. [[paper](https://doi.org/10.14778/3565816.3565826)]

**[1-D, Mutable]** Li, Pengfei, Hua Lu, Rong Zhu, Bolin Ding, et al. (2023). *DILI: A Distribution-Driven Learned Index*. VLDB, 2023. [[paper](https://arxiv.org/pdf/2304.08817.pdf)]

**[1-D, Mutable, Persistent]** Yulai Tong, Jiazhen Liu, Hua Wang, Ke Zhou, Rongfeng He, Qin Zhang, and Cheng Wang. (2023). *Sieve: A Learned Data-Skipping Index for Data Analytics*. VLDB, 2023. [[paper](https://dl.acm.org/doi/pdf/10.14778/3611479.3611520)]

#### Multi-dimensional Index

**[Multi-D, Immutable]** Nathan, V., Ding, J., Alizadeh, M., & Kraska, T. (2020). *Learning multi-dimensional indexes*. SIGMOD, 2020. [[paper](https://dl.acm.org/doi/10.1145/3318464.3380579)]

**[Multi-D, Mutable, Persistent]** Li, P., Lu, H., Zheng, Q., Yang, L., & Pan, G. (2020). *LISA: A Learned Index Structure for Spatial Data*. SIGMOD, 2020. [[paper](https://doi.org/10.1145/3318464.3389703)]

**[Multi-D, Mutable, Persistent]** Qi, J., Liu, G., Jensen, C.S., Kulik, L. (2020). *Effectively learning spatial indices*. VLDB, 2020. [[paper](http://www.vldb.org/pvldb/vol13/p2341-qi.pdf)]

**[Multi-D, Immutable]** Ding, J., Nathan, V., Alizadeh, M., & Kraska, T. (2020). *Tsunami: A learned multi-dimensional index for correlated data and skewed workloads*. VLDB, 2020. [[paper](https://dl.acm.org/doi/abs/10.14778/3425879.3425880)]

**[Multi-D, Mutable]** Dong, H., Chai, C., Luo, Y., Liu, J., Feng, J., Zhan, C. (2022). *RW-Tree: A Learned Workload-aware Framework for R-tree Construction*. ICDE, 2022. [[paper](https://doi.org/10.1109/ICDE53745.2022.00201)]

**[Multi-D, Immutable]** Gao, J., Cao, X., Yao, X., Zhang, G., & Wang, W. (2023). *LMSFC: A Novel Multidimensional Index based on Learned Monotonic Space Filling Curves*. VLDB, 2023. [[paper](https://arxiv.org/pdf/2304.12635.pdf)]

#### Experiment and Analysis

**[1-D, Immutable, Analysis]** Ferragina, P., Lillo, F., & Vinciguerra, G. (2020). *Why are learned indexes so effective?*. ICML, 2020. [[paper](http://proceedings.mlr.press/v119/ferragina20a/ferragina20a.pdf)]

**[1-D, Immutable, Experiment]** Marcus, R., Stoian, M., Kipf, A., Misra, S., van Renen, A., Kemper, A., Neumann, T., & Kraska, T. (2020). *Benchmarking learned indexes*. VLDB, 2020. [[paper](https://dl.acm.org/doi/10.14778/3421424.3421425)] [[code](https://github.com/learnedsystems/SOSD)]

**[1-D, Poisoning Attack]** Evgenios M. Kornaropoulos, Silei Ren, Roberto Tamassia. (2022). *The Price of Tailoring the Index to Your Data: Poisoning Attacks on Learned Index Structures*. SIGMOD, 2022. [[paper](https://dl.acm.org/doi/abs/10.1145/3514221.3517867)]

**[1-D, Mutable, Experiment]** Wongkham, C., Lu, B., Liu, C., Zhong, Z., Lo, E., Wang, T. (2022). *Are Updatable Learned Indexes Ready?*. VLDB, 2022. [[paper](https://doi.org/10.14778/3551793.3551848)]

**[1-D, Immutable, Experiment]** Maltry, M., Dittrich, J. (2022). *A critical analysis of recursive model indexes*. VLDB, 2022. [[paper](https://doi.org/10.14778/3510397.3510405)]

**[1-D, Hash Index, Experiment]** Sabek, I., Vaidya, K., Horn TUM, D., Kipf, A., Mitzenmacher, M., Kraska, T., Horn, D., Kraska Can, T. (2022) *Can Learned Models Replace Hash Functions?*. VLDB, 2022. [[paper](https://doi.org/10.14778/3570690.3570702)]

**[1-D, Mutable, Experiment]** Sun, Z., Zhou, X., Li, G. (2023). *Learned Index: A Comprehensive Experimental Evaluation*. VLDB, 2023. [[paper](https://dl.acm.org/doi/pdf/10.14778/3594512.3594528)] [[code](https://github.com/curtis-sun/TLI)]

**[1-D, Immutable, Experiment]** Sabek, I., & Kraska, T. (2023). *The Case for Learned In-Memory Joins*. VLDB, 2023. [[paper](https://arxiv.org/pdf/2111.08824.pdf)]

### Layout

**[Learned Layout]** Liwen Sun, Michael J. Franklin, Sanjay Krishnan, et al. *Fine-grained partitioning for aggressive data skipping*. SIGMOD, 2014. [[paper](https://doi.org/10.1145/2588555.2610515)]

**[Learned Layout]** Yang, Z., Chandramouli, B., Wang, C., Gehrke, J., Li, Y., Minhas, U. F., … Acharya, R. (n.d.). *Qd-tree: Learning Data Layouts for Big Data Analytics*. SIGMOD, 2020. [[paper](https://doi.org/10.1145/3318464.3389770)]

**[Learned Layout]** Jialin Ding, Umar Farooq Minhas, Badrish Chandramouli, et al. *Instance-Optimized Data Layouts for Cloud Analytics Workloads*. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3457270)]

**[Data Container]** Madden S, Ding J, Kraska T, Sudhir S, Cohen D, Mattson T, Tatbul N. *Self-Organizing Data Containers*. CIDR, 2022. [[paper](https://www.cidrdb.org/cidr2022/papers/p44-madden.pdf)]

**[Learned Layout]** Teng Zhang, Jian Tan, Xin Cai, Jianying Wang, Feifei Li, Jianling Sun. *SA-LSM : Optimize Data Layout for LSM-tree Based Storage using Survival Analysis*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p2161-zhang.pdf)]

**[Learned Layout]** Michael Abebe. *Tiresias: Enabling Predictive Autonomous Storage and Indexing*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p3126-abebe.pdf)]

### Query Execution

**[Scheduling]** Zhang, C., Marcus, R., Kleiman, A., & Papaemmanouil, O. (2020). *Buffer Pool Aware Query Scheduling via Deep Reinforcement Learning*. AIDB@VLDB, 2020. [[paper](https://arxiv.org/abs/2007.10568)]

**[Operators]** Bandle, M., Giceva, J., & Neumann, T. (2021). *To Partition, or Not to Partition, That is the Join Question in a Real System*. SIGMOD, 2021. [[paper](https://doi.org/10.1145/3448016.3452831)]

**[CodeGen]** Immanuel Trummer. *CodexDB: Synthesizing Code for Qery Processing from Natural Language Instructions using GPT-3 Codex*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p2921-trummer.pdf)]


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

### System and Kernel Causes

**Automatic Performance Diagnosis and Tuning in Oracle**

*Karl Dias, Mark Ramacher, Uri Shaft, et al. CIDR, 2005.* [[paper](https://www.cidrdb.org/cidr2005/papers/P07.pdf)]


**DBSherlock: A Performance Diagnostic Tool for Transactional Databases.**

*Yoon, D. Y., Niu, N., & Mozafari, B. SIGMOD, 2016.*  [[paper](https://web.eecs.umich.edu/~mozafari/php/data/uploads/sigmod_2016.pdf)]


**iQCAR: inter-Query Contention Analyzer for Data Analytics Frameworks.**

*Kalmegh, P., Babu, S., & Roy, S. SIGMOD, 2019.*  [[paper](https://users.cs.duke.edu/~sudeepa/papers/SIGMOD2019-iqcar.pdf)]


**FluxInfer: Automatic Diagnosis of Performance Anomaly for Online Database System**

*Ping Liu, Shenglin Zhang, Yongqian Sun, et al. IPCCC, 2020.* [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9391550)]


**Diagnosing Root Causes of Intermittent Slow Queries in Cloud Databases.**

*Minghua Ma, Zheng Yin, Shenglin Zhang, et al. VLDB, 2020.*  [[paper](http://www.vldb.org/pvldb/vol13/p1176-ma.pdf)]


**Generic and Robust Performance Diagnosis via Causal Inference for OLTP Database Systems.**

*Xianglin Lu, Zhe Xie, Zeyan Li, et al. CCGrid, 2022.*  [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9826016)]


**DBPA: A Benchmark for Transactional Database Performance Anomalies.**

*Shiyue Huang,Ziwei Wang, Xinyi Zhang, et al. SIGMOD, 2023.*  [[paper](https://dl.acm.org/doi/abs/10.1145/3588926)]

### Bottleneck Queries

**PinSQL: Pinpoint Root Cause SQLs to Resolve Performance Issues in Cloud Databases.** 

*Xiaoze Liu, Zheng Yin, Chao Zhao, et al. ICDE, 2022.*  [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9835371)]

## 7. General Techniques

### Feature Engineering for DB

**[PlanEncoding]** Yue Zhao, Gao Cong, Jiachen Shi, Chunyan Miao. *QueryFormer: A Tree Transformer Model for Query Plan Representation*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p1658-zhao.pdf)]

**[Plan2Feature]** Debjyoti Paul, Jie Cao, Feifei Li, Vivek Srikumar. *Database Workload Characterization with Query Plan Encoders*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p923-paul.pdf)]

**[Pretrained Representation]** Xiu Tang, Sai Wu, Mingli Song, Shanshan Ying, Feifei Li, Gang Chen: *PreQR: Pre-training Representation for SQL Understanding*. SIGMOD Conference 2022: 204-216 [[paper](https://dl.acm.org/doi/abs/10.1145/3514221.3517878)]

**[WorkloadAsGraph]** Sanjay Agrawal, Eric Chu, Vivek R. Narasayya. Automatic physical design tuning: workload as a sequence. SIGMOD, 2006. [[paper](https://doi.org/10.1145/1142473.1142549)]

**[DataSummary]** Brit Youngmann et al. *Guided Exploration of Data Summaries*. VLDB, 2022. [[paper](https://www.vldb.org/pvldb/vol15/p1798-youngmann.pdf)]

Jiang H, Liu C, Paparrizos J, et al. Good to the Last Bit: Data-Driven Encoding with CodecDB. SIGMOD 2021. [[paper](https://dl.acm.org/doi/pdf/10.1145/3448016.3457283?casa_token=NVcav-WiJuwAAAAA:iYwHvshbC43qeBpObX4d7UYndrtqsfgE2FkI2Pkx43r59YCZJjsvm1C0Qv-M_oESKhZicbJLTIi0WsI)] 


### Feature Engineering for AI

**Apache flink: Stream and batch processing in a single engine[J].** ![](https://img.shields.io/badge/-feature_extraction-green)

*Carbone P, Katsifodimos A, Ewen S, et al.  The Bulletin of the Technical Committee on Data Engineering, 2015, 38(4).* [[paper](https://asterios.katsifodimos.com/assets/publications/flink-deb.pdf)]

**Feature selection in machine learning: A new perspective[J/OL].** ![](https://img.shields.io/badge/-feature_selection-yellow)

*CAI J, LUO J, WANG S et al.  Neurocomputing (Amsterdam), 2018, 300: 70-79. DOI:10.1016/j.neucom.2017.11.077.* [[paper](https://www.sciencedirect.com/science/article/abs/pii/S0925231218302911)]

**Optimizing in-memory database engine for AI-powered on-line decision augmentation using persistent memory.** ![](https://img.shields.io/badge/-feature_extraction-green)

*Cheng Chen, Jun Yang, Mian Lu, Taize Wang, Zhao Zheng, Yuqiang Chen, Wenyuan Dai, Bingsheng He, Weng-Fai Wong, Guoan Wu, Yuping Zhao, and Andy Rudoff. 2021.  Proc. VLDB Endow. 14, 5 (January 2021), 799–812.* [[paper](https://doi.org/10.14778/3446095.3446102)]

**Managing ML pipelines: feature stores and the coming wave of embedding ecosystems[J].** ![](https://img.shields.io/badge/-fe_for_embedding-red)

*Orr L, Sanyal A, Ling X, et al.  arXiv preprint arXiv:2108.05053, 2021.* [[paper](https://arxiv.org/pdf/2108.05053.pdf)]

**A System for Time Series Feature Extraction in Federated Learning.** ![](https://img.shields.io/badge/-fe_for_federated_learning-blue)

*Siqi Wang, Jiashu Li, Mian Lu, Zhao Zheng, Yuqiang Chen, and Bingsheng He. 2022.  In Proceedings of the 31st ACM International Conference on Information & Knowledge Management (CIKM '22). Association for Computing Machinery, New York, NY, USA, 5024–5028.* [[paper](https://doi.org/10.1145/3511808.3557176)]

**FEBench: A Benchmark for Real-Time Relational Data Feature Extraction.** ![](https://img.shields.io/badge/-benchmark-purple)

*Xuanhe Zhou, Cheng Chen, Kunyi Li, Bingsheng He, Mian Lu, Qiaosheng Liu, Wei Huang, Guoliang Li, Zhao Zheng, Yuqqiang Chen. 2023. Proc. VLDB Endow.* [[paper](https://github.com/decis-bench/febench/blob/main/report/febench.pdf)]


### Model Transfer

Meghdad Kurmanji, Peter Triantafillou. Detect, Distill and Update: Learned DB Systems Facing Out of Distribution Data. SIGMOD, 2023. [[paper](https://arxiv.org/pdf/2210.05508.pdf)]

### Query And Data Generation

#### Query Generation

L.Zhang, C.Chai, X.Zhou, and G.Li. Learned sqlgen: Constraint-aware sql generation using reinforcement learning. In SIGMOD, 2022. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/sigmod2022-sqlgen.pdf)]

Liu X, Kong X, Liu L, et al. TreeGAN: syntax-aware sequence generation with generative adversarial networks. In ICDM, 2018. [[paper](http://cn.liuleics.com/uploads/1/4/1/2/14126273/1808.07582.pdf)]

#### Data Generation

**[DeepAR]** Jingyi Yang, Peizhi Wu, Gao Cong, Tieying Zhang, Xiao He. *SAM: Database Generation from Query Workloads with Supervised Autoregressive Models*. SIGMOD, 2022. [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3526168)]

Francesco Ventura, Zoi Kaoudi, Jorge-Arnulfo Quiané-Ruiz, Volker Markl. Expand your training limits! Generating training data for ML-based data management. SIGMOD, 2021 [[paper](https://dl.acm.org/doi/pdf/10.1145/3448016.3457286)]

Ju Fan, Tongyu Liu, Guoliang Li, Yuwei Shen, Xiaoyong Du. Relational Data Synthesis using Generative Adversarial Networks: A Design Space Exploration. VLDB 2020. [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb2020-datagan.pdf)]


## 8. Database Frameworks

**Self-Driving Database Management Systems.** ![](https://img.shields.io/badge/-model_assembly-orange) 

*Andrew Pavlo, Gustavo Angulo, Joy Arulraj, et al. CIDR, 2017.* [[paper](https://www.pdl.cmu.edu/PDL-FTP/Database/p42-pavlo-cidr17.pdf)]


**Cloud native database systems at Alibaba: Opportunities and challenges.** ![](https://img.shields.io/badge/-learned_tuning-orange)  

*Feifei Li. VLDB, 2018.* [[paper](http://www.vldb.org/pvldb/vol12/p2263-li.pdf)]


**SageDB: A learned database system.** ![](https://img.shields.io/badge/-learned_CDFs-orange) 

*Tim Kraska, Mohammad Alizadeh, Alex Beutel, et al. CIDR, 2019.* [[paper](http://www.alexbeutel.com/papers/CIDR2019_SageDB.pdf)]


**MonetDBLite: An embedded analytical database.** 

*Mark Raasveldt. SIGMOD, 2018.* [[paper](https://mytherin.github.io/papers/2018-monetdblitecikm.pdf)]


**XuanYuan: An AI-Native Database.** ![](https://img.shields.io/badge/-model_assembly-blue)  

*Guoliang Li, Xuanhe Zhou, Sihao Li. Data Eng., 2019* [[paper](http://sites.computer.org/debull/A19june/p70.pdf)]


**DBMS Fitting: Why should we learn what we already know?** ![](https://img.shields.io/badge/-near_white_box_cost_model-blue)   

*Benjamin Hilprecht, Tiemo Bang, Muhammad El-Hindi, et al. CIDR, 2020.* [[paper](http://cidrdb.org/cidr2020/papers/p34-hilprecht-cidr20.pdf)]


**MB2 : Decomposed Behavior Modeling for Self-Driving Database Management Systems.** ![](https://img.shields.io/badge/-forecast_model_driven-orange)

*Lin Ma, William Zhang, Jie Jiao, et al. SIGMOD, 2021.* [[paper](https://dl.acm.org/doi/10.1145/3448016.3457276)]


**openGauss: An Autonomous Database System.** ![](https://img.shields.io/badge/-learned_models-orange)

*Guoliang Li, Xuanhe Zhou, Ji Sun, et al. VLDB, 2021.* [[paper](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb21-opengauss.pdf)]


**From Natural Language Processing to Neural Databases.** ![](https://img.shields.io/badge/-nlp_interface-orange) 

*James Thorne, Majid Yazdani, Marzieh Saeidi, et al. VLDB, 2021.* [[paper](http://www.vldb.org/pvldb/vol14/p1033-thorne.pdf)]


**One Model to Rule them All: Towards Zero-Shot Learning for Databases.** ![](https://img.shields.io/badge/-model_transfer-blue)

*Benjamin Hilprecht, Carsten Binnig. CIDR, 2022.* [[paper](https://www.cidrdb.org/cidr2022/papers/p16-hilprecht.pdf.)]


**A Unified Transferable Model for ML-Enhanced DBMS.** ![](https://img.shields.io/badge/-model_transfer-blue)

*Ziniu Wu, et al. CIDR, 2022.* [[paper](https://www.cidrdb.org/cidr2022/papers/p6-wu.pdf)]


**PerfGuard: Deploying ML-for-Systems without Performance Regressions, Almost!** ![](https://img.shields.io/badge/-model_validation-purple) 

*Remmelt Ammerlaan, Gilbert Antonius, Marc Friedman, et al. VLDB, 2022.* [[[paper](https://vldb.org/pvldb/vol14/p3362-hossain.pdf)]


**Database Gyms.** ![](https://img.shields.io/badge/-model_training-purple)

*Lim, Wan Shen, Matthew Butrovich, William Zhang, et al. CIDR, 2023.* [[paper](https://www.cidrdb.org/cidr2023/papers/p27-lim.pdf)]


**mutable: A Modern DBMS for Research and Fast Prototyping.** ![](https://img.shields.io/badge/-module_separation-green)

*Immanuel L Haffner, Jens Dittrich. CIDR, 2023.* [[paper](https://www.cidrdb.org/cidr2023/papers/p41-haffner.pdf)]


**SageDB: An Instance-Optimized Data Analytics System.** ![](https://img.shields.io/badge/-partial_MVs-orange)

*Jialin Ding, Ryan Marcus, Andreas Kipf, et al. VLDB, 2022.* [[paper](https://www.vldb.org/pvldb/vol15/p4062-ding.pdf)]



**Towards Building Autonomous Data Services on Azure.** ![](https://img.shields.io/badge/-auto_cloud_services-purple)

*Yiwen Zhu, Yuanyuan Tian, Joyce Cahoon, et al. SIGMOD, 2023.* [[paper](https://dl.acm.org/doi/pdf/10.1145/3555041.3589674)]

## 9. Demonstrations

**[DB Tuning]** Bohan Zhang, Dana Van Aken, Justin Wang, Tao Dai, Shuli Jiang, Jacky Lao, Siyuan Sheng, Andrew Pavlo, Geoffrey J. Gordon. *A Demonstration of the ottertune automatic database management system tuning service*. VLDB, 2018. [[paper](http://www.vldb.org/pvldb/vol11/p1910-zhang.pdf)]

**[O&M Platform]** Xuanhe Zhou, Lianyuan Jin, Ji Sun, Xinyang Zhao, Xiang Yu, Shifu Li, Tianqing Wang, Kun Li, luyang liu. *DBMind: A Self-Driving Platform in openGauss*. VLDB, 2021. [[paper](http://vldb.org/pvldb/vol14/p2743-zhou.pdf)] [[website](https://www.dbmind.cn/)] 

**[DB Tuning]** Junxiong Wang, Immanuel Trummer, Debabrota Basu. *Demonstrating UDO: A Unified Approach for Optimizing Transaction Code, Physical Design, and System Parameters via Reinforcement Learning*. SIGMOD, 2021. [[paper](https://dl.acm.org/doi/abs/10.1145/3448016.3452754)]

**[DB Tuning]** Immanuel Trummer. *Demonstrating DB-BERT: A Database Tuning Tool that "Reads" the Manual*. SIGMOD, 2022. [[paper](https://arxiv.org/pdf/2112.10925.pdf)]

**[DB Tuning]** Luming Sun, Tao Ji, Cuiping Li, Hong Chen. *DeepO: A Learned Query Optimizer*. SIGMOD, 2022. [[paper](https://dl.acm.org/doi/pdf/10.1145/3514221.3520167)]

**[DB Tuning]** Xuanhe Zhou, Guoliang Li, Jianming Wu, Jiesi Liu, Zhaoyan Sun, Xinning Zhang. *A Learned Query Rewrite System*. VLDB, 2023. [[paper](https://www.vldb.org/pvldb/vol16/p4110-li.pdf)] [[website](http://rewrite_demo.dbmind.cn/)]

**[DB Tuning]** Wei Zhou, Chen Lin, Xuanhe Zhou, Guoliang Li, Tianqing Wang. *Demonstration of ViTA: Visualizing, Testing and Analyzing Index Advisors.* CIKM, 2023. [[video](https://youtu.be/RfV4ylOxpcc)]

**[DB Tuning]** Qiushi Bai, Sadeem Alsudais, Chen Li. *Demo of QueryBooster: Supporting Middleware-based SQL Query Rewriting as a Service.* VLDB, 2023. [[paper](https://www.vldb.org/pvldb/vol16/p4038-bai.pdf)]

**[DB Tuning]** Christoph Anneser, Mario Petruccelli, Nesime Tatbul, David Cohen, Zhenggang Xu, Prithviraj Pandian, Nikolay Laptev, Ryan Marcus, and Alfons Kemper. *QO-Insight: Inspecting Steered Query Optimizers.* VLDB, 2023. [[paper](https://www.vldb.org/pvldb/vol16/p3922-anneser.pdf)]

**[DB Tuning]** Zilong Wang, Qixiong Zeng, Ning Wang, Haowen Lu, Yue Zhang. *CEDA: Learned Cardinality Estimation with Domain Adaptation.* VLDB, 2023. [[paper](https://www.vldb.org/pvldb/vol16/p3934-wang.pdf)]

**[DB Tuning]** Junxiong Wang, Immanuel Trummer, Ahmet Kara, Dan Olteanu. *ADOPT: Adaptively Optimizing Attribute Orders for Worst-Case Optimal Join Algorithms via Reinforcement Learning.* VLDB, 2023. [[paper](https://www.vldb.org/pvldb/vol16/p2805-wang.pdf)]

**[DB Tuning]** Immanuel Trummer. *Demonstrating GPT-DB: Generating Query-Specifc and Customizable Code for SQL Processing with GPT-4.* VLDB, 2023. [[paper](https://www.vldb.org/pvldb/vol16/p4098-trummer.pdf)]

**[DB Diagnosis]** Xiu Tang, Sai Wu, Dongxiang Zhang, Ziyue Wang, Gongsheng Yuan, and Gang Chen. *A Demonstration of DLBD: Database Logic Bug Detection System.* VLDB, 2023. [[paper](https://www.vldb.org/pvldb/vol16/p3914-wu.pdf)]


# *📧 Special Issues*

## S1 Large Language Models Meet Database

### Peer-Reviewed

**Annotating Columns with Pre-trained Language Models.** ![](https://img.shields.io/badge/-llm4db-Informational) ![](https://img.shields.io/badge/-data_augment-purple)

*Y Suhara, J Li, Y Li, D Zhang, Ç Demiralp, C Chen, WC Tan. SIGMOD 2022* [[paper](https://dl.acm.org/doi/abs/10.1145/3514221.3517906)]


**Can LLM Already Serve as A Database Interface? A BIg Bench for Large-Scale Database Grounded Text-to-SQLs.**  ![](https://img.shields.io/badge/text2sql-orange) 

   *Jinyang Li, Binyuan Hui, Ge Qu, et al. NeurIPS, 2023.* [[pdf](https://arxiv.org/pdf/2305.03111.pdf)].  


**Can Foundation Models Wrangle Your Data?** ![](https://img.shields.io/badge/data_cleaning-green)

  *Avanika Narayan, Ines Chami, Laurel Orr, and Christopher Ré. VLDB, 2023.* [[pdf](https://www.vldb.org/pvldb/vol16/p738-narayan.pdf)].


**OmniscientDB: A Large Language Model-Augmented DBMS That Knows What Other DBMSs Do Not Know.** ![](https://img.shields.io/badge/-model_augment-purple)

*M Urban, DD Nguyen, C Binnig. aiDM@SIGMOD 2023* [[paper](https://dl.acm.org/doi/abs/10.1145/3593078.3593933)]


**DB-GPT: Large Language Model Meets Database.** ![](https://img.shields.io/badge/query_optimization-purple) 

   *Xuanhe Zhou, Zhaoyan Sun, Guoliang Li. Data Science and Engineering 2023.* [[pdf](http://dbgroup.cs.tsinghua.edu.cn/ligl/papers/dbgpt-dse.pdf)].


**CatSQL: Towards Real World Natural Language to SQL Applications.** ![](https://img.shields.io/badge/text2SQL-blue)

*H Fu, C Liu, B Wu, F Li, J Tan, J Sun. VLDB 2023* [[paper](https://dl.acm.org/doi/abs/10.14778/3583140.3583165)]


**DeepJoin: Joinable Table Discovery with Pre-trained Language Models.** ![](https://img.shields.io/badge/-llm4db-Informational)

*Y Dong, C Xiao, T Nozawa, M Enomoto, M Oyamada. VLDB 2023* [[paper](https://arxiv.org/abs/2212.07588)]


**How Large Language Models Will Disrupt Data Management.** ![](https://img.shields.io/badge/data_management-green)

*RC Fernandez, AJ Elmore, MJ Franklin, S Krishnan, C Tan. VLDB 2023* [[paper](https://dl.acm.org/doi/abs/10.14778/3611479.3611527)]


**Demonstrating GPT-DB: Generating Query-Specific and Customizable Code for SQL Processing with GPT-4.** ![](https://img.shields.io/badge/-llm4db-Informational)

*I Trummer. VLDB 2023* [[paper](https://dl.acm.org/doi/abs/10.14778/3611540.3611630)]


**Can Large Language Models Predict Data Correlations from Column Names?** ![](https://img.shields.io/badge/-llm4db-Informational)

*I Trummer. VLDB 2023*


**From BERT to GPT-3 Codex: Harnessing the Potential of Very Large Language Models for Data Management.** ![](https://img.shields.io/badge/data_management-green)

*I Trummer. VLDB 2022* [[paper](https://arxiv.org/abs/2306.09339)]


**CodexDB: Synthesizing Code for Query Processing from Natural Language Instructions using GPT-3 Codex.** ![](https://img.shields.io/badge/-llm4db-Informational)

*I Trummer. VLDB 2022* [[paper](https://dl.acm.org/doi/abs/10.14778/3551793.3551841)]


**Analyzing How BERT Performs Entity Matching.** ![](https://img.shields.io/badge/data_management-green)

*M Paganelli, F Del Buono, A Baraldi, F Guerra. VLDB 2022* [[paper](https://iris.unimore.it/handle/11380/1291984)]


**Schema Matching using Pre-Trained Language Models.**![](https://img.shields.io/badge/-llm4db-Informational)

Y Zhang, A Floratou, J Cahoon, S Krishnan, AC Müller, D Banda, F Psallidas, JM Patel. ICDE 2023 [[paper](https://ieeexplore.ieee.org/abstract/document/10184612/)]


**DB-BERT: a Database Tuning Tool that "Reads the Manual".** ![](https://img.shields.io/badge/knob_tuning-blue)

*I Trummer. SIGMOD 2022* [[paper](https://dl.acm.org/doi/abs/10.1145/3514221.3517843)]


### Others


**Querying Large Language Models with SQL [Vision].**  ![](https://img.shields.io/badge/sql2res-red) 

*Mohammed Saeed, Nicola De Cao, Paolo Papotti. arXiv 2023.* [[pdf](https://arxiv.org/pdf/2304.00472.pdf)].  


**CAESURA: Language Models as Multi-Modal Query Planners.** ![](https://img.shields.io/badge/multi_mode-blue)

*Matthias Urban, Carsten Binnig. arXiv 2023.* [[pdf](https://arxiv.org/pdf/2308.03424.pdf)].  


**Towards Multi-Modal DBMSs for Seamless Querying of Texts and Tables.**   ![](https://img.shields.io/badge/multi_mode-blue) 

*Matthias Urban, Carsten Binnig. arXiv 2023.* [[pdf](https://arxiv.org/pdf/2304.13559.pdf)].  


**Multimodal Neural Databases.**   ![](https://img.shields.io/badge/multi_mode-blue) 

*Giovanni Trappolini, Andrea Santilli, Emanuele Rodolà, Alon Halevy, Fabrizio Silvestri. arXiv 2023.* [[pdf](https://arxiv.org/pdf/2305.01447.pdf)].  


**ChatDB: Augmenting LLMs with Databases AS Their Symbolic Memory.** ![](https://img.shields.io/badge/split_task_to_sqls-orange)

*Chenxu Hu, Jie Fu, Chenzhuang Du, Simian Luo, Junbo Zhao, Hang Zhao. arXiv 2023.* [[pdf](https://arxiv.org/pdf/2306.03901.pdf)].


**Chat2DB**  ![](https://img.shields.io/badge/text2sql-orange)  ![](https://img.shields.io/badge/query_optimization-purple) [[project](https://github.com/eosphoros-ai/DB-GPT)]


**From Large Language Models to Databases and Back A discussion on research and education.** ![](https://img.shields.io/badge/wide_discussion-blue) 

*Sihem Amer-Yahia, Angela Bonifati, Lei Chen, Guoliang Li, Kyuseok Shim, Jianliang Xu, Xiaochun Yang. arXiv 2023.* [[pdf](https://arxiv.org/pdf/2306.01388.pdf)]

**Table-GPT: Table-tuned GPT for Diverse Table Tasks.** ![](https://img.shields.io/badge/data_cleaning-green) 

*Peng Li, Yeye He, Dror Yashar, et al. arXiv 2023.* [[pdf](https://arxiv.org/pdf/2310.09263.pdf)] 


**Efficient Memory Management for Large Language Model Serving with PagedAttention.** ![](https://img.shields.io/badge/sys4llm-blue) 

*Woosuk Kwon, Zhuohan Li, Siyuan Zhuang, et al. arXiv 2023.* [[pdf](https://arxiv.org/abs/2309.06180)].


**PDFTriage: Question Answering over Long, Structured Documents.** ![](https://img.shields.io/badge/text_to_structured_data-blue)  

*Jon Saad-Falcon, Joe Barrow, Alexa Siu, et al. arXiv, 2023.* [[pdf](https://arxiv.org/pdf/2309.08872.pdf)].


**Automatic Root Cause Analysis via Large Language Models for Cloud Incidents.** ![](https://img.shields.io/badge/db_maintenance-purple) 

*Yinfang Chen, Huaibing Xie, Minghua Ma, et al. arXiv 2023.* [[pdf](https://arxiv.org/pdf/2305.15778.pdf)]


**LLM As DBA [Vision].** ![](https://img.shields.io/badge/db_maintenance-purple) *arXiv 2023.* [[pdf](https://arxiv.org/abs/2308.05481)].


**D-Bot: Database Diagnosis System using Large Language Models.** ![](https://img.shields.io/badge/db_maintenance-purple) 

*Xuanhe Zhou, Guoliang Li, Zhaoyan Sun, Zhiyuan Liu, Weize Chen, et al. arXiv 2023.* [[pdf](https://arxiv.org/pdf/2312.01454.pdf)] [[code](https://github.com/TsinghuaDatabaseGroup/DB-GPT)].


**GPTuner: A Manual-Reading Database Tuning System via GPT-Guided Bayesian Optimization.** ![](https://img.shields.io/badge/knob_tuning-blue)  

*Jiale Lao, Yibo Wang, Yufei Li, et al. arXiv, 2023.* [[pdf](https://web1.arxiv.org/pdf/2311.03157.pdf)] [[code](https://github.com/SolidLao/GPTuner)]

**DBCopilot: Scaling Natural Language Querying to Massive Databases.**  ![](https://img.shields.io/badge/text2sql-orange)

*Tianshu Wang, Hongyu Lin, Xianpei Han, et al. arXiv, 2023.* [[pdf](https://arxiv.org/pdf/2312.03463.pdf)]

**LLM-SQL-Solver: Can LLMs Determine SQL Equivalence?**  ![](https://img.shields.io/badge/sql_equivalence-orange)

*Fuheng Zhao, Lawrence Lim, Ishtiyaque Ahmad, et al. arXiv, 2023.* [[pdf](https://arxiv.org/pdf/2312.10321.pdf)]

**OpsEval: A Comprehensive Task-Oriented AIOps Benchmark for Large Language Models** ![](https://img.shields.io/badge/db_maintenance-purple) 

*Yuhe Liu, Changhua Pei, Longlong Xu, et al. arXiv, 2023.* [[pdf](https://arxiv.org/pdf/2310.07637.pdf)]


## S2 AI Paper And Code List

**Partially Filtered NLP Papers** ![](https://img.shields.io/badge/paper_list-orange)  

*https://qinyuenlp.com/read/*


**Prompt Engineering for LLMs** ![](https://img.shields.io/badge/paper_list-orange)  

*https://www.promptingguide.ai/papers*


**Deployed AI Algorithms** ![](https://img.shields.io/badge/program_list-orange)  

*https://github.com/labmlai/annotated_deep_learning_paper_implementations*

**LLM Statistics**

*https://aistratagems.com/large-language-model-llm-statistics/*


**Brain in a Vat: On Missing Pieces Towards Artificial General Intelligence in Large Language Models**  ![](https://img.shields.io/badge/benchmark-orange)

*Yuxi Ma, Chi Zhang, Song-Chun Zhu. arXiv 2023.* [[pdf](https://arxiv.org/pdf/2307.03762.pdf)].


## S3 Open Datasets And SQLs

[https://github.com/cmu-db/benchbase](https://github.com/cmu-db/benchbase)

[https://github.com/cwida/public_bi_benchmark/tree/dev/master](https://github.com/cwida/public_bi_benchmark/tree/dev/master)

[https://github.com/TsinghuaDatabaseGroup/datasets](https://github.com/TsinghuaDatabaseGroup/datasets)

