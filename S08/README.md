[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](README.md)

# Backdoor Attacks in Continual Learning

**Project Code:** S08  
**Track:** Security × Artificial Intelligence  
**Revision:** Q4, 2025  

---

## 1. Project Background

Continual Learning (CL), also known as lifelong or incremental learning, aims to enable neural networks to learn a sequence of tasks over time while retaining knowledge acquired from earlier tasks. CL is widely studied as a solution to catastrophic forgetting and is increasingly adopted in real-world systems that must adapt continuously, such as cybersecurity monitoring, robotics, and autonomous systems.

Despite extensive research on performance and stability, the **security of continual learning systems remains largely underexplored**. In particular, **backdoor attacks** pose a serious threat. Backdoor attacks embed hidden malicious behaviors into a model during training, causing it to behave normally on clean inputs but produce attacker-chosen outputs when a specific trigger is present.

In continual learning settings, the sequential update of model parameters creates both challenges and opportunities for attackers. While task transitions may weaken or erase backdoors, they may also be exploited to hide or reinforce malicious behaviors. Understanding how backdoors can persist across tasks is therefore critical for the safe deployment of CL systems  [oai_citation:0‡01_backdoor in CL.pdf](sediment://file_0000000098747206964764f1f723779e).

---

## 2. Research Problems and Key Challenges

Backdoor attacks have been extensively studied in static supervised learning, but their effectiveness in continual learning is fundamentally challenged by sequential training dynamics. Parameter updates across tasks can overwrite previously learned representations, making **backdoor persistence** a central challenge.

This project addresses the following research questions:

How can backdoor attacks be designed to remain effective across sequential tasks in continual learning?  
Which components of a neural network remain stable enough to support persistent backdoor behavior?  
How does the choice of CL strategy influence backdoor survival and activation?

These questions highlight the tension between adaptability and security in lifelong learning systems.

---

## 3. State-of-the-Art Methods

Recent research has begun to address backdoor threats in continual learning. Jiang et al. introduced **latent backdoor attacks**, embedding malicious behaviors into pre-trained representations that activate only when the model is extended to downstream tasks. More recent work proposes **persistent backdoor attacks**, which strategically embed triggers into **stable neurons**—model components whose importance remains consistent across tasks.

By targeting stable rather than volatile parameters, these attacks achieve long-term survival and consistent activation despite continual updates. This project builds on these insights and encourages deeper investigation into representation stability and backdoor persistence mechanisms  [oai_citation:1‡01_backdoor in CL.pdf](sediment://file_0000000098747206964764f1f723779e).

---

## 4. Benchmark Datasets

Experiments should be conducted using standard continual learning benchmarks that support controlled task sequences:
(https://avalanche.continualai.org/avalanche/from-zero-to-hero-tutorial/03_benchmarks)

**PermutedMNIST**  
Ten sequential tasks constructed by applying different pixel permutations to the MNIST dataset. This benchmark isolates task boundaries while preserving class semantics.

**SplitMNIST**  
Five sequential tasks, each containing two digit classes. This dataset is widely used to study task-incremental and class-incremental learning.

**SplitCIFAR-10**  
Five sequential tasks, each consisting of two object categories from CIFAR-10. This benchmark introduces higher visual complexity and realism.

These datasets enable systematic evaluation of backdoor persistence across tasks.

---

## 5. Project Tasks

Students are expected to **design, implement, and evaluate a backdoor attack in a continual learning setting**. The study should be systematic and reproducible and include the following tasks.

### 5.1 Backdoor Design in Continual Learning

Design a backdoor attack that can be injected during one or more tasks in a CL pipeline. The attack should aim to remain effective across subsequent tasks.

### 5.2 Persistence Analysis Across Tasks

Evaluate whether and how the backdoor survives task transitions. Analyze activation strength and failure modes as new tasks are learned.

### 5.3 Comparison with State-of-the-Art Attacks

Compare the proposed method with existing latent and persistent backdoor attacks under identical CL settings and datasets.

### 5.4 Interaction with Continual Learning Strategies

Study how different CL strategies, such as rehearsal-based or regularization-based methods, affect backdoor persistence and clean performance.

---

## 6. Evaluation Metrics

| Metric | Description | Purpose |
|------|------------|---------|
| Attack Success Rate (ASR) | Percentage of triggered samples misclassified | Backdoor effectiveness |
| Clean Accuracy (CA) | Accuracy on benign test samples | Stealth assessment |
| Task-wise ASR | ASR measured after each task | Persistence analysis |
| Forgetting Rate | Performance drop on earlier tasks | CL stability |

---

## 7. Expected Outcomes

By completing this project, students will gain a deep understanding of how continual learning dynamics interact with adversarial threats. Expected outcomes include a reproducible CL backdoor attack, empirical insights into backdoor persistence, and a clearer understanding of security risks in lifelong learning systems. The project contributes to research on secure and trustworthy continual learning.

---

## 8. References

[1] Jiang, W., Zhang, T., Qiu, H., Li, H., & Xu, G., *Incremental Learning, Incremental Backdoor Threats*, IEEE Transactions on Dependable and Secure Computing, 2022, https://ieeexplore.ieee.org/document/9872528/
[2] Guo, Z., Kumar, A., & Tourani, R., *Persistent Backdoor Attacks in Continual Learning*, USENIX Security Symposium 2025, https://arxiv.org/abs/2409.13864