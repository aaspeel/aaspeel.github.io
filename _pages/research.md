---
layout: archive
title: "Research interests"
permalink: /research/
author_profile: true
---

My research focuses on **safety control** and **networked control systems**. My aim is to contribute to the development of mathematical and algorithmic tools for designing controllers that guarantee safety properties of large-scale systems. A key component of my research is the design of **resource-aware** controllers for networked systems, while ensuring performance and safety specifications.

By combining these areas, I strive to contribute to the development of robust and efficient control tools for the next-generation of **cyber-physical systems**.

# Overview of some of my recent works

### Koopman-like Lifted Systems for Correct-by-Design Control

* We introduce _lifted systems_ as a generalization of finite-dimensional Koopman approximations to systems with inputs.
* A notion of simulation relation is defined between lifted systems. It is proved that this simulation relation implies the containment of both the open- and closed-loop behaviors.
* These results enable us to compare different lifting functions and alternative lifted systems in terms of their usefulness in control design.
* This simalation relation generalizes (i) hybridizations, (ii) approximate immersions, and (iii) Koopman over-approximations.
* Can be used to enforce specifications (or to compute backward reachable sets).

<br/><img src='/images/Koopman_scheme.png'>

See the paper: Antoine Aspeel, Necmiye Ozay. [A Simulation Preorder for Koopman-like Lifted Control Systems](https://arxiv.org/abs/2401.14909). Presentation in _The 8th IFAC Conference on Analysis and Design of Hybrid Systems_, 2024. (accepted for publication). Some slides are available [here](/files/slides_lifted_systems.pdf), and a poster is available [here](/files/poster_simulation_lifted_system.pdf).

### Minimum Sensors-to-Actuators Communication

* Design a controller that can be implemented with a minimum number of sensor-to-actuator messages, while satisfying safety constraints.
* Reduces to a matrix rank minimization problem.
* Solution relies on a new matrix factorization that decomposes the controller 𝐊 into an encoder 𝐄 and a decoder 𝐃.

<br/><img src='/images/causal_facto.png'>

See the paper: Antoine Aspeel, Jakob Nylof, Jing Shuang (Lisa) Li, and Necmiye Ozay. [A Low Rank Approach to Minimize Sensor-to-Actuator Communication in Finite Horizon Output Feedback](https://ieeexplore.ieee.org/abstract/document/10336872). _IEEE Control Systems Letters_, 2023.

### Sparse Sensors and Actuators Activation

* Minimize the use of sensors and actuators, while satisfying safety constraints.
* Sensors/actuators sparsity is encoded as a linear constraint. We prove that this constraint remains linear after Youla parameterization.
* This leads to a scalable method for sensors/actuators scheduling.

<br/><img src='/images/drone.png'>

See the paper: Antoine Aspeel, Kwesi Rutledge, Raphaël M Jungers, Benoit Macq, and Necmiye Ozay. [Optimal control for linear networked control systems with information transmission constraints](https://ieeexplore.ieee.org/document/9683476). In _The 60th IEEE International Conference on Decision and Control_, 2021.


# Some things I like (non-exhaustive and unordered list)

* Hybrid systems theory
* Formal methods
* Reachability analysis
* Koopman theory
* Scenario optimization
* Polynomial optimization (sum of squares)
* System level synthesis
* Youla parameterization
* Reinforcement learning (and inverse reinforcement learning)