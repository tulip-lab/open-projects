[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](README.md)

# Clean-Label Backdoor Attacks in Image Classification

**Project Code:** S05  
**Track:** Security × Artificial Intelligence  
**Revision:** Q1, 2026  

---

## 1. Project Background

Deep neural networks for image classification are commonly trained on large-scale datasets collected from open or semi-trusted sources. While this practice accelerates model development, it also introduces significant security risks. One of the most critical threats is the **backdoor attack**, in which a model behaves normally on benign inputs but produces attacker-chosen predictions when a specific trigger is present.

Traditional backdoor attacks often rely on explicit label manipulation, making poisoned samples easier to detect. In contrast, **clean-label backdoor attacks** preserve the original labels of poisoned samples, rendering the attack substantially more stealthy. These attacks exploit the dynamics of representation learning by inducing feature-space collisions between poisoned samples and a target class, despite all labels remaining correct.

This project investigates how clean-label backdoor attacks can be designed, analyzed, and evaluated in modern image classification pipelines, with an emphasis on stealth, effectiveness, and robustness.

---

## 2. Threat Model and Research Problems

The project adopts a constrained and realistic threat model. The attacker may inject a small fraction of poisoned training samples but cannot modify labels, model architectures, or training procedures. The defender trains standard image classifiers using supervised learning and deploys them without explicit backdoor defenses.

The project addresses the following research problems: how to achieve high attack success while maintaining clean-data accuracy, which representation-level mechanisms enable clean-label attacks without label corruption, and how robust such attacks are to data augmentation, regularization, and common defenses. These questions highlight the trade-offs between **stealth**, **effectiveness**, and **robustness**.

---

## 3. Methods and Benchmark Datasets

### 3.1 Clean-Label Backdoor Mechanisms

The focus is on clean-label backdoor attacks grounded in representation manipulation. Feature collision–based attacks construct poisoned samples that remain visually consistent with their ground-truth class while being optimized to lie close to a target class in embedding space. Other approaches rely on imperceptible or naturalistic triggers that are repeatedly reinforced during training. Students are encouraged to analyze representation evolution during training to explain attack success.

---

### 3.2 Benchmark Datasets

Experiments should use standard image classification benchmarks commonly adopted in backdoor research:

- **CIFAR-10**: https://www.cs.toronto.edu/~kriz/cifar.html  
- **Tiny-ImageNet**: https://www.image-net.org  
- **GTSRB (German Traffic Sign Recognition Benchmark)**: https://benchmark.ini.rub.de/gtsrb_news.html  

These datasets enable fair comparison with prior work under increasing task complexity.

---

## 4. Project Tasks

Students are expected to **design, implement, and evaluate a clean-label backdoor attack** for image classification models. The study must be systematic and reproducible and include the following core tasks.

### 4.1 Comparison with State-of-the-Art Attacks

Conduct a comprehensive comparison with existing **state-of-the-art clean-label and dirty-label backdoor attacks**. All methods must be evaluated on the same benchmark datasets (e.g., CIFAR-10, GTSRB, Tiny-ImageNet) under identical settings. Report **Attack Success Rate (ASR)** and **Clean-Data Accuracy (CDA)**.

### 4.2 Cross-Model Attack Performance Validation

Evaluate transferability across **at least three model architectures**, such as **ResNet**, **VGG**, and **DenseNet**, using the same poisoned datasets and trigger designs.

### 4.3 Ablation Study

Perform ablation experiments to analyze the contribution of individual components, including trigger patterns, poisoning strategies, and latent feature perturbations.

### 4.4 Hyperparameter Analysis

Systematically analyze the effect of key hyperparameters, such as poisoning rate, number of training epochs, trigger size, and placement, and discuss trade-offs between stealthiness and effectiveness.

### 4.5 Robustness Evaluation Against Defenses

Assess robustness against mainstream backdoor defenses, including **Neural Cleanse**, **STRIP**, and **ANP**, using their public implementations:
- Neural Cleanse: https://github.com/VinAIResearch/input-aware-backdoor-attack-release/tree/master/defenses  
- STRIP: https://github.com/Unispac/Fight-Poison-With-Poison/blob/master/other_cleansers/strip.py  
- ANP: https://github.com/csdongxian/ANP_backdoor  

Analyze whether the backdoor remains effective after defense and discuss implications.

---

## 5. Evaluation Metrics

| Metric | Description | Purpose |
|------|------------|---------|
| Clean Accuracy (CDA) | Accuracy on clean test data | Stealth verification |
| Attack Success Rate (ASR) | Targeted misclassification rate | Attack effectiveness |
| Trigger Generalization | Performance across trigger variants | Robustness |
| Poisoning Sensitivity | ASR vs poisoning rate | Practical feasibility |

---

## 6. Expected Outcomes

Expected outcomes include a reproducible clean-label backdoor implementation, rigorous evaluation against SOTA attacks and defenses, and insights into representation-level vulnerabilities of deep neural networks. The project contributes to research on trustworthy and robust machine learning.

---

## 7. References

[1] Shafahi, A., Najibi, M., Ghiasi, A., Xu, Z., Dickerson, J., Studer, C., Davis, L., Taylor, G., & Goldstein, T., *Poison Frogs! Targeted Clean-Label Poisoning Attacks on Neural Networks*, NeurIPS 2018, https://papers.nips.cc/paper/2018/hash/22722a343513ed45f14905eb07621686-Abstract.html  
[2] Turner, A., Tsipras, D., & Madry, A., *Label-Consistent Backdoor Attacks*, arXiv:1912.02771, https://arxiv.org/abs/1912.02771  
[3] Saha, A., Subramanya, A., & Pirsiavash, H., *Hidden Trigger Backdoor Attacks*, AAAI 2021, https://ojs.aaai.org/index.php/AAAI/article/view/16248  
[4] Wang, B., Yao, Y., Shan, S., Li, H., Viswanath, B., Zheng, H., & Zhao, B. Y., *Neural Cleanse: Identifying and Mitigating Backdoor Attacks in Neural Networks*, IEEE Symposium on Security and Privacy 2019, https://ieeexplore.ieee.org/document/8835365  
[5] Gao, Y., Xu, C., Wang, D., Chen, S., Ranasinghe, D. C., & Nepal, S., *STRIP: A Defence Against Trojan Attacks on Deep Neural Networks*, ACSAC 2019, https://arxiv.org/abs/1902.06531  
[6] Wu, B., Wang, X., Chen, S., Li, Z., & Jin, H., *Adversarial Neuron Pruning Purifies Backdoored Deep Models*, NeurIPS 2021, https://arxiv.org/abs/2105.02600  