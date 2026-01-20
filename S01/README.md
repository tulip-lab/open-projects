[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--AI-orange)](README.md)

# Intrusion Detection via Semantic Drift Attribution

**Project Code:** S01  
**Track:** Security × Artificial Intelligence  
**Revision:** Q1, 2026

---

## 1. Project Background

Network intrusion detection systems (IDS) are critical components of cyber defense that monitor networks for malicious or anomalous behavior. IDS are broadly categorized as signature-based or anomaly-based systems. Anomaly-based systems model normal traffic and flag deviations as potential threats, often employing machine learning to support detection decisions ([turn0search41][turn0search43]).

Modern IDS must operate in dynamic environments where traffic patterns evolve over time due to software updates, network configuration changes, or changes in user behavior. Continual learning methods allow models to adapt incrementally to new data without retraining from scratch. However, existing continual IDS frameworks often assume benign traffic transitions and do not explicitly handle adversarial interference.

Attackers can exploit this gap by inducing semantic drift in learned representations, slowly poisoning memory buffers or adapting attack behavior to evade detection. These adversarially induced changes can degrade the IDS performance over time without triggering conventional drift detectors. This project focuses on distinguishing **natural distribution evolution** from **maliciously induced semantic drift**, thereby enabling more robust and trustworthy continual intrusion detection.

---

## 2. Research Problems

The primary research question is: **How can a continual intrusion detection system distinguish between benign concept evolution and adversarially induced semantic drift, and respond effectively without degrading overall adaptability?**

Key challenges include:

- Developing representation-level metrics that capture semantic changes in network traffic over time.
- Attributing observed drift to benign evolution or adversarial manipulation under partial labels and real-time constraints.
- Designing adaptive model updates and mitigation strategies that prevent drift exploitation without reintroducing forgetting.
- Evaluating robustness under realistic adversarial intrusion scenarios with varying drift intensities and attack patterns.

---

## 3. SOTA Methods and Benchmark Datasets

### 3.1 State-of-the-Art Methods

Representative research related to this project includes:

- **Continual Learning for IDS:** Techniques such as rehearsal, regularization, and parameter isolation are used to maintain performance on previous tasks while learning new patterns. These approaches typically lack explicit adversarial drift attribution.
- **Concept Drift Detection:** Methods for drift detection in data streams identify changes in distribution but are not designed to determine whether drift results from adversarial manipulation ([turn0search39]).
- **Adversarial Machine Learning:** Research on poisoning and evasion attacks informs how malicious changes can disrupt learning systems and motivates the need for robust detection mechanisms ([turn0search42]).

### 3.2 Benchmark Datasets

The following publicly available datasets are widely used for intrusion detection research and support evaluation of continual learning and drift-aware methods:

- **CIC-IDS-2017:** A benchmark network intrusion dataset with multiple attack types and labeled flows. It is widely used for machine learning-based IDS evaluation. Dataset page: https://www.unb.ca/cic/datasets/ids-2017.html 
- **CSE-CIC-IDS-2018:** An updated IDS dataset with diverse traffic and attack scenarios, including flow features extracted by CICFlowMeter. Available via AWS Open Data: https://registry.opendata.aws/cse-cic-ids2018/  
- **BoT-IoT:** A large network traffic dataset with IoT-related attack behaviors suitable for large-scale evaluation. UNSW Canberra project page: https://research.unsw.edu.au/projects/bot-iot-dataset  

These datasets provide traffic capture files (e.g., pcap), flow statistics, and multiple attack categories that support robust testing of detectors under continual and adversarial conditions.

---

## 4. Project Tasks

In this project, students are expected to complete the following tasks:

1. **Literature Review**  
   Conduct a survey of continual learning, concept drift, network IDS, and adversarial machine learning, with emphasis on adversarial drift in streaming models.

2. **Method Design and Implementation**  
   Design and implement a semantic drift attribution framework leveraging embedding divergence metrics, uncertainty scoring, and memory consistency checks.

3. **Experimental Evaluation**  
   Evaluate methods on the benchmark datasets listed above. Metrics should include detection accuracy, forgetting rates, false positives, drift detection precision, and adaptability to benign evolution.

4. **Analysis and Discussion**  
   Provide in-depth analysis of how adversarial drift manifests in learned representations and how attribution methods affect detection robustness.

5. **Reporting and Documentation**  
   Prepare a technical report summarizing methodologies, experiments, results, and conclusions. Maintain reproducible code and experiment logs in the project repository.

---

## 5. Expected Outcomes

Expected project deliverables and outcomes include:

- A formal characterization of adversarial semantic drift in continual intrusion detection settings.
- Practical attribution mechanisms that distinguish benign evolution from malicious drift.
- Empirical evaluation demonstrating improved robustness against adversarial manipulation in continual IDS.
- Reproducible code, benchmark results, and datasets prepared for future research use.

---

## 6. References

[1] Fathima, N. F. A. H., Khraisat, A., S. I. S. P., & Li, G. (2025). *Adaptive memory replay for network intrusion detection: Tackling data drift and catastrophic forgetting*. Computer Networks, 272, 111712. https://doi.org/10.1016/j.comnet.2025.111712  
[2] Gama, J., Žliobaitė, I., Bifet, A., Pechenizkiy, M., & Bouchachia, A. (2014). *A survey on concept drift adaptation*. ACM Computing Surveys, 46(4), 44. https://doi.org/10.1145/2523813  
[3] Sommer, R., & Paxson, V. (2010). *On using machine learning for network intrusion detection*. IEEE Symposium on Security and Privacy, https://ieeexplore.ieee.org/document/5504793/.  
[4] Biggio, B., & Roli, F. (2018). *Wild patterns: Ten years after the rise of adversarial machine learning*. Pattern Recognition, 84, 317-331. https://doi.org/10.1016/j.patcog.2018.07.023  
[5] Concept drift. Wikipedia. https://en.wikipedia.org/wiki/Concept_drift  
[6] Intrusion Detection System, Wikipedia, https://en.wikipedia.org/wiki/Intrusion_detection_system 