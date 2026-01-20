[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](../README.md#ledger-coursework-research--projects)

# Adversarial Example Attacks in Continual Learning

**Project Code:** S11  
**Track:** Security × Artificial Intelligence  
**Revision:** Q4, 2025  

---

## 1. Project Background

Continual Learning (CL), also referred to as lifelong or incremental learning, aims to enable machine learning models to learn a sequence of tasks over time while preserving knowledge acquired from earlier tasks. Most existing CL research focuses on mitigating catastrophic forgetting, whereas the **security and adversarial robustness of continual learning systems remain largely underexplored**.

Adversarial examples (AEs) constitute a well-known threat to deep learning models. By introducing carefully crafted and often imperceptible perturbations to input data, attackers can cause models to produce incorrect predictions with high confidence. While adversarial attacks have been extensively studied in static learning settings, their effectiveness in continual learning environments is far less understood.

In continual learning, models are repeatedly updated with new tasks that differ in data distribution and label space. As a result, adversarial examples crafted for an earlier model often lose their effectiveness after subsequent updates. Understanding whether adversarial examples can be made **sustainable under continual model evolution** is essential for deploying CL systems in security-critical applications  [oai_citation:1‡04_AE attack in CL.pdf](sediment://file_0000000091947206b3ef6280f28e2939).

---

## 2. Research Problems and Key Challenges

The core research problem addressed in this project is how to design adversarial examples that remain effective across the entire continual learning process. Unlike static models, CL systems undergo repeated parameter updates, causing significant representation drift that can invalidate previously generated adversarial perturbations.

The key challenge is therefore **adversarial sustainability**: ensuring that adversarial examples continue to induce targeted misclassification even after the model has learned multiple new tasks. This requires adversarial perturbations that align with stable semantic features rather than task-specific or transient representations.

This project explores how adversarial attacks can be adapted to continual learning settings and how model evolution fundamentally changes the threat landscape.

---

## 3. State-of-the-Art Methods

Recent work has begun to investigate adversarial example attacks under continual learning. A representative approach is **SAE (Sustainable Adversarial Examples)**, which improves the longevity of adversarial examples in class-incremental learning scenarios.

SAE aligns adversarial examples semantically with the target class while explicitly separating them from non-target classes. To improve generalization across tasks, SAE leverages a visual-language model to capture high-level semantic information and introduces filtering and augmentation strategies to stabilize adversarial semantics under continual updates.

This project builds upon these ideas and encourages students to analyze why certain adversarial perturbations survive model evolution while others fail  [oai_citation:2‡04_AE attack in CL.pdf](sediment://file_0000000091947206b3ef6280f28e2939).

---

## 4. Benchmark Datasets

Experiments should be conducted using **standard continual learning benchmarks** that support controlled task sequences.

**SplitCIFAR-100**  
A continual learning benchmark constructed from CIFAR-100, consisting of 10 sequential tasks with 10 classes per task. It introduces moderate visual complexity and is widely used for class-incremental learning evaluation.  
Dataset link: https://www.cs.toronto.edu/~kriz/cifar.html  
Benchmark protocol: https://avalanche.continualai.org/benchmarks/split_cifar100/

**SplitTinyImageNet**  
A continual learning benchmark derived from TinyImageNet, consisting of 20 sequential tasks with 10 classes per task. It provides higher visual diversity and complexity, making it suitable for evaluating adversarial robustness under more challenging conditions.  
Dataset link: https://www.kaggle.com/c/tiny-imagenet  
Benchmark protocol: https://avalanche.continualai.org/benchmarks/split_tinyimagenet/

These benchmarks enable systematic evaluation of adversarial example sustainability across task sequences.

---

## 5. Project Tasks

Students are expected to **design, implement, and evaluate adversarial example attacks in continual learning settings**. The experimental study should be systematic and reproducible and include the following tasks.

### 5.1 Implementation of Baseline Attacks

Reproduce baseline adversarial attacks and evaluate their effectiveness when applied to continual learning models without modification.

### 5.2 Design of Sustainable Adversarial Examples

Implement or extend state-of-the-art methods such as SAE to generate adversarial examples that remain effective across multiple tasks.

### 5.3 Sustainability Analysis Across Tasks

Measure how adversarial effectiveness evolves as the model learns new tasks. Identify which perturbations persist and which degrade.

### 5.4 Comparison with Static-Model Attacks

Compare continual-learning-aware adversarial examples with conventional static-model attacks to highlight fundamental differences.

---

## 6. Evaluation Metrics

| Metric | Description | Purpose |
|------|------------|---------|
| Attack Success Rate (ASR) | Proportion of adversarial examples classified as the target class | Immediate effectiveness |
| Sustainable ASR (SASR) | Average ASR across all tasks in the CL process | Long-term sustainability |
| Clean Accuracy | Accuracy on benign samples | Stealth assessment |
| Task-wise ASR | ASR measured after each task | Persistence analysis |

Sustainable ASR (SASR) measures adversarial effectiveness over the entire continual learning trajectory and captures long-term attack viability.

---

## 7. Expected Outcomes

By completing this project, students will gain a deep understanding of how adversarial examples interact with continual learning dynamics. Expected outcomes include a reproducible sustainable AE attack pipeline, empirical insights into adversarial persistence, and a clearer understanding of security risks in lifelong learning systems. The project contributes to research on adversarial robustness beyond static models.

---

## 8. References

[1] T. Liu, X. Liu, L. Dong, Y. Liu, Y. Yang, and Z. Ma, *Improving Sustainability of Adversarial Examples in Class-Incremental Learning*, arXiv:2511.09088, 2025, https://arxiv.org/abs/2511.09088  