[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](../README.md#ledger-coursework-research--projects)

# Behavioral Profiling for Abnormal DNS Traffic Detection

**Project Code:** S02  
**Track:** Security × Artificial Intelligence  
**Revision:** Q1, 2026

---

## 1. Project Background

The Domain Name System (DNS) is a foundational protocol that translates domain names into IP addresses. Because DNS traffic is ubiquitous and often permitted through network security controls, it has become a target for attackers seeking to hide malicious activity or establish covert channels ([turn0search5]). Behavioral profiling of DNS traffic leverages statistical, temporal, and semantic characteristics of DNS queries and responses to detect abnormal events that may indicate data exfiltration, tunneling, domain generation algorithm (DGA) usage, command-and-control (C2) communication, or other stealthy behaviors.

Conventional DNS monitoring methods, such as blacklisting, fail to identify adaptive adversarial methods due to high false negatives when attackers generate novel or transient malicious domains. Machine learning approaches that model *normal* DNS behavior and identify deviations are more promising due to their ability to generalize beyond known signatures and capture behavioral patterns ([turn0search21]).

This project focuses on **behavioral profiling for abnormal DNS traffic detection**, where models learn patterns of benign DNS flows and flag deviations indicative of malicious intent. It explores statistical and machine learning mechanisms to profile, characterize, and detect anomalous behavior at the traffic flow and domain usage levels.

---

## 2. Research Problems

The core research questions are:

- How can behavioral profiling models effectively distinguish between benign and malicious DNS traffic patterns without relying on static signatures or blacklists?
- What features best capture behavioral anomalies in DNS traffic, including query frequency, domain entropy, response patterns, and temporal correlations?
- How can models generalize to unseen threats such as DNS exfiltration, tunneling, or fast flux domain behavior?
- What are the limitations of existing DNS anomaly detection methods with respect to real-time performance, false positive rates, and adaptability to changing network environments?

Challenges include dealing with highly imbalanced datasets where malicious traffic is rare, accounting for diverse benign behavior, and ensuring that feature representations capture meaningful patterns relevant to malicious activity.

---

## 3. SOTA Methods and Benchmark Datasets

### 3.1 State-of-the-Art Methods

Representative research relevant to this topic includes:

- **Behavioral Profiling in DNS Traffic:** Methods that generate behavioral profiles of users or devices based on DNS query patterns and detect deviations without relying on signatures ([turn0academia49]).
- **Machine Learning for DNS Anomaly Detection:** Techniques such as sequence modeling, clustering, and classification (e.g., SVM, Random Forest, deep learning) have been applied to DNS tunneling and exfiltration detection ([turn0search9], [turn0search10]).
- **Approximate String Matching Approaches:** Transformation of DNS traffic data into symbolic sequences and applying approximate pattern matching to detect anomalies ([turn0academia47]).

These methods improve over static rule-based systems by capturing temporal and structural aspects of DNS behavior, although scalability and model interpretability remain open issues.

### 3.2 Benchmark Datasets

The project will utilize publicly available DNS datasets suitable for behavioral anomaly research:

- **CIC-Bell-DNS-EXF-2021:** A large DNS traffic dataset with benign and exfiltration attack samples. Includes feature-engineered records suitable for ML modeling. Hosted by CIC’s dataset repository and mirrored on Kaggle: https://www.unb.ca/cic/datasets/dns-exf-2021.html ([turn0search2]) / https://www.kaggle.com/datasets/humera11/cicbelldnsexf2021  
- **CIC-Bell-DNS-2021:** A large domain dataset containing malware, phishing, spam, and benign domain labels, useful for domain-level fingerprinting and classification tasks: https://www.unb.ca/cic/datasets/dns-2021.html  
- **DNS Tunnel Dataset (Community/Research Repositories):** Collections of benign and tunneled DNS traffic useful for detecting covert channels. A consolidated resource is available via GitHub: https://github.com/ggyggy666/DNS-Tunnel-Datasets  

These datasets provide diverse DNS behaviors and are structured for feature-based modeling and evaluation of behavioral profiling systems.

---

## 4. Project Tasks

1. **Literature Review**  
   Examine recent works on DNS anomaly detection, behavioral profiling, feature engineering, and machine learning classification techniques.

2. **Feature Engineering and Profiling**  
   Identify and extract meaningful behavioral features from DNS flows, including query frequency distributions, domain-based lexical features, TTL statistics, and entropy measures.

3. **Model Development**  
   Design machine learning models (e.g., random forests, anomaly detection algorithms, sequence models) trained on behavioral features to distinguish between benign and abnormal DNS activity.

4. **Evaluation and Benchmarking**  
   Evaluate model performance using standard metrics (precision, recall, F1-score, AUC) on selected benchmark datasets. Compare against baseline methods.

5. **Documentation and Reporting**  
   Produce a comprehensive technical report summarizing methodology, experiments, and results. Maintain reproducible code in the project repository.

---

## 5. Expected Outcomes

The project expects to produce:

- A set of engineered behavioral features that capture DNS traffic patterns relevant to anomalies.
- Machine learning models capable of profiling and detecting abnormal DNS traffic with demonstrable performance improvements over basic statistical baselines.
- Empirical benchmarking results on public DNS datasets.
- Open-source code and documentation supporting replicability and future extensions.

---

## 6. References

[1] Saeli, S., Bisio, F., Lombardo, P., & Massa, D. (2020). *DNS Covert Channel Detection via Behavioral Analysis: a Machine Learning Approach*. arXiv:2010.01582. https://arxiv.org/abs/2010.01582   
[2] Mateless, R., & Segal, M. (2019). *Approximate String Matching for DNS Anomaly Detection*. arXiv:1905.09455. https://arxiv.org/abs/1905.09455   
[3] A survey on malicious domains detection using DNS data. ACM Computing Surveys. https://dl.acm.org/doi/10.1145/3191329   
[4] H. Jha, I. Patel, G. Li, A. K. Cherukuri and S. Thaseen, Detection of Tunneling in DNS over HTTPS, 2021 7th International Conference on Signal Processing and Communication (ICSC), Noida, India, 2021, pp. 42-47, [doi: 10.1109/ICSC53193.2021.9673380.](https://ieeexplore.ieee.org/abstract/document/9673380)