# Advanced geospatial methods

A repository containing introductions to advanced geospatial methods.

---

## Summary table

| # | Method | Description | Package | Reference |
|---|--------|-------------|---------|-----------|
| 1 | Neural networks for geospatial data | NN-GLS: combines MLP, Gaussian processes, and GLS loss for spatial data analysis | [geospaNN](https://pypi.org/project/geospaNN) | [Zhan & Datta (2024)](https://www.tandfonline.com/doi/abs/10.1080/01621459.2024.2356293) |
| 2 | Multiscale Similarity and Geographically Weighted Regression | M-SGWR: extends GWR by combining geographic proximity and attribute similarity via predictor-specific alpha weights | [M-SGWR](https://github.com/Lessani252/M-SGWR) | [Lessani & Li (2026)](https://arxiv.org/abs/2601.19888) |

---

## 1. Neural networks for geospatial data: an application of GeospaNN

### Overview

**GeospaNN** is a Python package that implements **NN-GLS** (Neural Networks with Generalized Least Squares), a geographically-informed Graph Neural Network (GNN) for analyzing large and irregular geospatial data. The method was proposed by Zhan & Datta (2024) and explicitly accounts for spatial correlation in the data.

Geospatial data naturally exhibits spatial dependence. Traditional geostatistical methods handle this through model-based approaches such as Gaussian processes (GP), while artificial neural networks (NNs) can capture non-linear regression functions but typically ignore spatial correlation. **NN-GLS** bridges these two worlds:

- A **multi-layer perceptron (MLP)** models the non-linear regression function *f(x)*.
- A **Gaussian process (GP)** models the spatially correlated errors.
- The resulting loss function is a **Generalized Least Squares (GLS) loss** informed by the GP covariance matrix, which explicitly incorporates spatial correlation into the NN optimisation.

Zhan & Datta (2024) show that NN-GLS can be represented as a **Graph Neural Network (GNN)**, where GP covariances guide the neighbourhood aggregation on the output layer. The package is built on [PyTorch](https://pytorch.org/) and [PyTorch Geometric (PyG)](https://pytorch-geometric.readthedocs.io/en/latest/).

To scale to large datasets (up to ~500,000 observations), **geospaNN** approximates the working correlation structure using the **Nearest Neighbor Gaussian Process (NNGP)** (Datta et al., 2016).

### Key features

- Regression function estimation via MLP + GLS loss.
- Spatial prediction (kriging) using the fitted GP.
- Scales to sample sizes of hundreds of thousands.
- Complete geospatial analysis pipeline.

### Package

- **PyPI**: [https://pypi.org/project/geospaNN](https://pypi.org/project/geospaNN)
- **Documentation & examples**: [https://wentaozhan1998.github.io/geospaNN-doc/](https://wentaozhan1998.github.io/geospaNN-doc/)
- **Source code**: [https://github.com/WentaoZhan1998/geospaNN](https://github.com/WentaoZhan1998/geospaNN)

### Authors

**Wentao Zhan** (wzhan3@jhu.edu) and **Abhirup Datta** (abhidatta@jhu.edu), Johns Hopkins University.

### Reference

Zhan, W., & Datta, A. (2024). Neural networks for geospatial data. *Journal of the American Statistical Association*, 119(548), 1–13. <https://www.tandfonline.com/doi/abs/10.1080/01621459.2024.2356293>

> Acknowledgement: This work is supported by National Institute of Environmental Health Sciences grant R01ES033739.

---

## 2. Multiscale Similarity and Geographically Weighted Regression: an application of M-SGWR

### Overview

**M-SGWR** (Multiscale Similarity-based Geographically Weighted Regression) extends traditional local regression frameworks—GWR and MGWR—by characterising spatial interaction across two dimensions: **geographic proximity** and **attribute (variable) similarity**. For each predictor, geographic and attribute-based weight matrices are constructed separately and combined using an optimised parameter *alpha*, which governs their relative contribution to local model fitting. Analogous to variable-specific bandwidths in MGWR, the optimal *alpha* varies by predictor, allowing the model to account for purely geographic, mixed, or non-spatial (remote similarity) effects. Simulation experiments and an empirical application show that M-SGWR consistently outperforms GWR, SGWR, and MGWR across all goodness-of-fit metrics.

### Key features

- Dual-dimension weighting: geographic proximity + attribute similarity per predictor.
- Predictor-specific *alpha* optimisation (analogous to variable-specific bandwidths in MGWR).
- Compatible with standard GWR diagnostics (AIC, AICc, local R², t-values).

### Package

- **Source code**: [https://github.com/Lessani252/M-SGWR](https://github.com/Lessani252/M-SGWR)

### Authors

**Alireza Lessani** and **Zhenlong Li**, University of South Carolina.

### Reference

Lessani, A., & Li, Z. (2026). Multiscale similarity and geographically weighted regression. *arXiv preprint*. <https://arxiv.org/abs/2601.19888>
