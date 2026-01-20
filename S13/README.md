[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](../README.md#ledger-coursework-research--projects)

# Generalizable Backdoor Attacks in Reinforcement Learning

**Project Code:** S13  
**Track:** Security × Artificial Intelligence  
**Revision:** Q1, 2024  

---

## 1. Project Background

Backdoor attacks aim to implant hidden malicious behaviors into learning systems that are activated only under specific trigger conditions. While backdoor attacks have been extensively studied in supervised learning, recent work has shown that **reinforcement learning (RL) systems are also vulnerable to training-time backdoor poisoning**.

Early studies on RL backdoors demonstrate that malicious behaviors can be embedded by manipulating rewards, observations, or policy updates during training. However, many existing attacks rely on overly strong assumptions, such as full access to the Markov Decision Process (MDP) or handcrafted state-specific triggers. As a result, these attacks are tightly coupled to a single environment and exhibit **poor generalization across tasks and domains**.

This project focuses on **generalizable backdoor attacks in reinforcement learning**, aiming to design attack mechanisms that remain effective across different MDPs and tasks. Understanding such attacks is essential for assessing the real-world security risks of RL systems deployed in robotics, autonomous driving, and decision-making systems  [oai_citation:1‡Topic 2.pdf](sediment://file_00000000880472069761aab371a532be).

---

## 2. Research Problems and State-of-the-Art Methods

Most existing backdoor attacks in RL inject malicious behavior by manipulating one of the following components during training: reward signals, environment observations, or policy updates. These approaches typically assume strong control over the training environment and design triggers tied to specific states or observations, which severely limits generalization.

This motivates the central research question of this project:  
**How can backdoor attacks in reinforcement learning be designed to generalize across different MDPs?**

Recent advances attempt to decouple backdoor triggers from environment-specific states. **SleeperNets** learn trigger representations jointly with the policy and activate malicious behaviors when the policy enters particular internal representations, improving stealthiness and reducing reliance on explicit state triggers. **UniDoor** formalizes the problem of generalizable RL backdoors and proposes **action-level backdoor mechanisms**, where malicious behavior is activated in the action space rather than raw observations.

This project builds on these ideas and encourages exploration of backdoor generalization across domains and tasks.

---

## 3. Problem Formulation and Evaluation Setting

Given the diversity of RL tasks, a key challenge is defining meaningful notions of generalization. One common formulation categorizes problems into **domains** and **tasks**, where a domain is defined by shared environment dynamics and contains multiple tasks distinguished by task-specific reward functions.

Under this formulation, a backdoor attack is considered generalizable if it remains effective when transferred to unseen tasks within the same domain or across related domains. Students are encouraged to formalize and evaluate generalization along these dimensions.

---

## 4. Benchmark Environments

Experiments should be conducted on standard reinforcement learning benchmarks that support multi-task or multi-domain evaluation.

**Atari Learning Environment (ALE)**  
A widely used benchmark consisting of diverse arcade games with shared visual dynamics but distinct reward structures. Suitable for evaluating backdoor generalization across tasks within a domain.  
https://www.gymlibrary.dev/environments/atari/

**MuJoCo Control Tasks**  
Continuous control environments commonly used in RL research, such as Hopper, Walker2d, and HalfCheetah. These environments support evaluation across tasks with similar dynamics but different objectives.  
https://www.gymlibrary.dev/environments/mujoco/

**Custom Multi-Task Environments**  
Students may construct simplified multi-task environments with shared dynamics and varying reward functions to explicitly study backdoor transferability.

---

## 5. Project Tasks

Students are expected to **design, implement, and evaluate a generalizable backdoor attack in reinforcement learning**. The project should include the following core tasks.

### 5.1 Backdoor Design in Reinforcement Learning

Design a backdoor attack mechanism that can be injected during RL training without modifying the deployment environment.

### 5.2 Cross-Task Generalization Evaluation

Evaluate whether the injected backdoor remains effective when the trained policy is transferred to new tasks or environments.

### 5.3 Comparison with State-of-the-Art Attacks

Compare the proposed method with existing RL backdoor attacks, including reward-based, observation-based, and policy-level approaches.

### 5.4 Stealthiness Analysis

Analyze the impact of the backdoor on clean policy performance, ensuring that expected cumulative reward remains high in benign environments.

---

## 6. Evaluation Metrics

| Metric | Description | Purpose |
|------|------------|---------|
| Attack Success Rate (ASR) | Percentage of successful backdoor activations | Attack effectiveness |
| Expected Cumulative Reward | Policy performance on clean environments | Stealth assessment |
| Cross-Task ASR | ASR measured on unseen tasks | Generalization analysis |
| Performance Degradation | Reward drop under benign conditions | Detectability assessment |

---

## 7. Expected Outcomes

By completing this project, students will gain insight into how backdoor attacks can be made transferable in reinforcement learning. Expected outcomes include a reproducible generalizable RL backdoor attack, empirical analysis of cross-task transfer, and a deeper understanding of security risks in RL-based systems. The project contributes to the emerging field of secure and trustworthy reinforcement learning.

---

## 8. References

## References

[1] X. Zhang, Y. Ma, A. Singla, and X. Zhu, *Adaptive Reward-Poisoning Attacks against Reinforcement Learning*, ICML 2020, https://proceedings.mlr.press/v119/zhang20u.html  [oai_citation:0‡Proceedings of Machine Learning Research](https://proceedings.mlr.press/v119/zhang20u.html?utm_source=chatgpt.com)

[2] Y. Wu, J. McMahan, X. Zhu, and Q. Xie, *Reward Poisoning Attacks on Offline Multi-Agent Reinforcement Learning*, arXiv:2206.01888, 2022, https://arxiv.org/abs/2206.01888  [oai_citation:1‡arXiv](https://arxiv.org/abs/2206.01888?utm_source=chatgpt.com)

[3] J. Cui, Y. Han, Y. Ma, J. Jiao, and J. Zhang, *BadRL: Sparse Targeted Backdoor Attack Against Reinforcement Learning*, AAAI 2024, https://arxiv.org/abs/2312.12585  [oai_citation:2‡arXiv](https://arxiv.org/abs/2312.12585?utm_source=chatgpt.com)

[4] Y. Ma, X. Zhang, W. Sun, and J. Zhu, *Policy Poisoning in Batch Reinforcement Learning and Control*, NeurIPS 2019, https://papers.nips.cc/paper/2019/hash/53f5c77c3c0f2a8fbd4b8b2c0fbd6f05-Abstract.html  [oai_citation:3‡Proceedings of Machine Learning Research](https://proceedings.mlr.press/v119/zhang20u.html?utm_source=chatgpt.com)

[5] E. Rathbun, C. Amato, and A. Oprea, *SleeperNets: Universal Backdoor Poisoning Attacks Against Reinforcement Learning Agents*, NeurIPS 2024, https://arxiv.org/abs/2405.20539  [oai_citation:4‡arXiv](https://arxiv.org/abs/2405.20539?utm_source=chatgpt.com)

[6] O. Ma, L. Du, Y. Dai, C. Zhou, Q. Li, Y. Pu, and S. Ji, *UNIDOOR: A Universal Framework for Action-Level Backdoor Attacks in Deep Reinforcement Learning*, arXiv:2501.15529, 2025, https://arxiv.org/abs/2501.15529  [oai_citation:5‡arXiv](https://arxiv.org/abs/2501.15529?utm_source=chatgpt.com)

[7] F. Liu, H. Liu, A. Grover, and P. Abbeel, *Masked Autoencoding for Scalable and Generalizable Decision Making*, NeurIPS 2022,  https://arxiv.org/abs/2211.12740