[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](../README.md#ledger-coursework-research--projects)

# Detection of Encrypted DNS Traffic  

**Project Code:** S03  
**Track:** Security × Artificial Intelligence  
Project Supervisor :point_right: : To be confirmed.\
**Revision:** Q4, 2026

---

## 1. Project Background

The Domain Name System (DNS) has traditionally operated in clear text, making it easy for network operators and security systems to inspect DNS queries and responses. In response to widespread privacy concerns, encrypted DNS protocols such as **DNS over HTTPS (DoH)** and **DNS over TLS (DoT)** have been standardized and increasingly adopted by browsers, operating systems, and public resolvers.

While DoH and DoT significantly improve user privacy, they also introduce substantial challenges for network security. Encryption prevents traditional payload inspection and signature-based detection, reducing the visibility of DNS traffic and enabling attackers to hide malicious activities such as command-and-control communication, data exfiltration, and covert channels inside encrypted DNS flows.

This project focuses on the **detection of encrypted DNS traffic**, with an emphasis on identifying DoH and DoT usage and distinguishing benign encrypted DNS from malicious or policy-violating behavior. The goal is to explore how traffic analysis, flow-level features, and machine learning can restore security visibility without breaking encryption or violating privacy principles.

---

## 2. Research Problems

The core research questions addressed in this project include:

- How can encrypted DNS traffic (DoH / DoT) be reliably identified at the network level without decrypting payloads?
- What traffic features and behavioral patterns distinguish DoH / DoT from regular HTTPS or TLS traffic?
- How can malicious usage of encrypted DNS (e.g., tunneling, C2 communication) be differentiated from benign resolver traffic?
- What are the trade-offs between detection accuracy, false positives, and privacy preservation?

Key challenges arise from protocol mimicry, encrypted payloads, shared infrastructure (e.g., CDNs), and the overlap between DoH traffic and ordinary HTTPS flows.

---

## 3. SOTA Methods and Benchmark Datasets

### 3.1 State-of-the-Art Methods

Representative approaches in the literature include:

- **Flow-based and Statistical Detection:**  
  Methods that rely on packet sizes, timing patterns, burst behavior, and TLS handshake characteristics to identify DoH / DoT traffic without decryption.

- **Machine Learning for Encrypted Traffic Analysis:**  
  Supervised and unsupervised models trained on flow-level features to classify encrypted DNS traffic and detect anomalies.

- **Behavioral and Temporal Modeling:**  
  Techniques that exploit resolver interaction patterns, query periodicity, and session behavior to separate benign and malicious encrypted DNS usage.

- **Policy-Aware Detection:**  
  Approaches that detect policy violations, such as unauthorized use of public DoH resolvers in enterprise networks.

These methods demonstrate feasibility but often struggle with generalization across networks and evolving protocol implementations.

---

### 3.2 Benchmark Datasets

The primary benchmark is **CIRA-CIC-DoHBrw-2020**, which includes benign DoH, malicious DoH tunneling, and non-DoH traffic. It provides traffic captures and extracted features for evaluating encrypted DNS classification and tunneling detection.

Dataset and source documentation: https://www.unb.ca/cic/datasets/dohbrw-2020.html

This benchmark supports DoH experiments. DoT detection requires a separately verified dataset or a documented, authorised traffic-collection setup. Clear-text DNS and VPN datasets should not be presented as DoH or DoT benchmarks without checking their protocols and labels.

---

## 4. Project Tasks

In this project, students are expected to complete the following tasks:

1. **Literature Review**  
   Review encrypted DNS protocols, privacy motivations, and existing detection approaches for DoH / DoT traffic.

2. **Traffic Feature Analysis**  
   Identify discriminative flow-level and temporal features relevant to encrypted DNS detection.

3. **Model Design and Implementation**  
   Develop machine learning models for detecting DoH / DoT traffic and identifying anomalous or malicious encrypted DNS behavior.

4. **Experimental Evaluation**  
   Evaluate detection accuracy, false positive rates, robustness across datasets, and sensitivity to protocol variations.

5. **Analysis and Reporting**  
   Analyze results, discuss privacy–security trade-offs, and document findings in a structured technical report.

---

## 5. Expected Outcomes

Expected outcomes of this project include:

- A systematic analysis of encrypted DNS traffic characteristics.
- Detection models capable of identifying DoH / DoT traffic without payload decryption.
- Empirical evaluation of robustness and generalization across datasets.
- Reproducible experimental code and benchmark results.

The project aims to provide practical insights into balancing privacy protection and network security in modern encrypted environments.

---

## 6. References

[1] Böttger, T., Cuadrado, F., Antichi, G., Fernandes, E. L., Tyson, G., Castro, I., & Uhlig, S. (2019). *An Empirical Study of the Cost of DNS-over-HTTPS*. ACM Internet Measurement Conference. https://arxiv.org/abs/1909.06192

[2] MontazeriShatoori, M., Davidson, L., Kaur, G., & Lashkari, A. H. (2020). *Detection of DoH Tunnels using Time-series Classification of Encrypted Traffic*. The 5th IEEE Cyber Science and Technology Congress. Citation and dataset documentation: https://www.unb.ca/cic/datasets/dohbrw-2020.html

[3] Jha, H., Patel, I., Li, G., Cherukuri, A. K., & Thaseen, S. (2021). *Detection of Tunneling in DNS over HTTPS*. 7th International Conference on Signal Processing and Communication (ICSC), 42–47. https://doi.org/10.1109/ICSC53193.2021.9673380

[4] Canadian Institute for Cybersecurity. *CIRA-CIC-DoHBrw-2020*. University of New Brunswick. https://www.unb.ca/cic/datasets/dohbrw-2020.html
