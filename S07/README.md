[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](README.md)

# Backdoor Attacks in Object Detection Systems

**Project Code:** S07  
**Track:** Security × Artificial Intelligence  
**Revision:** Q1, 2026  

---

## 1. Project Background

Object detection is a fundamental task in computer vision and a core component of many safety- and security-critical systems, including autonomous driving, video surveillance, robotics, and intelligent transportation. Modern object detectors such as YOLO, Faster R-CNN, and RetinaNet jointly perform **object localization and classification**, making them more complex and vulnerable than standard image classifiers.

Recent studies show that object detection models are susceptible to **backdoor attacks**, where an attacker poisons training data so that the detector behaves normally on benign scenes but exhibits malicious behavior when a specific trigger is present. Unlike classification backdoors, detection backdoors can manipulate both **bounding box localization** and **class prediction**, leading to subtle yet dangerous failures.

This project focuses on **clean-label and stealthy backdoor attacks in object detection systems**, aiming to understand how training-time poisoning can jointly compromise localization and classification without obvious performance degradation on clean data.

---

## 2. Threat Model and Research Problems

The project adopts a realistic training-time threat model. The attacker can inject a limited number of poisoned training images but cannot modify labels, detector architectures, or training pipelines. The defender trains a standard object detection model using supervised learning and deploys it without specialized backdoor defenses.

Within this setting, the project investigates the following research problems: how to design backdoor triggers that affect detection behavior without reducing clean detection accuracy; how localization and classification errors interact under backdoor activation; and how robust detection backdoors are to common data augmentations, multi-scale training, and post-processing such as non-maximum suppression.

These challenges reflect the complexity of attacking structured prediction models compared with image classifiers.

---

## 3. Methods and Benchmark Datasets

### 3.1 Backdoor Attack Mechanisms for Object Detection

This project studies backdoor attacks that manipulate object detectors by embedding **contextual or spatially aligned triggers** into training images. These triggers may cause detectors to miss objects, mislocalize bounding boxes, or misclassify detected objects when activated.

Students are encouraged to analyze how poisoned samples influence feature pyramids, anchor assignment, and region proposal mechanisms, and how backdoor behavior propagates through the detection pipeline.

---

### 3.2 Benchmark Datasets

Experiments should be conducted on publicly available object detection datasets widely used in research:

**PASCAL VOC**  
PASCAL VOC provides annotated images for object detection across 20 classes. Its moderate size makes it suitable for controlled experimentation and detailed analysis.  
http://host.robots.ox.ac.uk/pascal/VOC/  

**MS COCO**  
MS COCO is a large-scale dataset with complex scenes, multiple objects per image, and fine-grained annotations. It enables evaluation of backdoor attacks under realistic and challenging conditions.  
https://cocodataset.org  

**BDD100K (Object Detection Annotations)**  
BDD100K includes object detection annotations for diverse driving scenarios, supporting evaluation in safety-critical and domain-specific contexts.  
https://bdd-data.berkeley.edu  

---

## 4. Project Tasks

Students are expected to **design, implement, and evaluate a backdoor attack for object detection models**. The experimental study must be systematic and reproducible and include the following tasks.

### 4.1 Comparison with State-of-the-Art Attacks

Conduct a comprehensive comparison with existing backdoor attacks for object detection. All methods must be evaluated on the same datasets under identical training and evaluation protocols. Metrics should reflect both localization and classification performance.

---

### 4.2 Cross-Detector Evaluation

Evaluate the proposed attack across **at least two different detection architectures**, such as **YOLO-based** and **Faster R-CNN–based** models. This assesses whether the backdoor generalizes across detector families.

---

### 4.3 Ablation Study

Perform ablation experiments to analyze the contribution of individual attack components, including trigger design, placement strategy, and poisoning ratio.

---

### 4.4 Robustness and Transfer Analysis

Analyze robustness under data augmentation, multi-scale training, and different non-maximum suppression settings. Evaluate whether triggers transfer across datasets or detector architectures.

---

### 4.5 Robustness Against Defenses

Evaluate the effectiveness of potential defenses, such as data filtering, feature consistency checks, or detector-specific anomaly detection methods. Discuss whether existing defenses can effectively mitigate detection backdoors.

---

## 5. Evaluation Metrics

| Metric | Description | Purpose |
|------|------------|---------|
| mAP (Clean) | Mean Average Precision on clean data | Detection correctness |
| Attack Success Rate | Probability of inducing targeted detection failure | Attack effectiveness |
| Localization Error | Bounding box deviation under trigger | Spatial impact |
| Clean Performance Drop | mAP degradation on benign data | Stealth assessment |

---

## 6. Expected Outcomes

By completing this project, students will gain insight into how backdoor attacks extend beyond classification to structured prediction tasks. Expected outcomes include a reproducible detection backdoor attack, empirical analysis of localization–classification interactions, and a deeper understanding of security risks in real-world detection systems. The project contributes to research on secure and trustworthy computer vision.

---

## 7. References

[1] Chen, X., Liu, C., Li, B., Lu, K., & Song, D., *Targeted Backdoor Attacks on Deep Learning Systems Using Data Poisoning*, arXiv:1712.05526, https://arxiv.org/abs/1712.05526  
[2] Saha, A., Subramanya, A., & Pirsiavash, H., *Hidden Trigger Backdoor Attacks*, AAAI 2021, https://ojs.aaai.org/index.php/AAAI/article/view/16248  
[3] Li, Y., et al., *Invisible Backdoor Attacks on Deep Neural Networks via Steganography and Regularization*, IEEE TPAMI, https://ieeexplore.ieee.org/document/9711191/  
[4] Redmon, J., et al., *You Only Look Once: Unified, Real-Time Object Detection*, CVPR 2016, https://arxiv.org/abs/1506.02640  
[5] Ren, S., He, K., Girshick, R., & Sun, J., *Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks*, NeurIPS 2015, https://arxiv.org/abs/1506.01497  
[6] Lin, T.-Y., et al., *Microsoft COCO: Common Objects in Context*, ECCV 2014, https://cocodataset.org  