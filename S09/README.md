[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](README.md)

# Poisoning Attacks in Continual Learning

**Project Code:** S09  
**Track:** Security × Artificial Intelligence  
**Revision:** Q4, 2025  

---

## 1. Project Background

Continual Learning (CL), also referred to as lifelong or incremental learning, aims to enable neural networks to learn a sequence of tasks while retaining knowledge acquired from previous tasks. Most existing CL research focuses on mitigating catastrophic forgetting, with comparatively little attention paid to **security and adversarial robustness**.

Data poisoning attacks represent a critical yet underexplored threat to CL systems. In such attacks, adversaries subtly manipulate training data so that, after standard training, the model exhibits attacker-desired behavior. In continual learning, this behavior often manifests as **intentional catastrophic forgetting** of previously learned tasks.

Compared with static learning, CL systems are particularly vulnerable because poisoned data injected at later stages can retroactively impair earlier tasks. As CL systems are increasingly deployed in security- and safety-critical applications, understanding poisoning-induced forgetting is essential for safe and trustworthy deployment.

---

## 2. Research Problems and Key Challenges

In the continual learning setting, poisoning attacks aim to deliberately induce catastrophic forgetting of earlier tasks while avoiding detection. Effective attacks must satisfy two competing objectives: **effectiveness**, meaning severe degradation of performance on previous tasks, and **stealthiness**, meaning high accuracy on the current task.

The central research question of this project is:  
How can poisoning attacks be designed to promote catastrophic forgetting of previous tasks while maintaining acceptable performance on the current task?

This challenge is unique to CL systems, as poisoning introduced during later tasks can influence both past and future knowledge retention.

---

## 3. State-of-the-Art Poisoning Attacks in Continual Learning

Recent research has begun to explore poisoning attacks tailored to continual learning:

Targeted task-level poisoning attacks generate clean-label poisoned samples whose gradients approximate those of label-flipped samples from target tasks, selectively forcing forgetting of specific historical tasks while preserving current-task performance.

Replay poisoning attacks target generative replay mechanisms by injecting poisoned samples that corrupt replayed data. These attacks exploit the fact that replayed samples may lose visible triggers while retaining incorrect semantic information, thereby accelerating forgetting in future tasks.

Bi-level optimization approaches reconstruct approximations of previous task data through model inversion and craft poisoned samples that explicitly minimize performance on reconstructed historical tasks while maintaining acceptable accuracy on the current task.

This project builds on these ideas and encourages deeper analysis of how poisoning interacts with continual learning dynamics. 

---

## 4. Benchmark Datasets

Experiments should be conducted using **standard continual learning benchmarks** that support controlled task sequences.

**PermutedMNIST**  
A benchmark constructed by applying different fixed pixel permutations to the MNIST dataset, forming ten sequential tasks. It isolates task boundaries while preserving class semantics and is widely used to study forgetting behavior.   

**SplitMNIST**  
A continual learning benchmark that divides MNIST into five sequential tasks, each containing two digit classes. It is commonly used for task-incremental and class-incremental learning evaluation.  

**SplitCIFAR-10**  
A benchmark constructed from CIFAR-10, forming five sequential tasks with two object categories per task. This benchmark introduces higher visual complexity and realism compared with MNIST-based benchmarks.  

These benchmarks enable systematic evaluation of poisoning-induced forgetting across tasks.

---

## 5. Project Tasks

Students are expected to **design, implement, and evaluate a poisoning attack in a continual learning setting**. The study should be systematic and reproducible and include the following tasks.

### 5.1 Poisoning Attack Design

Design a poisoning strategy that injects malicious samples during one or more tasks with the goal of inducing forgetting of specific or all previous tasks.

### 5.2 Forgetting Analysis Across Tasks

Evaluate how performance on earlier tasks degrades as new tasks are learned. Analyze task-wise accuracy and identify which tasks are most vulnerable.

### 5.3 Comparison with State-of-the-Art Attacks

Compare the proposed attack with existing poisoning attacks in continual learning under identical datasets, CL strategies, and evaluation protocols.

### 5.4 Interaction with Continual Learning Strategies

Study how different CL strategies, such as rehearsal-based or regularization-based methods, influence the effectiveness and stealthiness of poisoning attacks.

---

## 6. Evaluation Metrics

| Metric | Description | Purpose |
|------|------------|---------|
| Backward Transfer (BWT) | Performance change on previous tasks after learning new tasks | Quantifies forgetting |
| Clean Task Accuracy | Accuracy on the current task with poisoned data | Stealth assessment |
| Task-wise Accuracy | Accuracy measured after each task | Persistence analysis |
| Forgetting Severity | Magnitude of performance degradation | Attack effectiveness |

Backward Transfer (BWT) is defined as the average difference between task performance before and after learning subsequent tasks, where more negative values indicate stronger poisoning-induced forgetting  [oai_citation:3‡02_poisoning in CL.pdf](sediment://file_0000000081f07206bf178c466c471665).

---

## 7. Expected Outcomes

By completing this project, students will gain a deep understanding of how poisoning attacks exploit continual learning dynamics. Expected outcomes include a reproducible poisoning attack pipeline, empirical insights into poisoning-induced forgetting, and a clearer understanding of the security risks faced by CL systems. The project contributes to research on robust and trustworthy continual learning.

---

## 8. References

[1] H. Li and G. Ditzler, *Targeted Data Poisoning Attacks Against Continual Learning Neural Networks*, IJCNN 2022, https://ieeexplore.ieee.org/document/9892774
[2] S. Kang, Z. Shi, and X. Zhang, *Poisoning Generative Replay in Continual Learning to Promote Forgetting*, ICML 2023,  https://proceedings.mlr.press/v202/kang23c.html
[3] A. Abbasi, P. Nooralinejad, H. Pirsiavash, and S. Kolouri, *BrainWash: A Poisoning Attack to Forget in Continual Learning*, CVPR 2024, https://openaccess.thecvf.com/content/CVPR2024/html/Abbasi_BrainWash_A_Poisoning_Attack_to_Forget_in_Continual_Learning_CVPR_2024_paper.html  