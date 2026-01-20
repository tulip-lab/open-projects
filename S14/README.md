[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](README.md)

# Model Stealing Attacks in Reinforcement Learning

**Project Code:** S14  
**Track:** Security × Artificial Intelligence  
**Revision:** Q1, 2024  

---

## 1. Project Background

Deep learning models, including reinforcement learning (RL) policies, are increasingly deployed as black-box services through APIs in domains such as autonomous driving, robotics, recommender systems, and decision-support systems. While black-box deployment mitigates the risk of direct parameter leakage, **model behavior itself remains a critical attack surface**.

By querying a deployed policy and observing its outputs, attackers may reconstruct a substitute model that is functionally equivalent or closely approximates the target policy. Such **model stealing attacks** allow adversaries to replicate proprietary systems without access to training data or parameters, and can further enable downstream attacks such as adversarial manipulation, system impersonation, or security circumvention.

Understanding and evaluating model stealing attacks against RL policies under realistic black-box settings is therefore of significant practical and security relevance  [oai_citation:1‡Topic 3.pdf](sediment://file_00000000a3e07206a5edcc5bce53a597).

---

## 2. Research Problems and State-of-the-Art Methods

Early model stealing attacks primarily relied on **distillation-based approaches**, which assume access to output probability distributions, and **imitation learning–based approaches**, which train substitute models from queried input–output pairs. While effective in controlled settings, these methods often assume that the attacker can freely interact with the RL environment or collect large amounts of interactive data.

This leads to a central research challenge:  
**How can a high-performance substitute policy be extracted under limited query budgets and realistic black-box constraints?**

Recent research addresses this challenge along two complementary directions.  
First, **query-efficient extraction** methods leverage active learning and strategic query selection to reduce the number of required interactions. Pal et al. demonstrated that model extraction can be framed as an active learning problem, significantly improving efficiency.  
Second, **environment-free model stealing** relaxes assumptions about adversarial capabilities. In particular, Stealthy Imitation enables policy extraction without access to the environment or prior knowledge of the input distribution by learning a reward model to guide imitation.

Building on these advances, this project investigates efficient and realistic model stealing attacks against RL policies.

---

## 3. Benchmark Environments

Experiments should be conducted on standard reinforcement learning benchmarks that support evaluation of policy performance and extraction efficiency.

**Atari Learning Environment (ALE)**  
A widely used benchmark consisting of diverse arcade games with shared visual dynamics but different reward structures. It is suitable for evaluating policy extraction across tasks.  
https://www.gymlibrary.dev/environments/atari/

**MuJoCo Control Tasks**  
Continuous control environments such as Hopper, Walker2d, and HalfCheetah, commonly used to evaluate RL algorithms in robotics-like settings. These environments are well suited for measuring expected cumulative reward of stolen policies.  
https://www.gymlibrary.dev/environments/mujoco/

---

## 4. Project Tasks

Students are expected to **design, implement, and evaluate a model stealing attack against reinforcement learning policies**. The project should be systematic and reproducible and include the following core tasks.

### 4.1 Baseline Model Stealing Implementation

Reproduce baseline model stealing attacks based on imitation learning or policy distillation using black-box query access.

### 4.2 Query-Efficient Extraction Strategy

Design or implement a query-efficient extraction method using active learning or strategic sample selection to reduce query costs.

### 4.3 Environment-Free Policy Stealing

Implement or analyze environment-free policy stealing approaches, such as reward-guided imitation, and compare them with environment-dependent methods.

### 4.4 Comparative Evaluation

Compare different extraction strategies in terms of query efficiency and stolen policy performance under identical experimental settings.

---

## 5. Evaluation Metrics

| Metric | Description | Purpose |
|------|------------|---------|
| Query Cost | Number of queries required to reach a performance threshold | Attack efficiency |
| Expected Cumulative Reward | Performance of the stolen policy on the original environment | Attack effectiveness |
| Performance Gap | Reward difference between stolen and target policies | Fidelity assessment |

---

## 6. Expected Outcomes

By completing this project, students will gain hands-on experience with black-box attacks against reinforcement learning systems. Expected outcomes include a reproducible model stealing pipeline, empirical insights into query–performance trade-offs, and a deeper understanding of intellectual property and security risks in deployed RL services. The project contributes to research on secure and trustworthy reinforcement learning.

---

## 7. References


[1] K. Chen, S. Guo, T. Zhang, X. Xie, and Y. Liu, *Stealing Deep Reinforcement Learning Models for Fun and Profit*, ACM AsiaCCS 2021, https://dl.acm.org/doi/10.1145/3433210.3453090   

[2] F. Tramèr, F. Zhang, A. Juels, M. K. Reiter, and T. Ristenpart, *Stealing Machine Learning Models via Prediction APIs*, 25th USENIX Security Symposium 2016, https://www.usenix.org/system/files/conference/usenixsecurity16/sec16_paper_tramer.pdf   

[3] S. Pal, Y. Gupta, A. Shukla, A. Kanade, S. Shevade, and V. Ganapathy, *ActiveThief: Model Extraction Using Active Learning and Unannotated Public Data*, AAAI Conference on Artificial Intelligence 2020, https://ojs.aaai.org/index.php/AAAI/article/view/5432    

[4] Z. Zhuang, M.-I. Nicolae, and M. Fritz, *Stealthy Imitation: Reward-Guided Environment-Free Policy Stealing*, arXiv:2405.07004, 2024, https://arxiv.org/abs/2405.07004   