[![GitHub watchers](https://img.shields.io/badge/tulip--lab-Open--Projects-brightgreen)](../README.md)
[![GitHub watchers](https://img.shields.io/badge/Track-Security--Computational--Modelling-orange)](../README.md#ledger-coursework-research--projects)

# Dynamic Intervention for Misinformation Mitigation

**Project Code:** S15\
**Track:** Security × Computational Modelling\
Project Supervisor :point_right: : [Dr Xiaojuan Cheng](https://www.tulip.academy/members/)\
**Revision:** Q4, 2026

---

## 1. Project Background

Online misinformation can spread rapidly through social networks and influence large numbers of users before corrective information reaches them. Information managers, platforms, fact-checking organisations, and other stakeholders may therefore need to intervene during the propagation process by promoting corrective information, reducing the visibility of misleading content, or increasing mitigation effort.

A key practical difficulty is that intervention resources are limited. Applying a high intervention intensity throughout the entire propagation period may be costly or unnecessary, while weak intervention may fail to reduce misinformation effectively. The intervention effort should therefore change over time according to the evolving propagation state.

This project studies misinformation mitigation as a dynamic intervention problem. Instead of applying the same mitigation effort at all times, students will investigate how the intervention intensity should evolve during the propagation process in order to balance misinformation reduction and resource use.

The project is designed for undergraduate students interested in research. Prior knowledge of epidemic modelling or optimal control is not required. Students will first build a simple misinformation propagation simulation and then gradually formulate and solve a dynamic intervention problem.

For an extension that jointly optimises intervention timing and intensity, see [S16: Adaptive Timing and Intensity of Misinformation Intervention](../S16/README.md).

---

## 2. Research Problems

The primary research question is:

**How should an information manager dynamically adjust intervention intensity over time to mitigate misinformation propagation effectively under limited resources?**

Key research questions include:

- How does misinformation evolve under different propagation conditions when no intervention is applied?
- How does a constant intervention strategy compare with a dynamically adjusted intervention strategy?
- How should intervention strategies adapt as misinformation propagation evolves over time?

---

## 3. Related Methods and Experimental Settings

### 3.1 Related Methods

Representative methods related to this project include:

- **Misinformation Propagation Modelling:** Misinformation spreading can be described using state-transition models, where users move between different information states according to their interactions with others. These models provide a dynamic environment for studying misinformation evolution and intervention.
- **Dynamic Mitigation Modelling:** Mitigation mechanisms can be incorporated into the propagation dynamics to represent corrective information, awareness campaigns, content moderation, or other management actions. The effectiveness of intervention may vary over time as the propagation process evolves.
- **Optimal Control:** Intervention strategy can be modelled as a time-dependent control variable. Optimal-control methods can then be used to determine how mitigation effort should evolve over time while balancing misinformation reduction and intervention resource use.

A solid mathematical background is required, as the project involves advanced mathematical derivations.

### 3.2 Experimental Settings

This project primarily uses controlled simulation environments to investigate misinformation propagation and mitigation under different conditions.

Suggested simulation environments include:

- **Synthetic Social Networks:**
  Random, scale-free, and realistic networks may be used to represent different patterns of social connectivity.

- **Resource Conditions:**
  Different intervention budgets or resource constraints may be used to examine how mitigation strategies change under limited resources.

Possible public misinformation datasets may be incorporated as extensions where suitable network or cascade information is available, but real-world data are not required for the minimum project outcome.

---

## 4. Project Tasks

In this project, students are expected to complete the following tasks:

### 4.1 Literature Review

Conduct a focused review of misinformation propagation, misinformation mitigation, dynamic intervention, and basic optimal-control or numerical-optimisation approaches.

### 4.2 Propagation Model and Simulation

Implement a simple misinformation propagation model on a social network. The simulator should support configurable initial conditions, propagation parameters, and time-varying spreading behaviour.

### 4.3 Baseline Intervention Strategies

Implement several simple baselines, such as:

- no intervention;
- constant weak intervention;
- constant medium intervention;
- constant strong intervention;
- random intervention.

### 4.4 Dynamic Intervention Formulation

Represent the intervention intensity as a time-dependent decision variable $u(t)$. Define an objective that accounts for both misinformation impact and intervention resource use.

### 4.5 Optimal-Control Analysis and Solution

Derive the necessary optimality conditions for the dynamic intervention problem and implement a numerical method to obtain the resulting intervention strategy.

### 4.6 Experimental Evaluation

Evaluate the dynamic intervention strategy under different:

- intervention budgets;
- network structures;
- time-varying propagation scenarios.

Evaluation metrics may include cumulative misinformation exposure, peak prevalence, final prevalence, and objective value.

### 4.7 Analysis and Discussion

Analyse how the optimal intervention strategy changes under different propagation and resource conditions. Particular attention should be paid to how intervention intensity evolves over time and how resource limitations influence the resulting strategy.

### 4.8 Reporting and Documentation

Prepare a technical report summarising the methodology, experiments, results, limitations, and conclusions. Maintain reproducible code and experiment logs in the project repository.

---

## 5. Expected Outcomes

By completing this project, students will gain a practical understanding of dynamic misinformation mitigation using optimal-control methods. Expected outcomes include a working propagation and intervention model, an optimized time-varying mitigation strategy, empirical insights into how intervention intensity changes under different propagation and resource conditions, and a reproducible implementation with a technical research report.

---

## 6. References

[1] Xie, K., & Wang, S. (2025). A Survey on False Information Detection: From A Perspective of Propagation on Social Networks. arXiv preprint arXiv:2506.18052. https://arxiv.org/abs/2506.18052

[2] Lazer, D. M. J., et al. (2018). *The science of fake news*. Science, 359(6380), 1094–1096.
https://doi.org/10.1126/science.aao2998

[3] Pastor-Satorras, R., Castellano, C., Van Mieghem, P., & Vespignani, A. (2015). Epidemic processes in complex networks. Reviews of Modern Physics, 87(3), 925–979. https://doi.org/10.1103/RevModPhys.87.925

[4] Lenhart, S., & Workman, J. T. (2007). *Optimal Control Applied to Biological Models*. Chapman & Hall/CRC.

[5] Sun, L., Rao, Y., Wu, L., Zhang, X., Lan, Y., & Nazir, A. (2023). Fighting False Information from Propagation Process: A Survey. ACM Computing Surveys, 55(10), Article 207, 1–38. https://doi.org/10.1145/3563388
