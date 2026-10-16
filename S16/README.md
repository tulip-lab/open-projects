[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--Computational--Modelling-orange)](../README.md#ledger-coursework-research--projects)

# Adaptive Timing and Intensity of Misinformation Intervention

**Project Code:** S16\
**Track:** Security × Computational Modelling\
Project Supervisor :point_right: : [Dr Xiaojuan Cheng](https://www.tulip.academy/members/)\
**Revision:** Q4, 2026

---

## 1. Project Background

Misinformation propagation is rarely constant over time. Public attention, user activity, external events, and platform dynamics may cause spreading risk to increase, decrease, or exhibit multiple peaks. Under such conditions, deciding only how much intervention to apply is not sufficient. An information manager must also decide when intervention should occur.

Intervening too early may use limited resources before they are needed, while intervening too late may allow misinformation to grow beyond easy control. The strength of an intervention is also linked to its timing: an early intervention may require only moderate effort, whereas a delayed intervention may require a stronger response.

This project studies misinformation mitigation as a joint intervention timing and intensity optimisation problem. Rather than assuming that intervention opportunities are fixed in advance, both the intervention times and the corresponding intervention intensities are determined computationally according to the evolving propagation process.

The project extends the basic dynamic-mitigation setting and is intended for students who are comfortable with programming, simulation, and numerical optimisation. Prior knowledge of optimal control theory is helpful but not required.

For the foundational dynamic intervention intensity problem, see [S15: Dynamic Intervention for Misinformation Mitigation](../S15/README.md).

---

## 2. Research Problems

The primary research question is:

**When should an information manager intervene, and how strong should each intervention be, when misinformation propagation changes over time?**

Key research questions include:

- How should intervention times adapt to increasing, decreasing, single-peak, or multi-peak propagation patterns?
- How are intervention timing and intervention intensity coupled?
- How robust are the resulting intervention schedules when propagation patterns or model parameters change?

---

## 3. Related Methods and Experimental Settings

### 3.1 Related Methods

Representative methods related to this project include:

- **Time-Varying Misinformation Propagation:**
  Misinformation propagation may change over time due to variations in user activity, attention, or external events. Time-varying propagation models provide a basis for studying how intervention decisions should adapt to evolving propagation conditions.

- **Misinformation Mitigation Modelling:**
  Mitigation mechanisms can be incorporated into misinformation propagation models to represent corrective information, awareness campaigns, content moderation, or other management actions.

- **Dynamic Intervention Optimisation:**
  Intervention timing and intensity can be jointly considered as decision variables, allowing mitigation strategies to adapt to changes in the propagation process and available resources.

A key challenge is to determine when intervention should occur and how strongly the information manager should intervene as misinformation propagation evolves over time.

### 3.2 Experimental Environments

This project primarily uses controlled simulation environments to investigate misinformation propagation and intervention under different conditions.

Suggested simulation settings include:

- **Synthetic Social Networks:**
  Random, scale-free, and realistic networks may be used to represent different patterns of social connectivity.

- **Propagation Conditions:**
  Different time-varying propagation patterns may be considered to represent changing misinformation risks over time.

---

## 4. Project Tasks

In this project, students are expected to complete the following tasks:

### 4.1 Literature Review

Conduct a focused review of misinformation propagation, misinformation mitigation, intervention timing, and dynamic intervention optimisation.

### 4.2 Time-Varying Propagation Simulation

Develop a misinformation propagation simulator in which the spreading process changes over time. Implement several interpretable propagation scenarios, such as increasing, decreasing, peak-shaped, or multi-wave spreading.

### 4.3 Baseline Intervention Strategies

Implement and evaluate several simple intervention baselines, including fixed-timing, fixed-intensity, periodic, and randomly timed intervention strategies, together with a no-intervention baseline.

### 4.4 Joint Timing-Intensity Formulation

Formulate the intervention problem so that both intervention timing and intervention intensity can be determined dynamically. Each intervention may be represented by:

$$
(\tau_k, u_k)
$$

where $\tau_k$ denotes the intervention time and $u_k$ denotes the intervention intensity.

### 4.5 Method Design and Implementation

Develop and implement a computational method for jointly determining:

- when interventions should occur; and
- how strong each intervention should be.

### 4.6 Experimental Evaluation

Evaluate the proposed intervention strategy under different propagation conditions, initial misinformation levels, intervention settings, and network structures.

Evaluation metrics may include cumulative misinformation exposure, peak prevalence, final prevalence, intervention cost, and intervention timing.

### 4.7 Analysis and Discussion

Analyse how intervention timing and intensity change as the misinformation propagation process evolves, and investigate the relationship between intervention timing, intervention strength, and mitigation effectiveness.

### 4.8 Reporting and Documentation

Prepare a technical report summarising the model, methodology, experiments, results, and conclusions. Maintain reproducible code and experiment logs in the project repository.

---

## 5. Expected Outcomes

By completing this project, students will gain practical experience in time-varying misinformation simulation, intervention optimisation, and research-oriented experimentation. Expected outcomes include a working misinformation propagation simulator, a computational framework for jointly optimising intervention timing and intensity, empirical insights into how intervention strategies adapt to evolving propagation conditions, and reproducible code with a technical research report.

---

## 6. References

[1] Xie, K., & Wang, S. (2025). A Survey on False Information Detection: From A Perspective of Propagation on Social Networks. arXiv preprint arXiv:2506.18052. https://arxiv.org/abs/2506.18052

[2] Sun, L., Rao, Y., Wu, L., Zhang, X., Lan, Y., & Nazir, A. (2023). Fighting False Information from Propagation Process: A Survey. ACM Computing Surveys, 55(10), Article 207, 1–38. https://doi.org/10.1145/3563388

[3] X. Cheng, L.-X. Yang, Q. Zhu, C. Gan and G. Li, "Impulse Strategies for Suppressing Cyber Propaganda With Awareness," in IEEE Transactions on Computational Social Systems, vol. 12, no. 5, pp. 2685-2695, Oct. 2025, https://doi.org/10.1109/TCSS.2024.3522889

[4] Nowzari, C., Preciado, V. M., & Pappas, G. J. (2016). Analysis and Control of Epidemics: A Survey of Spreading Processes on Complex Networks. IEEE Control Systems Magazine, 36(1), 26–46. https://doi.org/10.1109/MCS.2015.2495000
