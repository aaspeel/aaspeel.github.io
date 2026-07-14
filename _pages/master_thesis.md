---
layout: archive
title: ""
permalink: /master_thesis/
author_profile: true
---

# Master Thesis — Community detection for time varying networks

My first step into research started with my Master's thesis (2016-2017) on large time-varying networks with Prof. [Jean-Charles Delvenne](https://perso.uclouvain.be/jean-charles.delvenne/welcome.html).

* Antoine Aspeel. [Community Detection in Large-Scale Time-Varying Networks, A Modularity Based Approach](https://thesis.dial.uclouvain.be/entities/masterthesis/112ea7fb-6274-4280-8fed-eeeb671ac437), 2017

In my Master's thesis, we developed fast optimization methods for community detection in time-varying graphs, that is, graphs where nodes and edges are added and removed. This work led to the following publications in SIAM journals:

* Michaël Fanuel, Antoine Aspeel, Michael T Schaub, Jean-Charles Delvenne. [Ellipsoidal embeddings of graphs](https://arxiv.org/abs/2403.15023). _SIAM Journal on Applied Mathematics_, 2024.

* Michaël Fanuel, Antoine Aspeel, Jean-Charles Delvenne, and Johan AK Suykens. [Positive semi-definite embedding for dimensionality reduction and out-of-sample extensions](https://epubs.siam.org/doi/10.1137/20M1370653). _SIAM Journal on Mathematics of Data Science_, 2022.

A common paradigm for community detection is to find a partition of the nodes that maximizes the **modularity**, a measure of the quality of the partition with respect to the graph structure [1].

The Louvain method has been proposed as an efficient heuristic to maximize modularity [2]. It proceeds by creating a hierarchical community structure: nodes are grouped into communities, and communities are grouped into communities-of-communities, etc. While offering computational benefits, the Louvain method and its hierarchical structure are not well-suited for time-varying graphs.

* <u>Challenge:</u> **Classical community detection methods, such as the Louvain algorithm, are not well-suited for time-varying graphs.** When the graph changes, these methods require recalculating the community structure from scratch, failing to leverage previous computations to adapt efficiently to the changes.

* <u>Solution:</u> To face this issue, the method I developed in my Master's thesis is based on **graph embedding**, where each node of the graph is associated with a point on a \\((r-1)\\)-dimensional sphere \\(\mathbb{S}^{r-1}\subset\mathbb{R}^r\\). Then, modularity maximization is relaxed into a smooth optimization problem over the sphere. The manifold structure of the sphere allows to use efficient methods for constrained optimization [3]. Then, the community structure of the graph is obtained by clustering the points on the sphere using the \\(k\\)-means algorithm.

> **A key advantage of our embed-and-partition approach is its adaptability to time-varying graphs.** When the graph undergoes changes, the existing embedding can serve as a warm start for the iterative optimization process, significantly reducing computational time.


## Embeddings are low dimensional

A natural question that arises when using our method is how to choose the embedding dimension \\(r\\) for the sphere \\(\mathbb{S}^{r-1}\\). Indeed, this is a user-defined parameter with no _a priori_ upper bound. In addition, using a large \\(r\\) increases the dimension of the optimization problem, leading to more computation time.

However, **numerical demonstrations show that the optimal embedding is often very low dimensional**, allowing one to choose a small value for the embedding dimension \\(r\\) without compromising the quality of the solution (see figures below). **We have been able to provide a theoretical explanation to the low dimensionality of the embeddings.** Indeed, we proved that the optimization problem we are solving to find the graph embedding is equivalent to a nuclear norm minimization subject to linear constraints. Since the nuclear norm is the tightest convex relaxation of the rank [4], it promotes low rank solutions which correspond to low-dimensional embeddings. **This finding provides theoretical support for the use of low-dimensional embeddings, resulting in significant reductions in computation time.**

<figure>
  <img src="/images/LFR_toy_1_embedding.png" alt="Description" width="300">
  <figcaption>
    Modularity-based embedding for a graph with 4 planted communities represented by the different colors. The graph has 2000 nodes and the embedding dimension \( r=10 \). Our embed-and-cluster method retrieves exactly these communities.
  </figcaption>
</figure>

<figure>
  <img src="/images/LFR_toy_1_spectrum.png" alt="Description" width="300">
  <figcaption>
    The eigenvalues of the solution, showing its low dimensionality. The effective dimension is 3, so that choosing \( r=3 \) instead of \( r=10 \) gives the same solution.
  </figcaption>
</figure>

## References

[1] M. E. Newman and M. Girvan, "Finding and evaluating community structure in networks," _Physical review E_, vol. 69, no. 2, p. 026 113, 2004.

[2] V. D. Blondel, J.-L. Guillaume, R. Lambiotte, and E. Lefebvre, "Fast unfolding of communities in large networks," _Journal of statistical mechanics: theory and experiment_, vol. 2008, no. 10, P10008, 2008.

[3] P.-A. Absil, R. Mahony, and R. Sepulchre, _Optimization algorithms on matrix manifolds._ Princeton University Press, 2008.

[4] M. Fazel, H. Hindi, and S. P. Boyd, "A rank minimization heuristic with application to minimum order system approximation," in _Proceedings of the 2001 American Control Conference._, IEEE, vol. 6, 2001, pp. 4734–4739.