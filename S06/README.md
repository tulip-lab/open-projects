[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](README.md)

# Physical Backdoor Attacks in Lane Detection Systems

**Project Code:** S06  
**Track:** Security × Artificial Intelligence  
**Revision:** Q1, 2026  

---

## 1. Project Background

Lane detection is a core perception module in autonomous driving systems and advanced driver assistance systems (ADAS). Modern lane detection models rely heavily on deep learning and are trained using large-scale driving datasets. While these models demonstrate strong performance under normal conditions, their data-driven nature exposes them to serious security risks.

Among these risks, **physical backdoor attacks** represent a particularly dangerous threat. Unlike digital backdoors that manipulate pixel-level inputs, physical backdoor attacks embed triggers into real-world objects or environments, such as lane markings, road textures, or roadside patterns. When captured by the vehicle’s camera, these triggers can cause the model to output attacker-controlled lane predictions while behaving normally on benign scenes.

This project focuses on **clean-label, physically realizable backdoor attacks** against lane detection networks, emphasizing realism, stealth, and robustness under real-world driving conditions.

---

## 2. Threat Model and Research Problems

The project adopts a realistic physical-world threat model. The attacker can inject a limited number of poisoned training samples containing physical triggers but cannot modify labels, network architectures, or training pipelines. The defender trains a standard lane detection model and deploys it without specialized backdoor defenses.

Within this setting, the project addresses the following research questions: how to design physical triggers that are visually natural yet consistently effective; how clean-label poisoning can manipulate lane predictions without degrading clean performance; and how robust such attacks are to viewpoint changes, illumination variations, and environmental noise.

These questions highlight the vulnerability of safety-critical perception systems to subtle and persistent adversarial manipulation.

---

## 3. Methods and Benchmark Datasets

### 3.1 Physical Backdoor Attack Mechanisms

This project studies backdoor attacks based on **context-aware physical triggers**, such as modified lane markings, textured patches aligned with road geometry, or subtle structural perturbations. These triggers are designed to be inconspicuous to human drivers while reliably activating the backdoor when observed by the lane detection model.

Students are encouraged to analyze how physical triggers interact with spatial perception, how consistency across frames influences attack success, and how representation learning contributes to vulnerability.

---

### 3.2 Benchmark Datasets

This project evaluates physical backdoor attacks on **publicly available lane detection datasets** widely used in autonomous driving research. Each dataset provides different scene characteristics and annotation styles, enabling comprehensive evaluation.

**TuSimple Lane Detection Dataset**  
TuSimple focuses on highway driving scenarios with clear lane markings and relatively simple backgrounds. It provides accurate lane annotations and a standardized evaluation protocol, making it suitable for controlled experimentation and baseline comparison.  
https://github.com/TuSimple/tusimple-benchmark  

**CULane Dataset**  
CULane is a large-scale dataset designed for challenging urban driving conditions, including night scenes, shadows, occlusions, curves, and crowded environments. It is particularly valuable for evaluating the robustness of physical backdoor triggers under visually complex conditions.  
https://xingangpan.github.io/projects/CULane.html  

**BDD100K (Lane Annotations)**  
BDD100K is a diverse driving dataset covering multiple cities, weather conditions, and lighting environments. Its lane annotations support evaluation under distribution shifts and environmental variability, which is essential for assessing real-world feasibility.  
https://bdd-data.berkeley.edu  

**ApolloScape (Optional Extension Dataset)**  
ApolloScape is a large-scale autonomous driving dataset with fine-grained lane annotations across diverse urban scenes, including complex road geometries and dense traffic. It offers higher-resolution imagery and more detailed annotations, making it well suited for analyzing spatially precise and context-aware physical triggers.  
https://apolloscape.auto  

ApolloScape is not mandatory due to its higher computational and preprocessing requirements, but it is strongly recommended as an extension dataset for advanced studies.

---

## 4. Project Tasks

Students are expected to **design, implement, and evaluate a physical clean-label backdoor attack** for lane detection systems. The experimental study must be systematic and reproducible and include the following tasks.

### 4.1 Comparison with State-of-the-Art Attacks

Compare the proposed method with existing digital and physical backdoor attacks for lane detection. All methods must be evaluated on the same datasets using identical training and evaluation protocols.

### 4.2 Cross-Model Evaluation

Evaluate the attack on at least two different lane detection architectures, such as segmentation-based and anchor-based models, to assess generalization across network designs.

### 4.3 Ablation Study

Perform ablation experiments to analyze the contribution of trigger shape, size, placement, and contextual alignment with road geometry.

### 4.4 Environmental Robustness Analysis

Analyze robustness under varying physical conditions, including changes in camera viewpoint, illumination, weather, motion blur, and partial occlusion.

### 4.5 Robustness Against Defenses

Evaluate the effectiveness of common defenses, such as aggressive data augmentation, input preprocessing, or anomaly-based detection. Discuss whether existing defenses are sufficient to mitigate physical backdoor attacks.

---

## 5. Evaluation Metrics

| Metric | Description | Purpose |
|------|------------|---------|
| Lane Detection Accuracy | Performance on clean test scenes | Functional correctness |
| Attack Success Rate | Probability of inducing targeted lane deviation | Attack effectiveness |
| Trigger Robustness | Performance under physical transformations | Real-world feasibility |
| Clean Performance Drop | Accuracy degradation on benign data | Stealth assessment |

---

## 6. Expected Outcomes

By completing this project, students will gain hands-on experience with physical-world attacks against safety-critical perception systems. Expected outcomes include a reproducible physical backdoor attack pipeline, empirical insights into trigger robustness, and a deeper understanding of the gap between digital and physical adversarial threats. The project contributes directly to research on secure and trustworthy autonomous driving systems.

---

## 7. References

[1] Chen, X., Liu, C., Li, B., Lu, K., & Song, D., *Targeted Backdoor Attacks on Deep Learning Systems Using Data Poisoning*, arXiv:1712.05526, https://arxiv.org/abs/1712.05526  
[2] Saha, A., Subramanya, A., & Pirsiavash, H., *Hidden Trigger Backdoor Attacks*, AAAI 2021, https://ojs.aaai.org/index.php/AAAI/article/view/16248  
[3] Li, Y., et al., *Invisible Backdoor Attacks on Deep Neural Networks via Steganography and Regularization*, IEEE TPAMI, https://ieeexplore.ieee.org/document/9154983  
[4] TuSimple Lane Detection Benchmark, https://github.com/TuSimple/tusimple-benchmark  
[5] CULane Dataset, https://xingangpan.github.io/projects/CULane.html  
[6] BDD100K Dataset, https://bdd-data.berkeley.edu  
[7] ApolloScape Dataset, https://apolloscape.auto  