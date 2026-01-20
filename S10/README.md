[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](../README.md#ledger-coursework-research--projects)

# Data-free Universal Adversarial Attacks

**Project Code:** S10  
**Track:** Security × Artificial Intelligence  
**Revision:** Q4, 2025  

---

## 1. Project Background

Deep neural networks (DNNs) have achieved remarkable success in computer vision tasks such as image classification, object detection, and semantic segmentation. Despite their strong performance, DNNs are highly vulnerable to adversarial examples, which are inputs perturbed by carefully crafted and often imperceptible noise that causes confident but incorrect predictions. This vulnerability raises serious concerns for deploying DNNs in safety- and security-critical applications.

Traditional adversarial attacks typically generate **input-specific perturbations**, which limits scalability and practicality. To overcome this limitation, **Universal Adversarial Perturbations (UAPs)** were introduced as image-agnostic attacks that learn a single perturbation capable of fooling a model across a wide range of unseen inputs. UAPs are significantly more efficient and threatening than per-sample attacks.

Most existing UAP methods rely on access to target-domain data. However, in many realistic scenarios, attackers do not have access to any training or test data. This motivates the study of **data-free universal adversarial attacks**, where perturbations must be generated without using any target-domain samples. This project investigates the design, evaluation, and limitations of such data-free UAP methods. 

---

## 2. Research Problems and Key Challenges

The core research problem of this project is how to generate effective and transferable universal adversarial perturbations **without access to any target-domain data**. Compared with data-dependent UAPs, the data-free setting is significantly more challenging because the attacker cannot exploit data priors or semantic information from real samples.

Key challenges include generating perturbations that generalize across unseen inputs, maintaining high fooling rates under strict data-free constraints, and improving transferability across different model architectures. The project also explores how semantic information can be implicitly captured or approximated when no real data is available.

---

## 3. State-of-the-Art Data-free UAP Methods

Several representative methods have been proposed to address data-free universal adversarial attacks.

**GD-UAP** maximizes neuron activations across multiple layers of a target CNN using random noise inputs, thereby corrupting internal feature representations and inducing misclassification.

**TRM-UAP** enhances transferability by maximizing truncated ratios of positive and negative neuron activations and introduces a curriculum optimization strategy to stabilize training.

**PSP-UAP** further improves performance by recursively extracting pseudo-semantic priors from the evolving UAP itself, enabling the perturbation to encode richer semantic structure despite the absence of real data.

This project builds upon these methods and encourages systematic comparison and analysis of their effectiveness and limitations. 

---

## 4. Benchmark Datasets

Although the attacks are generated without data, evaluation must be conducted on standard vision benchmarks to assess effectiveness.

**CIFAR-100**  
CIFAR-100 contains 60,000 color images from 100 object classes and is commonly used for benchmarking adversarial robustness in medium-scale image classification.  
Dataset link: https://www.cs.toronto.edu/~kriz/cifar.html  

**ImageNet Validation Set**  
The ImageNet validation set consists of 50,000 images across 1,000 classes and represents a large-scale, realistic benchmark for evaluating transferability and scalability of UAPs.  
Dataset link: https://www.image-net.org  

These datasets enable consistent comparison with prior work on universal adversarial attacks.

---

## 5. Project Tasks

Students are expected to **design, implement, and evaluate data-free universal adversarial attacks**. The study should be systematic and reproducible and include the following tasks.

### 5.1 Implementation of Baseline Data-free UAPs

Reproduce representative data-free UAP methods such as GD-UAP, TRM-UAP, or PSP-UAP, and verify reported performance on benchmark datasets.

### 5.2 Design of an Improved Data-free UAP Method

Propose a novel or improved objective, optimization strategy, or pseudo-prior construction mechanism to enhance fooling rate or transferability under the data-free constraint.

### 5.3 Cross-Model Transferability Analysis

Evaluate whether the generated UAPs generalize across different CNN architectures, such as ResNet, VGG, and DenseNet.

### 5.4 Ablation and Sensitivity Analysis

Analyze the contribution of individual components, including initialization, optimization objectives, and layer selection, to overall attack performance.

---

## 6. Evaluation Metrics

| Metric | Description | Purpose |
|------|------------|---------|
| Fooling Rate (FR) | Percentage of samples whose predictions change under UAP | Attack effectiveness |
| Cross-Model FR | FR measured on unseen architectures | Transferability |
| Perturbation Norm | Magnitude of the universal perturbation | Stealth assessment |
| Convergence Speed | Iterations required to reach stable FR | Efficiency |

---

## 7. Expected Outcomes

By completing this project, students will gain a deep understanding of universal adversarial attacks under realistic data-free constraints. Expected outcomes include a reproducible data-free UAP implementation, empirical insights into transferability and semantic priors, and a critical assessment of the limits of data-free adversarial attacks. The project contributes to research on adversarial robustness and secure deployment of deep learning systems.

---

## 8. References

[1] K. R. Mopuri, A. Ganeshan, and R. V. Babu, *Generalizable Data-Free Objective for Crafting Universal Adversarial Perturbations*, IEEE TPAMI 2018, https://arxiv.org/abs/1801.08092 
[2] Y. Liu, X. Feng, Y. Wang, W. Yang, and D. Ming, *TRM-UAP: Enhancing the Transferability of Data-Free Universal Adversarial Perturbation via Truncated Ratio Maximization*, ICCV 2023, https://openaccess.thecvf.com/content/ICCV2023/papers/Liu_TRM-UAP_Enhancing_the_Transferability_of_Data-Free_Universal_Adversarial_Perturbation_via_ICCV_2023_paper.pdf
[3] C. Lee, Y. Song, and J. Son, *Data-Free Universal Adversarial Perturbation with Pseudo-Semantic Prior*, CVPR 2025, https://arxiv.org/abs/2502.21048