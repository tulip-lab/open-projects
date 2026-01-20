[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](../README.md#ledger-coursework-research--projects)

# Safety-Critical Scenario Generation in Autonomous Driving via Adversarial Reinforcement Learning

**Project Code:** S12 
**Track:** Security × Artificial Intelligence  
**Revision:** Q1, 2024  

---

## 1. Project Background

Ensuring reliable performance under safety-critical scenarios is a central challenge in the deployment of autonomous driving systems. Safety-critical scenarios refer to situations in which autonomous vehicles face a high probability of collision with other road users, making such scenarios essential for exposing latent weaknesses in perception, planning, and decision-making modules.

However, collecting sufficient safety-critical data through real-world driving is impractical. Empirical studies report that safety-critical events occur only once every tens of thousands of kilometers of driving, rendering large-scale on-road data collection prohibitively expensive and time-consuming. As a result, **simulation-based generation of safety-critical scenarios** has become a key approach for evaluating and validating autonomous driving systems.

This project focuses on **adversarial reinforcement learning (RL)** for safety-critical scenario generation, where adversarial agents interact with an ego vehicle to automatically discover failure cases that are difficult to observe in naturalistic driving data.

---

## 2. Research Problems and State-of-the-Art Methods

Existing scenario generation methods broadly fall into two categories. Data-driven approaches learn generative models from large-scale driving datasets, while knowledge-driven approaches rely on expert-defined rules, constraints, or ontologies. Although both approaches are effective in certain settings, they often struggle to uncover rare and highly safety-critical corner cases.

More recently, **adversarial scenario generation** has emerged as a promising paradigm. By formulating the interaction between the ego vehicle and surrounding traffic participants as a zero-sum or competitive game, reinforcement learning can be used to generate scenarios that actively exploit vulnerabilities in the ego vehicle’s policy.

Despite this progress, a key limitation of existing adversarial RL methods is their tendency to overemphasize adversariality at the expense of realism. Overly aggressive adversarial agents may produce physically implausible trajectories or behaviorally unrealistic interactions, which limits the value of generated scenarios for real-world validation. Balancing **adversarial effectiveness**, **physical realism**, and **generation efficiency** therefore remains a fundamental research challenge.

---

## 3. Benchmark Data and Evaluation Metrics

### 3.1 Benchmark Datasets

Experiments should be conducted on large-scale, publicly available trajectory datasets that support realistic traffic modeling and scenario replay.

**Waymo Open Motion Dataset**  
A large-scale real-world driving dataset containing over 100,000 driving segments with detailed annotations of vehicle, pedestrian, and cyclist trajectories. It provides diverse traffic interactions suitable for safety-critical scenario analysis.   

**HighD Dataset**  
A naturalistic vehicle trajectory dataset collected on German highways, covering over 110,000 vehicles across 60 recordings. HighD focuses on high-speed highway scenarios and is well suited for studying longitudinal and lateral safety-critical interactions.   

---

### 3.2 Evaluation Metrics

The effectiveness and practicality of generated safety-critical scenarios should be evaluated using the following metrics.

| Metric | Description | Purpose |
|------|------------|---------|
| Attack Success Rate (ASR) | Proportion of generated scenarios that successfully induce unsafe behavior | Adversarial effectiveness |
| Crash Rate (CR) | Frequency of collisions at the trajectory level | Safety assessment |
| Route Completion Rate (RCR) | Proportion of scenarios where the ego vehicle completes its route | Functional robustness |
| Scenario Generation Time | Time required to generate a single scenario | Computational efficiency |

These metrics jointly evaluate safety impact, realism, and efficiency.

---

## 4. Project Tasks

Students are expected to **design and evaluate an adversarial reinforcement learning framework** for safety-critical scenario generation. The project should include the following core tasks.

### 4.1 Adversarial Scenario Formulation

Formulate the interaction between adversarial agents and the ego vehicle as a reinforcement learning problem, defining state representations, action spaces, and reward functions that capture safety-critical objectives.

### 4.2 Balancing Adversariality and Realism

Design mechanisms to constrain adversarial behaviors so that generated scenarios remain physically plausible and behaviorally realistic while still exposing weaknesses in the ego policy.

### 4.3 Benchmark Evaluation

Evaluate the proposed method on benchmark datasets using standardized metrics. Compare results against existing adversarial and non-adversarial scenario generation approaches.

### 4.4 Efficiency and Scalability Analysis

Analyze the computational cost of scenario generation and discuss scalability to large-scale testing and validation pipelines.

---

## 5. Expected Outcomes

By completing this project, students will gain practical experience in adversarial reinforcement learning, simulation-based testing, and autonomous driving safety evaluation. Expected outcomes include a reproducible adversarial scenario generation framework, empirical insights into the trade-off between realism and adversariality, and contributions toward safer and more reliable autonomous driving systems.

---

## 6. References

## References

[1] Sinha, A., Chand, S., Vu, V., Chen, H., & Dixit, V., *Crash and Disengagement Data of Autonomous Vehicles on Public Roads in California*, Scientific Data 8:298, 2021, https://www.nature.com/articles/s41597-021-01083-7  

[2] Gao, Y., et al., *Foundation Models in Autonomous Driving: A Survey on Scenario Generation and Scenario Analysis*, arXiv:2506.11526, 2025, https://arxiv.org/abs/2506.11526  

[3] Feng, L., Li, Q., Peng, Z., Tan, S., & Zhou, B., *TrafficGen: Learning to Generate Diverse and Realistic Traffic Scenarios*, ICRA 2023, https://arxiv.org/abs/2210.06609  

[4] Li, Y., Tao, J., & Wotawa, F., *Ontology-Based Test Generation for Automated and Autonomous Driving Functions*, Information and Software Technology 117:106200, 2020, https://www.sciencedirect.com/science/article/abs/pii/S0950584918302271  

[5] Hao, K., Luo, Y., Cui, W., Bai, Y., Yang, J., Yan, S., Pan, Y., & Yang, Z., *Adversarial Safety-Critical Scenario Generation Using Naturalistic Human Driving Priors*, arXiv:2408.03200, 2024, https://arxiv.org/abs/2408.03200  

[6] Liu, H., et al., *Safety-Critical Scenario Generation via Reinforcement Learning Based Editing*, ICRA 2024, https://ieeexplore.ieee.org/search/searchresult.jsp?queryText=Safety-Critical%20Scenario%20Generation%20via%20Reinforcement%20Learning%20Based%20Editing  