---
layout: archive
title: "Research interests"
permalink: /research/
author_profile: true
---

My research focuses on **safety control** and **networked control systems**. My aim is to contribute to the development of mathematical and algorithmic tools for designing controllers that guarantee safety properties of large-scale systems. A key component of my research is the design of **resource-aware** controllers for networked systems, while ensuring performance and safety specifications.

By combining these areas, I strive to contribute to the development of robust and efficient control tools for the next-generation of **cyber-physical systems**.

# Some of my recent works

### Over-Approximations with Previews for correct-by-Design Control

**For a blog post about this work, [click here](/over_approx_preview/).**

An **over-approximation** replaces a deterministic nonlinear system with a nondeterministic linear system such that the trajectory of the nonlinear system is one of the possible trajectories of the nondeterministic over-approximation. If a control policy guarantees safety for all trajectories of the over-approximation, then the same policy is guaranteed to ensure safety for the original system.

* While the over-approximation error is traditionally treated as an unknown disturbance, we show that it can instead be regarded as **input-dependent preview information** that can be exploited by the policy (see figure below).

* We show that at runtime, such a disturbance-dependent policy can be concretized efficiently via **fixed-point theory**.

<br/><img src='/images/preview_diagram.png'>


Related paper:
* Antoine Aspeel, Antoine Girard, Thiago Alves Lima. [Exploiting Over-Approximation Errors as Preview Information for Nonlinear Control](https://arxiv.org/abs/2511.03577).

### Lifted Systems for Correct-by-Design Control

* We introduce _lifted systems_ as a generalization of finite-dimensional Koopman approximations to systems with inputs.
* A notion of simulation relation is defined between lifted systems. It is proved that this simulation relation implies the containment of both the open- and closed-loop behaviors.
* These results enable us to compare different lifting functions and alternative lifted systems in terms of their usefulness in control design.
* This simalation relation generalizes (i) hybridizations, (ii) approximate immersions, and (iii) Koopman over-approximations.
* Can be used to enforce specifications (or to compute backward reachable sets).

<br/><img src='/images/Koopman_scheme.png'>

Related papers:
* Antoine Aspeel, Necmiye Ozay. [A Simulation Preorder for Koopman-like Lifted Control Systems](https://arxiv.org/abs/2401.14909). ([Slides](/files/slides_lifted_systems.pdf), [Poster](/files/poster_simulation_lifted_system.pdf))
* Haldun Balim, Antoine Aspeel, Zexiang Liu, and Necmiye Ozay. [Koopman-inspired Implicit Backward Reachable Sets for Unknown Nonlinear Systems](https://ieeexplore.ieee.org/abstract/document/10153400). ([Slides](/files/slides_Koopman_BRS_CDC.pdf), [Poster](/files/poster_Koopman_BRS.pdf))

### Minimum Sensors-to-Actuators Communication

**For a blog post about this work, [click here](/min_communication/).**

* Design a controller that can be implemented with a minimum number of sensor-to-actuator messages, while satisfying safety constraints.
* Reduces to a matrix rank minimization problem.
* Solution relies on a new matrix factorization that decomposes the controller 𝐊 into an encoder 𝐄 and a decoder 𝐃.

<br/><img src='/images/causal_facto.png'>

Related papers:
* Antoine Aspeel, Jakob Nylof, Jing Shuang (Lisa) Li, and Necmiye Ozay. [A Low Rank Approach to Minimize Sensor-to-Actuator Communication in Finite Horizon Output Feedback](https://ieeexplore.ieee.org/abstract/document/10336872). ([Slides](/files/slides_causal_factorization.pdf))
* Antoine Aspeel, Laurent Bako, Necmiye Ozay. [Minimal L2-Consistent Data-Transmission](https://arxiv.org/abs/2408.04012).

### Sparse Sensors and Actuators Activation

* Minimize the use of sensors and actuators, while satisfying safety constraints.
* Sensors/actuators sparsity is encoded as a linear constraint. We prove that this constraint remains linear after Youla parameterization.
* This leads to a scalable method for sensors/actuators scheduling.

<br/><img src='/images/drone.png'>

See the paper: Antoine Aspeel, Kwesi Rutledge, Raphaël M Jungers, Benoit Macq, and Necmiye Ozay. [Optimal control for linear networked control systems with information transmission constraints](https://ieeexplore.ieee.org/document/9683476).

# About my PhD Thesis

**For a blog post about my PhD work, [click here](/phd_thesis/).**

My PhD thesis was driven by an applied problem in proton therapy. Essentially, proton therapy aims to destroy tumors using a proton beamline, requiring precise knowledge of the tumor's position. This becomes challenging with mobile tumors, like lung tumors, which move with the patient's breathing.

One approach to address this is to use X-ray images of the patient's chest to measure the tumor's position. However, X-ray imaging exposes the patient, including healthy tissue, to radiation. Therefore, the number of X-ray images that can be taken is limited.

My thesis tackles the problem of _determining the optimal timing for X-ray acquisitions, given a limited budget, to achieve the best tracking of the tumor's position_. From a broader perspective, this problem can be formulated as **optimizing the measurement times to obtain the best state estimation of a dynamic system.** I studied this problem under different assumptions (linear vs. nonlinear dynamics, expected vs. worst case error).

During my PhD, **I had the privilege of collaborating with [IBA](https://www.iba-worldwide.com/), the world leader in proton therapy**. This collaboration enabled me to bridge the gap between theory and practice by applying the methods I developed to tumor tracking using real medical data.

My PhD thesis **_Optimal Sampling for State Estimation of Stochastic Dynamical Systems_** completed under the supervision of [Prof. Raphaël Jungers](https://perso.uclouvain.be/raphael.jungers/content/home) and [Prof. Benoît Macq](https://pilab.be/about-me/?p=benoit_macq), is available [here](https://dial.uclouvain.be/pr/boreal/object/boreal%3A264180/datastream/PDF_01/view). The slides of my PhD defense are available [here](/files/private_PhD_defense.pdf).

# About my Master Thesis (on graph theory)

**For a blog post about my Master Thesis [click here](/master_thesis/).**

# Some topics I like (non-exhaustive and unordered list)

* Hybrid systems theory
* Formal methods
* Reachability analysis
* Scenario optimization
* Polynomial optimization (sum of squares)
* Youla parameterization and System level synthesis
* Reinforcement learning (and inverse reinforcement learning)
* Koopman theory
