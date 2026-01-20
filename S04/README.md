[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](../README.md#ledger-coursework-research--projects)

# Abnormal DNS Traffic Detection (Clear-text DNS)

**Project Code:** S04  
**Track:** Security × Artificial Intelligence  
**Revision:** Q1, 2026  

---

## 1. Project Background

The Domain Name System (DNS) is a fundamental Internet protocol that remains largely observable in clear text in many enterprise, campus, and industrial networks. Unlike encrypted DNS, clear-text DNS traffic exposes rich lexical, statistical, and temporal information, making it a valuable signal source for detecting abnormal or malicious activity such as malware command-and-control (C2), data exfiltration, domain generation algorithms (DGAs), and DNS tunneling.

In real-world deployments, labeled attack data is often incomplete or unavailable. Consequently, unsupervised anomaly detection plays a central role in DNS security monitoring. These methods model normal DNS behavior and identify deviations without relying on predefined attack signatures.

This project focuses on abnormal DNS traffic detection under clear-text visibility using classical and modern unsupervised anomaly detection techniques. Emphasis is placed on interpretability, robustness, and operational realism.

---

## 2. Research Problems

This project addresses the following research problems:

1. **Modeling Normal DNS Behavior**  
   How can normal DNS usage patterns be effectively modeled in large-scale and heterogeneous networks?

2. **Anomaly Detection without Labels**  
   Which unsupervised methods are most effective for identifying abnormal DNS traffic when labeled attack data is unavailable?

3. **Feature Sensitivity and False Positives**  
   Which DNS features contribute to robust anomaly detection, and which lead to instability or excessive false alarms?

4. **Operational Usability**  
   How suitable are different anomaly detection methods for deployment, considering interpretability and maintenance cost?

The central challenge is balancing detection sensitivity with false positive control in environments with diverse benign DNS behavior.

---

## 3. SOTA Methods and Benchmark Datasets

### 3.1 State-of-the-Art Anomaly Detection Methods

Students are expected to implement and compare at least two of the following methods:

- **Isolation Forest (iForest)**  
  An ensemble-based anomaly detection method that isolates anomalies through random partitioning.  
  Strengths include scalability, simplicity, and strong empirical performance.

- **Isolation Kernel**  
  A kernelized extension of Isolation Forest that improves anomaly separability by mapping data into an isolation-induced similarity space.

- **Density-Based Methods (Optional Extension)**  
  Examples include Local Outlier Factor (LOF) and kNN-based anomaly scoring, which detect anomalies via local density deviations.

Students must clearly justify method selection and explain how anomaly scores are interpreted.

---

### 3.2 DNS Feature Categories

To align with S02–S04, features should be organized into the following categories:

| Feature Category | Examples |
|-----------------|----------|
| Lexical | Domain length, character entropy, vowel ratio |
| Statistical | Query frequency, response size, TTL statistics |
| Temporal | Inter-arrival time, burstiness, periodicity |

Feature selection must be justified and sensitivity discussed.

---

### 3.3 Benchmark Datasets

Some public dataset: 

- **CIC-DNS-2021**  
  DNS traffic with benign and malicious labels.  
  https://www.unb.ca/cic/datasets/


Whenever possible, datasets should be treated as time-ordered streams.

---

## 4. Project Tasks

Students are expected to complete the following tasks:

1. **Literature Review**  
   Review prior work on DNS-based anomaly detection and unsupervised learning, with emphasis on practical deployment motivations.

2. **Feature Engineering**  
   Extract DNS features and organize them into lexical, statistical, and temporal categories.

3. **Model Implementation**  
   Implement Isolation Forest and at least one comparison method.  
   Clearly document model parameters and anomaly scoring mechanisms.

4. **Experimental Evaluation**  
   Evaluate performance using ROC-AUC, precision-recall curves, false positive rate, and detection latency.

5. **Analysis and Reporting**  
   Analyze failure cases and false alarms, and discuss operational implications.

---

## 5. Evaluation Protocol

Evaluation follows the shared DNS project framework and is reported using the tables below.

### 5.1 Core Evaluation Metrics

| Metric | Description | Purpose |
|------|------------|---------|
| ROC-AUC / PR-AUC | Area under ROC or Precision-Recall curve | Overall detection performance |
| False Positive Rate | Fraction of benign traffic flagged as anomalous | Operational usability |
| Detection Latency | Time required to detect an anomaly | Responsiveness |
| Anomaly Score Stability | Variance of anomaly scores over time | Robustness |

---

### 5.2 Baseline Comparisons

| Baseline Type | Description |
|--------------|------------|
| Entropy-based detection | Thresholding based on domain entropy |
| Frequency-based heuristics | Detection based on query or domain frequency |

Baselines provide context and prevent overfitting to complex models.

---

### 5.3 Stress and Robustness Tests

| Stress Test | Purpose |
|------------|---------|
| Benign traffic bursts | Test resistance to false alarms |
| Time-shifted train/test split | Evaluate robustness to distribution shift |
| High-entropy benign domains | Assess susceptibility to mimicry |

At least one stress test must be included.


## 6. Expected Outcomes

Expected outcomes of this project include:

- A comparative analysis of unsupervised anomaly detection methods for DNS traffic
- Identification of effective and stable DNS feature sets
- Practical insights into deploying DNS anomaly detection systems
- Reproducible code and experimental results

This project emphasizes interpretability and realism, making it suitable for applied security analytics research.

---

## 7. References

[1] Liu, F. T., Ting, K. M., & Zhou, Z.-H. (2008). *Isolation Forest*. IEEE International Conference on Data Mining. https://ieeexplore.ieee.org/document/4781136  

[2] Ting, K. M., Zhu, Y., Carman, M. J., & Zhou, Z.-H. (2018). *Isolation Kernel and its Effect on SVM*.  ACM SIGKDD.  https://dl.acm.org/doi/10.1145/3219819.3219990  

[3] Bilge, L., et al. (2012). *Exposure: Finding Malicious Domains Using Passive DNS Analysis*.  NDSS.  https://www.ndss-symposium.org/ndss2012/exposure-finding-malicious-domains-using-passive-dns-analysis/  

 