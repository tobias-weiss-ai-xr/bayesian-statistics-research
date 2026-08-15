<h1 align="center">
  <strong>Bayesian Statistics Research Corpus</strong>
</h1>
<h3 align="center">Data-driven, auto-validated literature review for Bayesian statistics</h3>

<div align="center">

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![CI](https://img.shields.io/github/actions/workflow/status/tobias-weiss-ai-xr/bayesian-statistics-research/validate.yml?label=CI&logo=github)](https://github.com/tobias-weiss-ai-xr/bayesian-statistics-research/actions/workflows/validate.yml)
[![GitHub Pages](https://img.shields.io/badge/Demo-GitHub%20Pages-brightgreen.svg?logo=github)](https://tobias-weiss-ai-xr.github.io/bayesian-statistics-research/)

</div>

> 📊 **Bayesian statistics research corpus:** inference, computation, prior modeling,
> model selection, hierarchical and nonparametric Bayes, Bayesian deep learning, and
> applications — analyzed with the same taxonomy → momentum → burst → gap pipeline as
> [graph-research](https://github.com/tobias-weiss-ai-xr/graph-research) and
> [ai-literacy-research](https://github.com/tobias-weiss-ai-xr/ai-literacy-research).

## What you get

| Capability | How |
|------------|-----|
| 📄 **Curated corpus** | `papers.yaml` is the source of truth — one structured entry per paper |
| ✅ **Auto-validation** | `scripts/validate_papers.py` checks schema, duplicates, URL normalization, LaTeX artifacts |
| 🧾 **Auto-generated README** | `scripts/generate_readme.py` renders the paper list grouped by your taxonomy |
| 📊 **Statistics & trends** | `scripts/standard_stats.py` → `statistics.json` (momentum, gaps, bursts, venues, authors) |
| 🔍 **Literature review report** | `scripts/analysis/generate_reports.py` → `docs/research/literature_review.md` + `trends.md` |
| 🧭 **Topic planning** | `tools/topic_planner.py`, `tools/trend_scanner.py`, `tools/landscape_analyzer.py`, `tools/brief_generator.py` |
| 🔎 **New paper discovery** | `scripts/fetch/fetch_new_papers.py` (arXiv), `fetch_other_sources.py` (dblp/crossref/europepmc), `fetch_openalex_bulk.py` |
| 🐙 **GitHub repos discovery** | `scripts/fetch/fetch_github_repos.py` (optional, config-driven via `github_queries` in taxonomy.yaml) |
| 🦊 **GitLab projects discovery** | `scripts/fetch/fetch_gitlab_repos.py` (optional, config-driven via `gitlab_queries` in taxonomy.yaml) |
| 🏠 **Codeberg repos discovery** | `scripts/fetch/fetch_codeberg_repos.py` (optional, config-driven via `codeberg_queries` in taxonomy.yaml) |
| 🖥️ **GitHub Pages site** | `docs/index.html` — searchable, filterable paper browser |
| 🤖 **Agentic workflow** | `AGENTS.md` + `config/taxonomy.yaml` make this repo agent-friendly by design |

## 🚀 Quick Start

```bash
# Validate + generate all outputs
python3 scripts/validate_papers.py && python3 scripts/generate_readme.py && python3 scripts/standard_stats.py && python3 scripts/analysis/generate_reports.py

# Discover new papers from arXiv
python3 scripts/fetch/fetch_new_papers.py --months 12 --dry-run   # preview
python3 scripts/fetch/fetch_new_papers.py --local                 # append to papers.yaml

# Explore the corpus
python3 tools/trend_scanner.py --months 12
python3 tools/landscape_analyzer.py
python3 tools/topic_planner.py --top 10
```

## 📖 How it works

```
config/taxonomy.yaml ──► papers.yaml ──► validate_papers.py
                          │   ▲              │
                          ▼   └── fetch_* ───┘
                   generate_readme.py ──► README.md (auto)
                          │
                          ▼
                  standard_stats.py ──► statistics.json, docs/papers.json
                          │
                          ▼
              analysis/generate_reports.py ──► docs/research/*.md
```

- **Never edit README.md directly** — it is generated from `papers.yaml`.
- The **taxonomy lives in one place** (`config/taxonomy.yaml`); every script reads it via `scripts/research_config.py`.
- **CI (validate.yml)** runs on every push/PR and weekly to discover new papers.

## 🧪 Local pipeline (all in one)

```bash
# Full pipeline (validate → README → stats → reports)
python3 scripts/validate_papers.py && python3 scripts/generate_readme.py && python3 scripts/standard_stats.py && python3 scripts/analysis/generate_reports.py
```

## 🤖 Agentic workflow (AGENTS.md)

This repo is designed to be driven by coding agents (OpenCode, Claude Code, …):

- **Spec-style guardrails** in `AGENTS.md` — agents know the pipeline, never edit README, always re-validate.
- **One config file** to change → one re-run to verify (low context cost for agents).
- **Auto-validation** gives agents an objective pass/fail signal.
- **Weekly discovery** keeps the corpus fresh without human babysitting.

## 📚 Paper list

- [📚 Inference & Posterior Estimation](#inference-&-posterior-estimation)
  - [Method](#method)
  - [Theory](#theory)
  - [Application](#application)
  - [Evaluation](#evaluation)
  - [Development](#development)
  - [Systems](#systems)
- [📚 Computational Methods](#computational-methods)
  - [Method](#method)
  - [Theory](#theory)
  - [Application](#application)
  - [Development](#development)
- [📚 Prior Specification & Elicitation](#prior-specification-&-elicitation)
  - [Method](#method)
  - [Theory](#theory)
- [📚 Model Selection & Averaging](#model-selection-&-averaging)
  - [Method](#method)
  - [Theory](#theory)
  - [Application](#application)
  - [Evaluation](#evaluation)
- [📚 Hierarchical & Multilevel Models](#hierarchical-&-multilevel-models)
  - [Method](#method)
  - [Theory](#theory)
  - [Application](#application)
  - [Development](#development)
  - [Systems](#systems)
  - [Survey](#survey)
- [📚 Bayesian Nonparametrics](#bayesian-nonparametrics)
  - [Method](#method)
  - [Theory](#theory)
- [📚 Bayesian Deep Learning](#bayesian-deep-learning)
  - [Method](#method)
  - [Theory](#theory)
  - [Survey](#survey)
- [📚 Applications](#applications)
  - [Method](#method)
  - [Theory](#theory)
- [📚 Surveys & Tutorials](#surveys-&-tutorials)

### Inference & Posterior Estimation

#### Method

##### 2026

- [2026] **Recursive Gaussian Processes and the Bayesian Brain** [[paper](https://arxiv.org/abs/2608.00503)]
- [2026] **Private Generative Bootstrap via Blocking** [[paper](https://arxiv.org/abs/2608.02480)]
- [2026] **Calibrated Bayesian Inference for Stochastic Intervention Effects** [[paper](https://arxiv.org/abs/2608.02924)]
- [2026] **Bootstrap validity in Bayesian semi-parametric models** [[paper](https://arxiv.org/abs/2608.06670)]
- [2026] **Algorithm-Driven SVARs: Navigating the Wilderness of Big Data** [[paper](https://arxiv.org/abs/2608.05017)]
- [2026] **A space of inference spaces in the space sciences - Parametric Bayesian inference in astronomy, cosmology and particle physics** [[paper](https://arxiv.org/abs/2608.06078)]
- [2026] **Bayesian Inference in Machine Interference Model** *British Journal of Contemporary Research* [[paper](https://doi.org/10.67693/bjcr-bjv4kta4)]
- [2026] **Identifying Informative Environments for Cognition Parameter Inference via Bayesian Experimental Design** [[paper](https://arxiv.org/abs/2607.28894)]
- [2026] **Generalised Robust Bayes for Joint Inference of Model and Contamination** [[paper](https://arxiv.org/abs/2607.25665)]
- [2026] **Full Bayesian Reinforcement Learning via LF-IBIS** [[paper](https://arxiv.org/abs/2607.01741)]
- [2026] **Deep Adaptive Bayesian Screening** [[paper](https://arxiv.org/abs/2607.16927)]
- [2026] **Bayesian Wind Tunnels for Model Selection** [[paper](https://arxiv.org/abs/2607.19379)]
- [2026] **Backward Bayesian Outcome Weighted Learning** [[paper](https://arxiv.org/abs/2608.00317)]
- [2026] **Amortized Bayesian Causal Discovery of Extended Factor Graphs** [[paper](https://arxiv.org/abs/2607.22934)]
- [2026] **Adaptive Bayesian Online Learning via Expert Aggregation** [[paper](https://arxiv.org/abs/2607.20239)]
- [2026] **AIM: Amortized Inference for Multistate Transition Models** [[paper](https://arxiv.org/abs/2607.23294)]
- [2026] **A Bayesian Framework for Built-in Input Dimension Reduction for Gaussian Process Modeling** [[paper](https://arxiv.org/abs/2607.19498)]
- [2026] **A Bayesian Approach and Vecchia Grouping for Estimating Spatial Covariances in Large Datasets** *Environmetrics* [[paper](https://doi.org/10.1002/env.70114)]
- [2026] **ABC-RF-rejection: A two-stage machine-learning-enhanced framework for efficient likelihood-free inference** *Epidemics* [[paper](https://doi.org/10.1016/j.epidem.2026.100931)]
- [2026] **An Introduction to Bayesian and Frequentist Simulation-Based Inference with Machine Learning** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2607.21702)]
- [2026] **Supplementary material from "Simulation-based inference of epidemiological and phylodynamic models via neural posterior estimation"** *Figshare* [[paper](https://doi.org/10.6084/m9.figshare.c.8625457.v1)]
- [2026] **Generative Bayesian Filtering for State Estimation** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2607.20521)]
- [2026] **Universal EOS-Radius Inverse Mappings Govern Precision-Dependent Inference of the Neutron Star Equation of State** [[paper](https://arxiv.org/abs/2606.28183)]
- [2026] **Ribbon: Scalable Approximation and Robust Uncertainty Quantification** [[paper](https://arxiv.org/abs/2606.27269)]
- [2026] **Population-Aware Physics-Informed Neural Particle Flow for Robust Spacecraft Bayesian Navigation** [[paper](https://arxiv.org/abs/2606.10959)]
- [2026] **Nonlocal Bayesian Modeling of Continuous Spatio-Temporal Dynamics** [[paper](https://arxiv.org/abs/2606.14313)]
- [2026] **Neural Posterior Estimation for Stochastic Epidemic Models Using Final Outcome Data** [[paper](https://arxiv.org/abs/2606.02874)]
- [2026] **Learning rate selection via weighted Fisher divergence** [[paper](https://arxiv.org/abs/2606.26478)]
- [2026] **In-Context Learning for Latent Space Bayesian Optimization** [[paper](https://arxiv.org/abs/2606.09664)]
- [2026] **Flow-based generative models for amortized Bayesian inference in regression and inverse PDE problems** [[paper](https://arxiv.org/abs/2606.10370)]
- [2026] **Consistency of variational approximations under bounded Kullback--Leibler divergence** [[paper](https://arxiv.org/abs/2606.13230)]
- [2026] **Bayesian model selection of vine copulas: a loss-based perspective** [[paper](https://arxiv.org/abs/2606.21512)]
- [2026] **Bayesian Model Averaging under Predictor Redundancy via Density-Ratio Posterior Compression** [[paper](https://arxiv.org/abs/2606.21080)]
- [2026] **Neural posterior estimation for stochastic epidemic modeling** *The Annals of Applied Statistics* [[paper](https://arxiv.org/abs/2412.12967)]
- [2026] **posterior: Tools for Working with Posterior Distributions in R** *The Journal of Open Source Software* [[paper](https://doi.org/10.21105/joss.10526)]
- [2026] **Simulation-based inference for rapid Bayesian parameter estimation in epidemiological models: a comparison with MCMC** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2606.27286)]
- [2026] **Wasserstein Contraction of Coordinate Ascent Variational Inference** [[paper](https://arxiv.org/abs/2605.30253)]
- [2026] **The Bayesian Reflex: Online Learning as the Autonomic Nervous System of Modern and Future AI** [[paper](https://arxiv.org/abs/2605.02825)]
- [2026] **Sequential Bayesian inference with correlated heavy-ion datasets** [[paper](https://arxiv.org/abs/2605.17868)]
- [2026] **Self-Supervised Laplace Approximation for Bayesian Uncertainty Quantification** *TMLR* [[paper](https://arxiv.org/abs/2605.12208)]
- [2026] **Sample Complexity and Decision-Theoretic Guarantees for Bayesian Model Averaging over Decision Trees with Catalan-Exponential Priors** [[paper](https://arxiv.org/abs/2606.01340)]
- [2026] **Rashomon-Seeded Annealing for Robust Bayesian Inference in Factorial Designs** [[paper](https://arxiv.org/abs/2606.02589)]
- [2026] **Pre-trained Tabular Foundation Models as Versatile Summary Networks for Neural Posterior Estimation** [[paper](https://arxiv.org/abs/2605.07765)]
- [2026] **Posterior Contraction Rates for Sparse Kolmogorov-Arnold Networks in Anisotropic Besov Spaces** [[paper](https://arxiv.org/abs/2605.11652)]
- [2026] **Position: agentic AI orchestration should be Bayes-consistent** *ICML 2026* [[paper](https://arxiv.org/abs/2605.00742)]
- [2026] **Online Bayesian Calibration under Gradual and Abrupt System Changes** [[paper](https://arxiv.org/abs/2605.06612)]
- [2026] **Offline Policy Optimization with Posterior Sampling** [[paper](https://arxiv.org/abs/2605.07393)]
- [2026] **Neural Posterior Estimation for Spatial Individual-Level Epidemic Models** [[paper](https://arxiv.org/abs/2605.29180)]
- [2026] **Multi-Teacher Knowledge Distillation via Teacher-Informed Mixture Priors** [[paper](https://arxiv.org/abs/2605.27967)]
- [2026] **Memory by Design: Probabilistic Sequence Layers** [[paper](https://arxiv.org/abs/2605.31163)]
- [2026] **Joint Model and Data Sparsification via the Marginal Likelihood** *ICML 2026* [[paper](https://arxiv.org/abs/2605.29908)]
- [2026] **Integrating Bayesian Spectral Deconvolution and Expert Scientific Reasoning for Robust Peak Estimation** [[paper](https://arxiv.org/abs/2605.17518)]
- [2026] **Functional-prior-based approaches to Bayesian PDE-constrained inversion using physics-informed neural networks** [[paper](https://arxiv.org/abs/2605.07060)]
- [2026] **Energy-based Transport for Amortized Bayesian Inference** [[paper](https://arxiv.org/abs/2605.15407)]
- [2026] **Deep Adaptive Dimension Reduction for Bayesian Inference in Inverse Problems** [[paper](https://arxiv.org/abs/2605.29373)]
- [2026] **Data-informed posterior approximation for Bayesian linear inverse problems** [[paper](https://arxiv.org/abs/2605.20770)]
- [2026] **Corrected Integrated Laplace Approximation for Bayesian Inference in Latent Gaussian Models** [[paper](https://arxiv.org/abs/2605.20345)]
- [2026] **Concentration and Calibration in Predictive Bayesian Inference** [[paper](https://arxiv.org/abs/2605.00455)]
- [2026] **Bayesian inference with sources of uncertainty: from confidence modelling to sparse estimation** [[paper](https://arxiv.org/abs/2605.03134)]
- [2026] **Bayesian Latent Space Models for Graphs Are Misspecified: Toward Robust Inference via Generalized Posteriors** [[paper](https://arxiv.org/abs/2605.18927)]
- [2026] **A Stable Distance Persistence Homology for Dynamic Bayesian Network Clustering** [[paper](https://arxiv.org/abs/2605.11226)]
- [2026] **Posterior distribution estimation of parameters related to unsaturated soil hydraulic properties by combining parameterized physics-informed neural networks and Bayesian inference** *Computers and Geotechnics* [[paper](https://doi.org/10.1016/j.compgeo.2026.108298)]
- [2026] **Residual neural likelihood estimation and its application to gravitational-wave astronomy** *Physical review. D/Physical review. D.* [[paper](https://doi.org/10.1103/f5df-cxyg)]
- [2026] **Bridging Markov Chain Monte Carlo Techniques and Tierney–Kadane Approximations for Progressively Censored Garhy Reliability Models: Simulation Insights and a Medical Application** *Mathematics* [[paper](https://doi.org/10.3390/math14101777)]
- [2026] **Neural Posterior Estimation for UHECR source inference from 3D propagation simulations** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2605.01004)]
- [2026] **Variable selection and inference with a new robust Bayesian elastic net** *Figshare* [[paper](https://doi.org/10.6084/m9.figshare.32149876)]
- [2026] **Using Statistical Mechanics to Improve Real-World Bayesian Inference: A New Method Combining Tempered Posteriors and Wang-Landau Sampling** [[paper](https://arxiv.org/abs/2604.23527)]
- [2026] **Scalable Variational Bayesian Fine-Tuning of LLMs via Orthogonalized Low-Rank Adapters** [[paper](https://arxiv.org/abs/2604.03388)]
- [2026] **On Bayesian Softmax-Gated Mixture-of-Experts Models** [[paper](https://arxiv.org/abs/2604.20551)]
- [2026] **Monte Carlo Stochastic Depth for Uncertainty Estimation in Deep Learning** [[paper](https://arxiv.org/abs/2604.12719)]
- [2026] **Laplace Approximation for Bayesian Tensor Network Kernel Machines** [[paper](https://arxiv.org/abs/2604.26673)]
- [2026] **Efficient Bayesian Inference in the Cox Model via Rank-Ordered Likelihood** [[paper](https://arxiv.org/abs/2604.06034)]
- [2026] **Distill-Belief: Closed-Loop Inverse Source Localization and Characterization in Physical Fields** [[paper](https://arxiv.org/abs/2604.26095)]
- [2026] **Conformal prediction for uncertainties in the neutron star equation of state** [[paper](https://arxiv.org/abs/2604.21039)]
- [2026] **Bayesian inference for hidden Markov models under genuine multimodality with application to ecological time series** [[paper](https://arxiv.org/abs/2604.24587)]
- [2026] **Bayesian Optimization in Linear Time** [[paper](https://arxiv.org/abs/2605.00237)]
- [2026] **Bayesian Inference for Estimating Generation Costs in Electricity Markets** [[paper](https://arxiv.org/abs/2604.08309)]
- [2026] **Adaptive Meta-Learning Stochastic Gradient Hamiltonian Monte Carlo Simulation for Bayesian Updating of Structural Dynamic Models** [[paper](https://arxiv.org/abs/2604.25710)]
- [2026] **A Tensor-Train Framework for Bayesian Inference in High-Dimensional Systems: Applications to MIMO Detection and Channel Decoding** [[paper](https://arxiv.org/abs/2604.05890)]
- [2026] **A Bayesian Updating Framework for Long-term Multi-Environment Trial Data in Plant Breeding** [[paper](https://arxiv.org/abs/2604.16203)]
- [2026] **A Bayesian Perspective on the Role of Epistemic Uncertainty for Delayed Generalization in In-Context Learning** [[paper](https://arxiv.org/abs/2604.12434)]
- [2026] **Neural posterior estimation for population genetics** *Genetics* [[paper](https://doi.org/10.1093/genetics/iyag107)]
- [2026] **Emulator-accelerated Bayesian framework for nonlinear parameter estimation of entry capsule dynamic stability** *Aerospace Science and Technology* [[paper](https://doi.org/10.1016/j.ast.2026.112342)]
- [2026] **DAE-Aware Bayesian Inference for Joint Generator-Network Parameter Estimation** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2604.15686)]
- [2026] **Multidimensional Quantum Estimation and Model Learning Framework Based on Variational Bayesian Inference** *PRX Quantum* [[paper](https://arxiv.org/abs/2507.23130)]
- [2026] **Simulation-based inference with neural posterior estimation applied to X-ray spectral fitting** *SHILAP Revista de lepidopterología* [[paper](https://doaj.org/article/e732128952e3490fae382d6134aa5b5b)]
- [2026] **Likelihood-free parameter inference for spatiotemporal stochastic biological models using neural posterior estimation** *Journal of Theoretical Biology* [[paper](https://doi.org/10.1016/j.jtbi.2026.112475)]
- [2026] **Overcoming Selection Bias in Statistical Studies With Amortized Bayesian Inference** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2604.18319)]
- [2026] **mlr3mbo: Bayesian Optimization in R** [[paper](https://arxiv.org/abs/2603.29730)]
- [2026] **Variational Routing: A Scalable Bayesian Framework for Calibrated Mixture-of-Experts Transformers** [[paper](https://arxiv.org/abs/2603.09453)]
- [2026] **Transfer Learning in Bayesian Optimization for Aircraft Design** [[paper](https://arxiv.org/abs/2603.28999)]
- [2026] **Time-Aware Latent Space Bayesian Optimization** [[paper](https://arxiv.org/abs/2603.00935)]
- [2026] **PyINLA: Fast Bayesian Inference for Latent Gaussian Models in Python** [[paper](https://arxiv.org/abs/2603.27276)]
- [2026] **Probabilistic Learning and Generation in Deep Sequence Models** [[paper](https://arxiv.org/abs/2603.00888)]
- [2026] **Overfitting and Generalizing with (PAC) Bayesian Prediction in Noisy Binary Classification** [[paper](https://arxiv.org/abs/2603.22644)]
- [2026] **Generalized Bayes for Causal Inference** [[paper](https://arxiv.org/abs/2603.03035)]
- [2026] **Early Prediction of Creep Failure via Bayesian Inference of Evolving Barriers** [[paper](https://arxiv.org/abs/2603.16419)]
- [2026] **Direct Bayesian Additive Regression Trees for Conditional Average Treatment Effects in Regression Discontinuity Designs** [[paper](https://arxiv.org/abs/2603.03819)]
- [2026] **Bayesian Scattering: A Principled Baseline for Uncertainty on Image Data** [[paper](https://arxiv.org/abs/2603.20908)]
- [2026] **Bayesian Additive Distribution Regression** [[paper](https://arxiv.org/abs/2603.06462)]
- [2026] **Approximate posterior recalibration** [[paper](https://arxiv.org/abs/2603.20068)]
- [2026] **ALABI: Active Learning for Accelerated Bayesian Inference** [[paper](https://arxiv.org/abs/2603.18259)]
- [2026] **A Fast Generative Framework for High-dimensional Posterior Sampling: Application to CMB Delensing** [[paper](https://arxiv.org/abs/2603.04535)]
- [2026] **A Bayesian inferencing framework for ultrasound wave speed measurements in metal additive manufacturing** *Measurement* [[paper](https://doi.org/10.1016/j.measurement.2026.121216)]
- [2026] **Bayesian inference of RNA velocity incorporating timepoints, lineage bifurcations, and count data** *PLoS Computational Biology* [[paper](https://doi.org/10.1371/journal.pcbi.1014060)]
- [2026] **GeoBayes: Probabilistic Image Geo-Localization Inference via Sequential Bayesian Updating** *Proceedings of the AAAI Conference on Artificial Intelligence* [[paper](https://doi.org/10.1609/aaai.v40i11.37855)]
- [2026] **Identification of Strongly Lensed Gravitational-wave Events Using Squeeze-and-excitation Multilayer Perceptron Data-efficient Image Transformer** *The Astrophysical Journal Supplement Series* [[paper](https://arxiv.org/abs/2508.19311)]
- [2026] **Circuit Modeling for <i>In Situ</i> 21 cm Radiometer Calibration** *Journal of Astronomical Instrumentation* [[paper](https://doi.org/10.1142/s2251171726500029)]
- [2026] **Defocus deconvolution signal restoration based on Bayesian inference** [[paper](https://doi.org/10.1117/12.3094494)]
- [2026] **Bayesian inference for integrated pharmacokinetic modelling of mitragynine and 7-hydroxymitragynine** *ADMET & DMPK* [[paper](https://doi.org/10.5599/admet.3170)]
- [2026] **Universal priors: solving empirical Bayes via Bayesian inference and pretraining** [[paper](https://arxiv.org/abs/2602.15136)]
- [2026] **Sparse Bayesian Deep Functional Learning with Structured Region Selection** [[paper](https://arxiv.org/abs/2602.20651)]
- [2026] **Proximal-IMH: Proximal Posterior Proposals for Independent Metropolis-Hastings with Approximate Operators** [[paper](https://arxiv.org/abs/2602.21426)]
- [2026] **Pragmatic Curiosity: A Unified Framework for Hybrid Learning and Optimization via Active Inference** [[paper](https://arxiv.org/abs/2602.06104)]
- [2026] **On the Equivalence of Random Network Distillation, Deep Ensembles, and Bayesian Inference** [[paper](https://arxiv.org/abs/2602.19964)]
- [2026] **MDP Planning as Policy Inference** [[paper](https://arxiv.org/abs/2602.17375)]
- [2026] **Extending Multi-Source Bayesian Optimization With Causality Principles** [[paper](https://arxiv.org/abs/2602.14791)]
- [2026] **Conditional neural control variates for variance reduction in Bayesian inverse problems** [[paper](https://arxiv.org/abs/2602.21357)]
- [2026] **Bayesian Quadrature: Gaussian Processes for Integration** [[paper](https://arxiv.org/abs/2602.16218)]
- [2026] **Bayesian Generative Adversarial Networks via Gaussian Approximation for Tabular Data Synthesis** [[paper](https://arxiv.org/abs/2602.21948)]
- [2026] **BayesFlow 2: Multi-Backend Amortized Bayesian Inference in Python** [[paper](https://arxiv.org/abs/2602.07098)]
- [2026] **BFTS: Thompson Sampling with Bayesian Additive Regression Trees** [[paper](https://arxiv.org/abs/2602.07767)]
- [2026] **Amortising Inference and Meta-Learning Priors in Neural Networks** *ICLR 2026* [[paper](https://arxiv.org/abs/2602.08782)]
- [2026] **Comparing next-generation detector configurations for high-redshift gravitational wave sources with neural posterior estimation** *Astronomy and Astrophysics* [[paper](https://arxiv.org/abs/2512.20699)]
- [2026] **Variational Inference for Bayesian MIDAS Regression** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2602.19610)]
- [2026] **R-package Jsmm: Joint species movement modelling of mark-recapture data** *bioRxiv (Cold Spring Harbor Laboratory)* [[paper](https://doi.org/10.64898/2026.02.24.707702)]
- [2026] **Robust Bayesian Inference via Variational Approximations of Generalized Rho-Posteriors** [[paper](https://arxiv.org/abs/2601.07325)]
- [2026] **Propagating Surrogate Uncertainty in Bayesian Inverse Problems** [[paper](https://arxiv.org/abs/2601.03532)]
- [2026] **Neural Architectures for Amortized Bayesian Inference: Statistical Foundations and Empirical Assessments** [[paper](https://arxiv.org/abs/2601.07944)]
- [2026] **Investigating Batch Inference in a Sequential Monte Carlo Framework for Neural Networks** [[paper](https://arxiv.org/abs/2601.21983)]
- [2026] **Gradient-free ensemble transform methods for generalized Bayesian inference in generative models** [[paper](https://arxiv.org/abs/2601.00760)]
- [2026] **From Mice to Trains: Amortized Bayesian Inference on Graph Data** [[paper](https://arxiv.org/abs/2601.02241)]
- [2026] **Distribution-Matching Posterior Inference for Incomplete Structural Models** [[paper](https://arxiv.org/abs/2601.01077)]
- [2026] **Bayesian Inference for Discrete Markov Random Fields Through Coordinate Rescaling** [[paper](https://arxiv.org/abs/2601.17205)]
- [2026] **Bayesian Additive Regression Tree Copula Processes for Scalable Distributional Prediction** [[paper](https://arxiv.org/abs/2601.04913)]
- [2026] **An Empirical Study on Ensemble-Based Transfer Learning Bayesian Optimisation with Mixed Variable Types** [[paper](https://arxiv.org/abs/2601.15640)]
- [2026] **An AI-powered Bayesian Generative Modeling Approach for Arbitrary Conditional Inference** [[paper](https://arxiv.org/abs/2601.05355)] [[code](https://github.com/liuq-lab/bayesgm)]
- [2026] **Amortized Simulation-Based Inference in Generalized Bayes via Neural Posterior Estimation** *ICML 2026* [[paper](https://arxiv.org/abs/2601.22367)]
- [2026] **Adaptive Conformal Prediction via Bayesian Uncertainty Weighting for Hierarchical Healthcare Data** [[paper](https://arxiv.org/abs/2601.01223)]
- [2026] **A statistical framework for quantitative spectroscopy of luminous blue stars** [[paper](https://arxiv.org/abs/2601.01491)]

##### 2025

- [2025] **The Bayesian Geometry of Transformer Attention** [[paper](https://arxiv.org/abs/2512.22471)]
- [2025] **Tempering the Bayes Filter towards Improved Model-Based Estimation** [[paper](https://arxiv.org/abs/2512.02823)]
- [2025] **Generative Bayesian Hyperparameter Tuning** [[paper](https://arxiv.org/abs/2512.20051)]
- [2025] **Fully Bayesian Spectral Clustering and Benchmarking with Uncertainty Quantification for Small Area Estimation** [[paper](https://arxiv.org/abs/2512.15643)]
- [2025] **Efficient Bayesian inference for two-stage models in environmental epidemiology** [[paper](https://arxiv.org/abs/2512.18143)]
- [2025] **Debiased Bayesian Inference for High-dimensional Regression Models** [[paper](https://arxiv.org/abs/2512.09257)]
- [2025] **Characterizing Finite-Dimensional Posterior Marginals in High-Dimensional GLMs via Leave-One-Out** [[paper](https://arxiv.org/abs/2601.00091)]
- [2025] **Bayesian Semiparametric Mixture Cure (Frailty) Models** [[paper](https://arxiv.org/abs/2512.08173)]
- [2025] **\texttt{unimpeded}: A Public Nested Sampling Database for Bayesian Cosmology** [[paper](https://arxiv.org/abs/2511.05470)]
- [2025] **SmallML: Bayesian Transfer Learning for Small-Data Predictive Analytics** [[paper](https://arxiv.org/abs/2511.14049)]
- [2025] **Robust Experimental Design via Generalised Bayesian Inference** [[paper](https://arxiv.org/abs/2511.07671)]
- [2025] **Pixellated Posterior Sampling of Point Spread Functions in Astronomical Images** [[paper](https://arxiv.org/abs/2511.19594)]
- [2025] **Partial Trace-Class Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2511.01628)]
- [2025] **Optimizing Algorithms for Mobile Health Interventions with Active Querying Optimization** [[paper](https://arxiv.org/abs/2512.08950)]
- [2025] **Joint Bayesian Inference of Parameter and Discretization Error Uncertainties in ODE Models** [[paper](https://arxiv.org/abs/2511.23010)]
- [2025] **Identification-aware Markov chain Monte Carlo** [[paper](https://arxiv.org/abs/2511.12847)]
- [2025] **Generative Bayesian Filtering and Parameter Learning** [[paper](https://arxiv.org/abs/2511.04552)]
- [2025] **Fast Riemannian-manifold Hamiltonian Monte Carlo for hierarchical Gaussian-process models** [[paper](https://arxiv.org/abs/2511.06407)]
- [2025] **Conservative Software Reliability Assessments Using Collections of Bayesian Inference Problems** [[paper](https://arxiv.org/abs/2511.07038)]
- [2025] **Conjugate Generalized Bayesian Inference for Discrete Doubly Intractable Problems** [[paper](https://arxiv.org/abs/2511.23275)]
- [2025] **Conformalized Bayesian Inference, with Applications to Random Partition Models** [[paper](https://arxiv.org/abs/2511.05746)]
- [2025] **Bridging Theory and Practice: A Stochastic Learning-Optimization Model for Resilient Automotive Supply Chains** [[paper](https://arxiv.org/abs/2511.06479)]
- [2025] **Bernstein-von Mises for Adaptively Collected Data** [[paper](https://arxiv.org/abs/2511.06639)]
- [2025] **Bayesian--AI Fusion for Epidemiological Decision Making: Calibrated Risk, Honest Uncertainty, and Hyperparameter Intelligence** [[paper](https://arxiv.org/abs/2511.11983)]
- [2025] **Bayesian dynamic scheduling of multipurpose batch processes under incomplete look-ahead information** [[paper](https://arxiv.org/abs/2512.01093)]
- [2025] **Bayesian constraint of the initial condition for the Balitsky-Kovchegov equation at NLO** [[paper](https://arxiv.org/abs/2511.01394)]
- [2025] **Bayesian Semiparametric Causal Inference: Targeted Doubly Robust Estimation of Treatment Effects** [[paper](https://arxiv.org/abs/2511.15904)]
- [2025] **Bayesian Optimization for Function-Valued Responses under Min-Max Criteria** [[paper](https://arxiv.org/abs/2512.07868)]
- [2025] **Approximate Bayesian inference for cumulative probit regression models** [[paper](https://arxiv.org/abs/2511.06967)]
- [2025] **Addressing prior dependence in hierarchical Bayesian modeling for PTA data analysis I: Methodology and implementation** [[paper](https://arxiv.org/abs/2511.03667)]
- [2025] **A Fully Probabilistic Tensor Network for Regularized Volterra System Identification** [[paper](https://arxiv.org/abs/2511.20457)]
- [2025] **metabeta -- A fast neural model for Bayesian mixed-effects regression** [[paper](https://arxiv.org/abs/2510.07473)]
- [2025] **Stick-Breaking Mixture Normalizing Flows with Component-Wise Tail Adaptation for Variational Inference** [[paper](https://arxiv.org/abs/2510.07965)]
- [2025] **PriorGuide: Test-Time Prior Adaptation for Simulation-Based Inference** *ICLR 2026. Camera-ready version. 38 pages* [[paper](https://arxiv.org/abs/2510.13763)]
- [2025] **Out-of-Distribution Detection from Small Training Sets using Bayesian Neural Network Classifiers** [[paper](https://arxiv.org/abs/2510.06025)]
- [2025] **Online and Interactive Bayesian Inference Debugging** [[paper](https://arxiv.org/abs/2510.26579)]
- [2025] **Integrating Bayesian methods with neural network--based model predictive control: a review** [[paper](https://arxiv.org/abs/2510.05338)]
- [2025] **From Observations to Parameters: Detecting Changepoint in Nonlinear Dynamics with Simulation-based Inference** [[paper](https://arxiv.org/abs/2510.17933)]
- [2025] **Calibrating Bayesian Inference** [[paper](https://arxiv.org/abs/2510.27144)]
- [2025] **Bayesian neural networks with interpretable priors from Mercer kernels** [[paper](https://arxiv.org/abs/2510.23745)]
- [2025] **Bayesian model selection and misspecification testing in imaging inverse problems only from noisy and partial measurements** [[paper](https://arxiv.org/abs/2510.27663)]
- [2025] **Bayesian inference calibration of the modulus of elasticity** [[paper](https://arxiv.org/abs/2510.27060)]
- [2025] **Bayesian Nonlinear PDE Inference via Gaussian Process Collocation with Application to the Richards Equation** [[paper](https://arxiv.org/abs/2510.23550)]
- [2025] **Bayesian Neural Networks for Functional ANOVA model** [[paper](https://arxiv.org/abs/2510.00545)]
- [2025] **Bayesian Adaptive Polynomial Chaos Expansions** [[paper](https://arxiv.org/abs/2510.25036)]
- [2025] **Batch Bayesian Active Learning with Partial Batch Label Sampling** [[paper](https://arxiv.org/abs/2510.09877)] [[code](https://github.com/ADDAPT-ML/ParBaLS)]
- [2025] **Variational Uncertainty Decomposition for In-Context Learning** [[paper](https://arxiv.org/abs/2509.02327)]
- [2025] **Tractable Approximation of Labeled Multi-Object Posterior Densities** [[paper](https://arxiv.org/abs/2509.18780)]
- [2025] **Quantile-Scaled Bayesian Optimization Using Rank-Only Feedback** [[paper](https://arxiv.org/abs/2510.03277)]
- [2025] **Optimization-centric cutting feedback for semiparametric models** [[paper](https://arxiv.org/abs/2509.18708)]
- [2025] **On Quantification of Borrowing of Information in Hierarchical Bayesian Models** [[paper](https://arxiv.org/abs/2509.17301)]
- [2025] **Learning Informed Prior Distributions with Normalizing Flows for Bayesian Analysis** [[paper](https://arxiv.org/abs/2509.14911)]
- [2025] **Global Optimization of Stochastic Black-Box Functions with Arbitrary Noise Distributions using Wilson Score Kernel Density Estimation** [[paper](https://arxiv.org/abs/2509.09238)]
- [2025] **Geometric Autoencoder Priors for Bayesian Inversion: Learn First Observe Later** [[paper](https://arxiv.org/abs/2509.19929)]
- [2025] **Bouncy particle sampler with infinite exchanging parallel tempering** [[paper](https://arxiv.org/abs/2509.02003)]
- [2025] **BioBO: Biology-informed Bayesian Optimization for Perturbation Design** [[paper](https://arxiv.org/abs/2509.19988)]
- [2025] **Bayesian Semi-supervised Inference via a Debiased Modeling Approach** [[paper](https://arxiv.org/abs/2509.17385)]
- [2025] **Bayesian Additive Regression Trees for functional ANOVA model** [[paper](https://arxiv.org/abs/2509.03317)]
- [2025] **Outlier-Robust Bayesian Multivariate Analysis with Correlation-Intact Sandwich Mixture** [[paper](https://arxiv.org/abs/2508.18004)]
- [2025] **FBMS: An R Package for Flexible Bayesian Model Selection and Model Averaging** [[paper](https://arxiv.org/abs/2509.00753)]

[⬆ Back to top](#paper-list)

#### Theory

##### 2026

- [2026] **Verifiable Regularity Criterion for Conditional Expectation Operators and Conditional Mean Embeddings with Applications to Nonparametric Regression, Bayesian Inverse Problems, and Koopman Operators** [[paper](https://arxiv.org/abs/2608.06155)]
- [2026] **Induction and the rule of succession through a possibilistic inferential model lens** [[paper](https://arxiv.org/abs/2608.11935)]
- [2026] **Supercharging simulation-based inference for Bayesian optimal experimental design** *Machine Learning Science and Technology* [[paper](https://arxiv.org/abs/2602.06900)]
- [2026] **Some cautionary tales about Bayesian predictive inference** [[paper](https://arxiv.org/abs/2607.19206)]
- [2026] **Operator-Split Bayesian Learning for Elliptic PDEs with Unequal Interior and Boundary Data** [[paper](https://arxiv.org/abs/2607.14680)]
- [2026] **On-Policy and Off-Policy Learning for Large Action Spaces** [[paper](https://arxiv.org/abs/2607.28408)]
- [2026] **Merging of Bayes and quasi-Bayes empirical Bayes procedures for Poisson compound decisions** [[paper](https://arxiv.org/abs/2607.02340)]
- [2026] **Coherent Measures of Discrepancy, Uncertainty and Dependence, with Applications to Bayesian Predictive Experimental Design** [[paper](https://arxiv.org/abs/2607.26077)]
- [2026] **An Efficient Bayesian Framework for Uncertainty Quantification in Nonlinear Imaging Inverse Problems** [[paper](https://arxiv.org/abs/2607.10817)]
- [2026] **3D Uncertainty Quantification for the Photo-Acoustic Tomography** [[paper](https://arxiv.org/abs/2607.21373)]
- [2026] **Wrench-Based Bayesian Pose Estimation via Matrix--Fisher Gaussian Inference** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2607.07306)]
- [2026] **Bayesian Inference for the Extreme Value Index** *Journal of Statistical Theory and Practice* [[paper](https://doi.org/10.1007/s42519-026-00614-y)]
- [2026] **Probabilistic estimation and uncertainty quantification of grid inertia using variational bayesian inference with ambient noise perturbations** *Global Energy Interconnection* [[paper](https://doi.org/10.1016/j.gloei.2026.06.005)]
- [2026] **Factorized neural posterior estimation for rapid and reliable inference of parameterized post-Einsteinian deviation parameters in gravitational waves** *Communications in Theoretical Physics* [[paper](https://doi.org/10.1088/1572-9494/ae8f1e)]
- [2026] **Predictive Concordance for Parameter Optimisation and Mixture Synthesis** [[paper](https://arxiv.org/abs/2606.14382)]
- [2026] **Multivariate Varying-Coefficient BART with Graphical Horseshoe Priors** [[paper](https://arxiv.org/abs/2606.29114)]
- [2026] **Higher-order spectral perturbation expansions II: Kernel matrices and manifold learning** [[paper](https://arxiv.org/abs/2606.16373)]
- [2026] **Ferguson's Dirichlet Process Breakthrough: A Lasting Legacy** [[paper](https://arxiv.org/abs/2606.24519)]
- [2026] **Bayesian Prediction in Gamma Models: Admissibility and Infinitesimal Prediction** [[paper](https://arxiv.org/abs/2606.18700)]
- [2026] **Bayesian Transfer Learning for Enhanced Estimation and Inference** *Journal of the American Statistical Association* [[paper](https://arxiv.org/abs/2412.02986)]
- [2026] **Inference for Stress–Strength Reliability Under Unified Hybrid Censoring: A One-Parameter Model with Applications** *Mathematics* [[paper](https://doi.org/10.3390/math14122041)]
- [2026] **Bayesian inference under intractable models and imperfect priors** *Rutgers University Community Repository (Rutgers University)* [[paper](https://www.proquest.com/LegacyDocView/DISSNUM/32445993)]
- [2026] **Bayesian Inference of Seizure-related Ionic Dysregulation in Cortical Tissue** *International Journal Bioautomation* [[paper](https://doi.org/10.7546/ijba.2026.30.2.1104)]
- [2026] **Computational adaptive optics for interferometric microscopy based on Bayesian inference** *Optics and Lasers in Engineering* [[paper](https://doi.org/10.1016/j.optlaseng.2026.109924)]
- [2026] **Robust ensemble Kalman filtering under observation noise misspecification via diffusion score matching** [[paper](https://arxiv.org/abs/2605.26881)]
- [2026] **Predictive Inference via Kernel Density Estimates** [[paper](https://arxiv.org/abs/2605.14008)]
- [2026] **Posterior Concentration of Bayesian Physics-Informed Neural Networks for Elliptic PDEs** [[paper](https://arxiv.org/abs/2605.08672)]
- [2026] **Entropic Strict Minimum Message Length and Its Connections to PAC-Bayes and NML** [[paper](https://arxiv.org/abs/2605.02099)]
- [2026] **Bayesian and Empirical Bayesian Bootstrapping** [[paper](https://arxiv.org/abs/2605.11677)]
- [2026] **Bayesian Inference with Shaped Deep Non-linear MLPs** [[paper](https://arxiv.org/abs/2605.30860)]
- [2026] **Bayesian Inference for Multivariate Monotone Densities** *Scandinavian Journal of Statistics* [[paper](https://arxiv.org/abs/2306.05202)]
- [2026] **Physics-informed neural particle flow for the Bayesian update step** *Knowledge-Based Systems* [[paper](https://doi.org/10.1016/j.knosys.2026.116209)]
- [2026] **Flow matching-guided adaptive Markov Chain Monte Carlo with deep generative proposals for Bayesian model updating in structural health monitoring** *Reliability Engineering & System Safety* [[paper](https://doi.org/10.1016/j.ress.2026.112917)]
- [2026] **Minimax Optimal High-Dimensional Nonparametric Inference: Bridging Bayesian Posteriors and Frequentist Risk Bounds** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.20402864)]
- [2026] **A Bayesian Inference Algorithm for Equipment Software Price Estimation Based on Nonlinear Contribution Models** *Algorithms* [[paper](https://doi.org/10.3390/a19050396)]
- [2026] **Bayesian Estimation for α-Mixture Survival Models** *Mathematics* [[paper](https://doi.org/10.3390/math14101772)]
- [2026] **Parametric Statistical Inference in the Zone of Moderate Deviation Probabilities** [[paper](https://arxiv.org/abs/2604.24736)]
- [2026] **Large-Sample Bayesian Approximations for Privatized Data** [[paper](https://arxiv.org/abs/2604.24817)]
- [2026] **Bayesian online learning in the one-pass regime: Frequentist validity and uncertainty quantification** [[paper](https://arxiv.org/abs/2604.27442)]
- [2026] **Bayesian Nonparametric Inference for “Species-Sampling” Problems** *Statistical Science* [[paper](https://doi.org/10.1214/24-sts961)]
- [2026] **Frequency-domain Bayesian inference for identifying high-dimensional nonlinear mechanical properties of heterogeneous materials** *Journal of the Mechanics and Physics of Solids* [[paper](https://doi.org/10.1016/j.jmps.2026.106625)]
- [2026] **Accelerated inference of microlensed gravitational waves with machine learning** *Physical review. D/Physical review. D.* [[paper](https://arxiv.org/abs/2511.08486)]
- [2026] **Variational inference for sparse poisson regression** *Computational Statistics* [[paper](https://arxiv.org/abs/2311.01147)]
- [2026] **Disentangling Aleatoric and Epistemic Uncertainty in Physics‐Informed Neural Networks: Application to Insulation Material Degradation Prognostics** *Advanced Intelligent Systems* [[paper](https://arxiv.org/abs/2601.03673)]
- [2026] **The relative value of interventional and observational samples in Bayesian Causal Linear Gaussian Models** [[paper](https://arxiv.org/abs/2603.26460)]
- [2026] **The Bernstein-von Mises theorem and efficiency for semiparametric inference in multivariate Hawkes processes** [[paper](https://arxiv.org/abs/2603.23655)]
- [2026] **Retraining as Approximate Bayesian Inference** [[paper](https://arxiv.org/abs/2603.25480)]
- [2026] **Continuity of the Solution of a Non-Parametric Bayesian Statistical Calibration Procedure** [[paper](https://arxiv.org/abs/2603.20665)]
- [2026] **Bayesian Modular Inference for Copula Models with Potentially Misspecified Marginals** [[paper](https://arxiv.org/abs/2603.11457)]
- [2026] **A Hierarchical Bayesian Dynamic Game for Competitive Inventory and Pricing under Incomplete Information: Learning, Credible Risk, and Equilibrium** [[paper](https://arxiv.org/abs/2603.06072)]
- [2026] **Bayesian Fourier neural operator for digital twin-based structural performance identification of PC girder bridges** *Engineering Structures* [[paper](https://doi.org/10.1016/j.engstruct.2026.122513)]
- [2026] **Inference on stress-strength reliability model under step-stress partially accelerated life testing based on the Lomax distribution** *Quality & Quantity* [[paper](https://doi.org/10.1007/s11135-026-02648-7)]
- [2026] **Theory of Epistemic Abductive Geometry (TEAG): A Unified Theory of Admissibility-Driven Inference Across Dynamical Systems, Measure Theory, and Language** *Preprints.org* [[paper](https://doi.org/10.20944/preprints202603.2010.v2)]
- [2026] **CIFLE: A physics-based machine learning framework with probabilistic inference for low-cycle fatigue life prediction** *Journal of Magnesium and Alloys* [[paper](https://doi.org/10.1016/j.jma.2026.102028)]
- [2026] **Bayesian posterior inference for sentiment analysis using Dirichlet-multinomial conjugate structure** *Journal of the Korean Data and Information Science Society* [[paper](https://doi.org/10.7465/jkdi.2026.37.2.355)]
- [2026] **Stochastic Optimal Control with Side Information and Bayesian Learning** [[paper](https://arxiv.org/abs/2602.22047)]
- [2026] **Semi-parametric Bayesian inference under Neyman orthogonality** [[paper](https://arxiv.org/abs/2602.20371)]
- [2026] **Robust Bayesian estimation in conditionally heteroscedastic time series models** [[paper](https://arxiv.org/abs/2602.06360)]
- [2026] **Piecewise Deterministic Markov Processes for Bayesian Inference of PDE Coefficients** [[paper](https://arxiv.org/abs/2602.05559)]
- [2026] **Minimax Simple Bayes Estimators of a Normal Variance** [[paper](https://arxiv.org/abs/2603.00553)]
- [2026] **Inhomogeneous Priors for Bayesian Inverse Problems** [[paper](https://arxiv.org/abs/2602.07856)]
- [2026] **Exchangeable random permutations with an application to Bayesian graph matching** [[paper](https://arxiv.org/abs/2602.01993)]
- [2026] **Dynamic Decision-Making under Model Misspecification: A Stochastic Stability Approach** [[paper](https://arxiv.org/abs/2602.17086)]
- [2026] **Compound decisions and empirical Bayes via Bayesian nonparametrics** [[paper](https://arxiv.org/abs/2602.20115)]
- [2026] **Bayesian Optimality of In-Context Learning with Selective State Spaces** [[paper](https://arxiv.org/abs/2602.17744)]
- [2026] **A closed form solution for Bayesian analysis of a simple linear mixed model** [[paper](https://arxiv.org/abs/2602.10730)]
- [2026] **A New Look at Bayesian Testing** [[paper](https://arxiv.org/abs/2602.11132)]
- [2026] **Robust Bayesian high-dimensional variable selection and inference with the horseshoe family of priors** *Computational Statistics & Data Analysis* [[paper](https://doi.org/10.1016/j.csda.2026.108358)]
- [2026] **Unsupervised Continual Learning for Amortized Bayesian Inference** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2602.22884)]
- [2026] **Measurement Uncertainty Estimation Using GUM, Monte Carlo Simulation, and Bayesian Inference** [[paper](https://doi.org/10.1109/iciptm69057.2026.11466046)]
- [2026] **Semi-parametric Bernstein-von Mises Theorem in a Parabolic PDE Problem** [[paper](https://arxiv.org/abs/2602.00889)]
- [2026] **Random tree Besov priors: Data-driven regularisation parameter selection** [[paper](https://arxiv.org/abs/2601.12957)]
- [2026] **Posterior concentration in spatio-temporal Hawkes processes** [[paper](https://arxiv.org/abs/2601.03719)]
- [2026] **Markov Stick-breaking Processes** [[paper](https://arxiv.org/abs/2601.16561)]
- [2026] **A new class of colored Gaussian graphical models with explicit normalizing constants** [[paper](https://arxiv.org/abs/2601.16945)]
- [2026] **A Langevin sampler for quantum tomography** [[paper](https://arxiv.org/abs/2601.08775)]

##### 2025

- [2025] **The Bayesian Way: Uncertainty, Learning, and Statistical Reasoning** [[paper](https://arxiv.org/abs/2512.05883)]
- [2025] **Singular Fluctuation as Specific Heat in Bayesian Learning** [[paper](https://arxiv.org/abs/2512.21411)]
- [2025] **Peace Sells, But Whose Songs Connect? Bayesian Multilayer Network Analysis of the Big 4 of Thrash Metal** [[paper](https://arxiv.org/abs/2512.10254)]
- [2025] **Graphon-Level Bayesian Predictive Synthesis for Random Network** [[paper](https://arxiv.org/abs/2512.18587)]
- [2025] **Convergence analysis of data augmentation algorithms in Bayesian lasso models with log-concave likelihoods** [[paper](https://arxiv.org/abs/2512.20041)]
- [2025] **Contextual Peano Scan and Fast Image Segmentation Using Hidden and Evidential Markov Chains** [[paper](https://arxiv.org/abs/2512.11939)]
- [2025] **Bounds on Maximal Leakage over Bayesian Networks** [[paper](https://arxiv.org/abs/2512.04955)]
- [2025] **Bayesian Effective Dimension: A Mutual Information Perspective** [[paper](https://arxiv.org/abs/2512.23047)]
- [2025] **A novel sequential method for building upper and lower bounds of moments of distributions** [[paper](https://arxiv.org/abs/2512.01761)]
- [2025] **A Bayesian approach to learning mixtures of nonparametric components** [[paper](https://arxiv.org/abs/2512.12988)]
- [2025] **The Bayesian optimal two-stage design for clinical phase II trials based on Bayes factors** [[paper](https://arxiv.org/abs/2511.23144)]
- [2025] **Singular Learning Theory for Factor Analysis** [[paper](https://arxiv.org/abs/2511.15419)]
- [2025] **Minimum bounding polytropes for estimation of max-linear Bayesian networks** [[paper](https://arxiv.org/abs/2511.05962)]
- [2025] **Estimation of the Coefficient of Variation of Weibull Distribution under Type-I Progressively Interval Censoring: A Simulation-based Approach** [[paper](https://arxiv.org/abs/2511.16102)]
- [2025] **CBMA: Improving conformal prediction through Bayesian model averaging** [[paper](https://arxiv.org/abs/2511.16924)]
- [2025] **An Approximate Bayesian Approach to Optimal Input Signal Design for System Identification** [[paper](https://arxiv.org/abs/2511.04425)]
- [2025] **Structural Identifiability of Graphical Continuous Lyapunov Models** [[paper](https://arxiv.org/abs/2510.04985)]
- [2025] **Hyperparameter Selection via Early Stopping for Bayesian Semilinear PDEs** [[paper](https://arxiv.org/abs/2510.18547)]
- [2025] **Estimation in linear high dimensional Hawkes processes: a Bayesian approach** [[paper](https://arxiv.org/abs/2510.24182)]
- [2025] **Can Linear Probes Measure LLM Uncertainty?** [[paper](https://arxiv.org/abs/2510.04108)]
- [2025] **Batch learning equals online learning in Bayesian supervised learning** [[paper](https://arxiv.org/abs/2510.16892)]
- [2025] **Robust Semiparametric Inference for Bayesian Additive Regression Trees** [[paper](https://arxiv.org/abs/2509.24634)]
- [2025] **Resolution of the Borel-Kolmogorov Paradox via the Maximum Entropy Principle** [[paper](https://arxiv.org/abs/2509.24735)]
- [2025] **Dirichlet moment tensors and the correspondence between admixture and mixture of product models** [[paper](https://arxiv.org/abs/2509.25441)]
- [2025] **Apply Bayes Theorem to Optimize IVR Authentication Process** [[paper](https://arxiv.org/abs/2510.02378)]
- [2025] **An exploration of sequential Bayesian variable selection -- A comment on García-Donato et al. (2025). "Model uncertainty and missing data: An objective Bayesian perspective"** [[paper](https://arxiv.org/abs/2509.22901)]
- [2025] **A unified theory of the high-dimensional Laplace approximation with application to Bayesian inverse problems** [[paper](https://arxiv.org/abs/2509.07952)]
- [2025] **A nonparametric Bayesian analysis of independent and identically distributed observations of covariate-driven Poisson processes** [[paper](https://arxiv.org/abs/2509.02299)]

[⬆ Back to top](#paper-list)

#### Application

##### 2026

- [2026] **Sustainable and informed groundwater management in a critical karstic mining setting of western India: Application of Isotope-enabled Variational Bayesian-End Member Mixing Analysis** *Groundwater for Sustainable Development* [[paper](https://doi.org/10.1016/j.gsd.2026.101619)]
- [2026] **Uncertainty Estimation of Rheological Parameters of Soft Rock Using Bayesian Inference and its Application** *Rock Mechanics and Rock Engineering* [[paper](https://doi.org/10.1007/s00603-026-05405-2)]

[⬆ Back to top](#paper-list)

#### Evaluation

##### 2026

- [2026] **Generalized Bayesian multidimensional scaling and model comparison** *Statistics and Computing* [[paper](https://doi.org/10.1007/s11222-026-10839-3)]

[⬆ Back to top](#paper-list)

#### Development

##### 2026

- [2026] **Statistical inference and optimal design for multiple constant-stress accelerated life tests under ordered ranked set sampling with progressive Type-II censoring** *Statistical Papers* [[paper](https://doi.org/10.1007/s00362-026-01821-2)]

[⬆ Back to top](#paper-list)

#### Systems

##### 2026

- [2026] **Neural posterior estimation for scalable and accurate inverse parameter inference in Li-ion batteries** *Journal of Energy Storage* [[paper](https://doi.org/10.1016/j.est.2026.123823)]

[⬆ Back to top](#paper-list)

### Computational Methods

#### Method

##### 2026

- [2026] **Variational Inference Using a Differentiable Multigrid Linear Solver** [[paper](https://arxiv.org/abs/2608.00760)]
- [2026] **Optimal Designs in Multicomponent Stress Strength Reliability for the Unit Generalized Rayleigh Distribution** [[paper](https://arxiv.org/abs/2608.06214)]
- [2026] **A Computational Bayesian Framework for Entropy-Based Inference in the Inverse Gaussian Distribution Under Progressive Type-II Censoring** *Entropy* [[paper](https://doi.org/10.3390/e28080871)]
- [2026] **exdqlm: An R Package for Estimation and Analysis of Flexible Dynamic Quantile Linear Models** [[paper](https://arxiv.org/abs/2607.22760)]
- [2026] **VIBES -- A Two-Stage Scalable Bayesian Uncertainty Quantification Framework: Application to a Biomass Valorization Process** [[paper](https://arxiv.org/abs/2607.06743)]
- [2026] **Transit Destination Inference from Tap-In-Only Bus Smart-Card Data: A Hierarchical Bayesian Approach** [[paper](https://arxiv.org/abs/2608.11223)]
- [2026] **Simulation-consistent Estimation of the Marginal Likelihood for Block Models** [[paper](https://arxiv.org/abs/2607.23998)]
- [2026] **Scaling Results for Piecewise Deterministic Monte Carlo : A Survey** [[paper](https://arxiv.org/abs/2607.22449)]
- [2026] **SalientGS: Unified SfM-to-3DGS with Importance-Guided MCMC Gaussian Allocation** [[paper](https://arxiv.org/abs/2607.11285)] [[code](https://github.com/Six-Bit-TX/SalientGS)]
- [2026] **Risk-Aware Belief Control Barrier Functions over Random Finite Sets** [[paper](https://arxiv.org/abs/2607.15016)]
- [2026] **PiVoT: A Variational Solution for Real-time Large-scale Multi-object Detection and Tracking under Heavy Clutter** [[paper](https://arxiv.org/abs/2607.13891)]
- [2026] **Parallel Noising in Neural Markov Logic Networks** [[paper](https://arxiv.org/abs/2607.19126)]
- [2026] **Orthogonalized Design Matrices Speed-ups of Bayesian Semiparametric Regression** [[paper](https://arxiv.org/abs/2607.09013)]
- [2026] **Non-Asymptotic Error Bounds for SMC with Biased Proposals: Application to Conditional Diffusion Sampling** [[paper](https://arxiv.org/abs/2607.04780)]
- [2026] **Gradient-free Riemannian Langevin Sampler** [[paper](https://arxiv.org/abs/2607.07519)]
- [2026] **Generative Model Proposal based Particle Filtering for Data Assimilation** [[paper](https://arxiv.org/abs/2607.01012)]
- [2026] **Feedback stabilization of multi-qubit Hamiltonian parameters enabled by single-shot measurement-based sequential Monte Carlo** [[paper](https://arxiv.org/abs/2607.26480)]
- [2026] **Dynamic Online Processor-Native Inference for State Estimation** [[paper](https://arxiv.org/abs/2607.12095)]
- [2026] **Bayesian Inference: Kernel-Based Model for Surface Temperature Reconstruction in Ice Borehole Thermometry** [[paper](https://arxiv.org/abs/2607.20322)]
- [2026] **BayesPO: Bayesian Prompt Optimization via Parallel-Tempered Gradient-Guided Discrete MCMC** [[paper](https://arxiv.org/abs/2607.16001)]
- [2026] **ABC methods for IoT Emitter Geolocalisation using LEO Satellite Doppler Measurements** [[paper](https://arxiv.org/abs/2607.28585)]
- [2026] **Markov Chain Monte Carlo** *Cambridge University Press eBooks* [[paper](https://doi.org/10.1017/9781009709071.014)]
- [2026] **Comparative Analysis of Probabilistic Risk Models for Sustainable Construction Risk Management in Developing Economies** *Mendeley Data* [[paper](https://doi.org/10.17632/w3b29j9tbj)]
- [2026] **Using Variational Inference to Improve the Efficiency of MCMC Algorithms** [[paper](https://arxiv.org/abs/2606.29205)]
- [2026] **Structured Nonparametric Variational Inference for Dependent Latent Modeling** [[paper](https://arxiv.org/abs/2606.15458)]
- [2026] **Stochastic Volatility in Mean Models with Heavy Tails: A Fast Approximate Bayesian Inference Using Hidden Markov Models** [[paper](https://arxiv.org/abs/2606.22615)]
- [2026] **SphereVBx: Spherical Variational Bayes Clustering for Simplified EEND-VC Diarization** [[paper](https://arxiv.org/abs/2606.24528)]
- [2026] **SMC-ITA: Sequential Monte Carlo Inference-Time Alignment for Video-to-Audio Generation** [[paper](https://arxiv.org/abs/2606.08393)]
- [2026] **Revisiting the Quantum-Guided Cluster Algorithm: Improvements and Numerical Experiments** [[paper](https://arxiv.org/abs/2606.01826)]
- [2026] **Resampling in conditional SMC algorithms** [[paper](https://arxiv.org/abs/2606.25603)]
- [2026] **On the design distribution for predictive Bayesian regression** [[paper](https://arxiv.org/abs/2606.14544)]
- [2026] **Neural posterior estimation of Galactic Binary signals for the LISA mission** [[paper](https://arxiv.org/abs/2606.29039)]
- [2026] **Implicit Variational Rejection Sampling** [[paper](https://arxiv.org/abs/2606.14235)]
- [2026] **Gaussian Mean Field Variational Inference can Overestimate Predictive Variance** [[paper](https://arxiv.org/abs/2606.25745)]
- [2026] **Error bounds for simultaneous Wasserstein contractive adaptive increasingly rare MCMC** [[paper](https://arxiv.org/abs/2606.30018)]
- [2026] **Bayesian 3D Steerable CNNs: Enabling Equivariance and Uncertainty Quantification Simultaneously** [[paper](https://arxiv.org/abs/2606.15479)]
- [2026] **BCL: Bayesian In-Context Learning Framework for Information Extraction** [[paper](https://arxiv.org/abs/2606.18620)]
- [2026] **An example of Ensemble Kalman Filter with resampling** [[paper](https://arxiv.org/abs/2606.25539)]
- [2026] **AIA: A 16nm Multicore SoC for Approximate Inference Acceleration Exploiting Non-normalized Knuth-Yao Sampling and Inter-Core Register Sharing** [[paper](https://arxiv.org/abs/2606.16148)]
- [2026] **A Bayesian spatio-temporal nearest neighbor Gaussian process model for pooled genetic data** [[paper](https://arxiv.org/abs/2606.19743)]
- [2026] **Fast Estimation and Valid Statistical Inference for Mixed‐Effect Location‐Scale Models Using Variational Inference** *Statistics in Medicine* [[paper](https://doi.org/10.1002/sim.70640)]
- [2026] **Quantifying uncertainty in financial forecasting: A Bayesian deep learning approach integrating MCMC and variational inference with multi-pass estimation** *Information Sciences* [[paper](https://doi.org/10.1016/j.ins.2026.123752)]
- [2026] **Medical ultrasound full waveform inversion via Stein variational inference: posterior mean reconstruction and uncertainty quantification** *Inverse Problems* [[paper](https://doi.org/10.1088/1361-6420/ae8294)]
- [2026] **BayesDensity.jl: Bayesian nonparametric density estimation in Julia** *SoftwareX* [[paper](https://doi.org/10.1016/j.softx.2026.102847)]
- [2026] **dirichletprocess: An R Package for Fitting Complex Bayesian Nonparametric Models** [[paper](https://arxiv.org/abs/2605.01603)]
- [2026] **bde: A Python Package for Bayesian Deep Ensembles via MILE** [[paper](https://arxiv.org/abs/2605.14146)]
- [2026] **Variational Inference for Lévy Process-Driven SDEs via Neural Tilting** [[paper](https://arxiv.org/abs/2605.10934)]
- [2026] **Uncertainty Quantification in Data-Driven Inverse Optimization via Bayesian Inference** [[paper](https://arxiv.org/abs/2605.25288)]
- [2026] **Uncertainty Quantification for Cardiac Shape Reconstruction with Deep Signed Distance Functions via MCMC methods** [[paper](https://arxiv.org/abs/2605.07987)]
- [2026] **Unbiased Diffusion Variational Inversion via Principled Posterior Matching** [[paper](https://arxiv.org/abs/2605.25042)]
- [2026] **Ultra-light axion constraints from Planck and ACT: the role of nonlinear modelling** [[paper](https://arxiv.org/abs/2605.12054)]
- [2026] **Training-Free Bayesian Filtering with Generative Emulators** [[paper](https://arxiv.org/abs/2605.20028)]
- [2026] **The Score Kalman Filter** [[paper](https://arxiv.org/abs/2605.16644)]
- [2026] **The Bayesian Gaussian Process Latent Variable Model for Spatio-Temporal Stream Networks** [[paper](https://arxiv.org/abs/2605.21307)]
- [2026] **Tempered Guided Diffusion** [[paper](https://arxiv.org/abs/2605.03712)]
- [2026] **Synthetic Well Log Generation with Preserved Multivariate Correlations and Vertical Facies Stacking Patterns** [[paper](https://arxiv.org/abs/2605.06255)]
- [2026] **StanBKT: Rethinking Parameter Estimation in Bayesian Knowledge Tracing** [[paper](https://arxiv.org/abs/2605.23048)]
- [2026] **Sequential Monte Carlo for Resilient Networks: Assessment, Mitigation, and Generative Modeling** [[paper](https://arxiv.org/abs/2605.04751)]
- [2026] **Scalable High-Dimensional Bayesian Field Reconstruction with Finite Elements: Application to 3D Porous Media Flow** [[paper](https://arxiv.org/abs/2605.24682)]
- [2026] **SMCEvolve: Principled Scientific Discovery via Sequential Monte Carlo Evolution** [[paper](https://arxiv.org/abs/2605.15308)] [[code](https://github.com/kongwanbianjinyu/SMCEvolve)]
- [2026] **Modeling Misclassification in Spousal Violence Reporting: Evidence from Bayesian Quantile Regression** [[paper](https://arxiv.org/abs/2605.15428)]
- [2026] **Inference-Time Alignment of Diffusion Models via Trust-Region Iterative Twisted Sequential Monte Carlo** [[paper](https://arxiv.org/abs/2605.25123)]
- [2026] **Greedy or not, here I come: Language production under vocabulary constraints in humans and resource-rational models** [[paper](https://arxiv.org/abs/2605.15365)]
- [2026] **Fast Monte-Carlo** [[paper](https://arxiv.org/abs/2605.02085)]
- [2026] **Efficient Learning of Deep State Space Models via Importance Smoothing** [[paper](https://arxiv.org/abs/2605.21108)]
- [2026] **Deep Variational Inference Symbolic Regression** [[paper](https://arxiv.org/abs/2605.01067)]
- [2026] **Decentralized Proximal Stochastic Gradient Langevin Dynamics** [[paper](https://arxiv.org/abs/2605.00723)]
- [2026] **Contrastive Distribution Matching for Amortized Sequential Monte Carlo in Discrete Diffusion** [[paper](https://arxiv.org/abs/2605.23346)]
- [2026] **Chained Markov melding using divide and conquer sequential Monte Carlo** [[paper](https://arxiv.org/abs/2605.22301)]
- [2026] **Bayesian Rain Field Reconstruction using Commercial Microwave Links and Diffusion Model Priors** [[paper](https://arxiv.org/abs/2605.05520)]
- [2026] **Bayesian Nonparametric Clustering to Support Medical Decision-Making: A Variational Inference Approach** [[paper](https://arxiv.org/abs/2605.31511)]
- [2026] **Amortized Factor Inference Networks for Posterior Inference** [[paper](https://arxiv.org/abs/2605.26419)] [[code](https://github.com/joohwanko/AFINs)]
- [2026] **Adversarial Configurations for the ReCom Transition Function** [[paper](https://arxiv.org/abs/2606.01333)]
- [2026] **Accelerating Bayesian Phylogenetic Inference via Delayed Acceptance Sequential Monte Carlo with Random Forest Surrogates** [[paper](https://arxiv.org/abs/2605.09506)] [[code](https://github.com/wentYu/DAphyloSMC)]
- [2026] **A Scalable Parametric Item Calibration Engine (SPICE) for Explanatory IRT with Sparse Data** [[paper](https://arxiv.org/abs/2605.21782)]
- [2026] **A Gaussian Sum Filter for Unifying Gaussian and Particle Filters** [[paper](https://arxiv.org/abs/2605.21698)]
- [2026] **Consistent multiscale modelling of movement and habitat selection** *Journal of Mathematical Biology* [[paper](https://doi.org/10.1007/s00285-026-02370-w)]
- [2026] **Approximation bias during marginalization over nuisance parameters in likelihood-based variational inference, and its impact on Bayesian solutions** *Geophysical Journal International* [[paper](https://doi.org/10.1093/gji/ggag180)]
- [2026] **Fast Variational Bayes for Large Spatial Data** *Journal of Computational and Graphical Statistics* [[paper](https://arxiv.org/abs/2507.12251)]
- [2026] **Learning Multimodal Energy-Based Model with Multimodal Variational Auto-Encoder via MCMC Revision** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2605.00644)]
- [2026] **VBGS-SLAM: Variational Bayesian Gaussian Splatting Simultaneous Localization and Mapping** [[paper](https://arxiv.org/abs/2604.02696)]
- [2026] **Tempered Sequential Monte Carlo for Trajectory and Policy Optimization with Differentiable Dynamics** [[paper](https://arxiv.org/abs/2604.21456)]
- [2026] **Scalable Model-Based Clustering with Sequential Monte Carlo** [[paper](https://arxiv.org/abs/2604.14810)]
- [2026] **Reversible Jump MCMC With No Regrets: Bayesian Variable Selection Using Mixtures of Mutually Singular Distributions** [[paper](https://arxiv.org/abs/2604.27791)]
- [2026] **Replacing Gaussian Processes with Neural Networks in Pulsar Timing Array Inference of the Gravitational-Wave Background** [[paper](https://arxiv.org/abs/2604.04340)]
- [2026] **Radio signal generation in milliseconds: enabling multi-parameter reconstruction of ultra-high-energy cosmic rays** [[paper](https://arxiv.org/abs/2604.27684)]
- [2026] **Occam's Razor is Only as Sharp as Your ELBO** [[paper](https://arxiv.org/abs/2604.25984)]
- [2026] **LiDAR-based Dynamic Blockage Prediction: A Data-driven Approach for Learning Interactive Bayesian Models** [[paper](https://arxiv.org/abs/2604.28040)]
- [2026] **Learning with Embedded Linear Equality Constraints via Variational Bayesian Inference** [[paper](https://arxiv.org/abs/2604.24911)]
- [2026] **Laplace and skew-Laplace approximations for Dirichlet process mixture posterior density** [[paper](https://arxiv.org/abs/2604.25410)]
- [2026] **Implications of weak convergence rates of Markov transition kernels** [[paper](https://arxiv.org/abs/2604.25867)]
- [2026] **GPA: Learning GUI Process Automation from Demonstrations** [[paper](https://arxiv.org/abs/2604.01676)]
- [2026] **Faster LLM Inference via Sequential Monte Carlo** [[paper](https://arxiv.org/abs/2604.15672)]
- [2026] **DRL-Based Antenna Position Optimization For MA-Assisted OTFS System Under Imperfect CSI** [[paper](https://arxiv.org/abs/2604.23611)]
- [2026] **Bayesian approach for uncertainty quantification of hybrid spectral unmixing in γ-ray spectrometry** [[paper](https://arxiv.org/abs/2604.20691)]
- [2026] **A Predictive View on Streaming Hidden Markov Models** [[paper](https://arxiv.org/abs/2604.09208)]
- [2026] **Nii-body: Bayesian Inference of Multiplanet Dynamics in N-body Simulations** *Astronomical Techniques and Instrument* [[paper](https://doi.org/10.3724/ati2026004)]
- [2026] **Nii-body: Bayesian Inference of Multiplanet Dynamics via N-body Simulations** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2604.09383)]
- [2026] **High-throughput parameter estimation from experimental data using Bayesian Inference with accelerated sampling** *npj Computational Materials* [[paper](https://doi.org/10.1038/s41524-026-01995-1)]
- [2026] **Robust parameter inference for Taiji via time-frequency contrastive learning and normalizing flows** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2604.13867)]
- [2026] **MIXED-EFFECT MODELS WITH RESTRICTED MAXIMUM LIKELIHOOD (REML), BOOT-STRAPPED REML AND BAYESIAN INFERENCE IN APPLICATION OF GAPMINDER DATA** *BAREKENG JURNAL ILMU MATEMATIKA DAN TERAPAN* [[paper](https://doi.org/10.30598/barekengvol20iss3pp1985-1998)]
- [2026] **Neural Autoregressive Flows Based Variational Bayes Model Averaging** *The American Statistician* [[paper](https://doi.org/10.1080/00031305.2026.2654767)]
- [2026] **Model calibration and reliability updating for array antenna using an integrated variational Bayesian and subset simulation framework** *Reliability Engineering & System Safety* [[paper](https://doi.org/10.1016/j.ress.2026.112765)]
- [2026] **Scalable Bayesian full waveform inversion via dual augmented Lagrangian SVGD** [[paper](https://arxiv.org/abs/2603.24751)]
- [2026] **Rule-State Inference (RSI): A Bayesian Framework for Compliance Monitoring in Rule-Governed Domains** [[paper](https://arxiv.org/abs/2603.21610)]
- [2026] **Reject, Resample, Repeat: Understanding Parallel Reasoning in Language Model Inference** [[paper](https://arxiv.org/abs/2603.07887)]
- [2026] **Parallelizable Feynman-Kac Models for Universal Probabilistic Programming** [[paper](https://arxiv.org/abs/2603.22463)]
- [2026] **Leveraging Sparsity to Improve No-U-Turn Sampling Efficiency for Hierarchical Bayesian Models** [[paper](https://arxiv.org/abs/2603.02437)]
- [2026] **Laplace Variational Inference for Bayesian Envelope Models** [[paper](https://arxiv.org/abs/2603.00927)]
- [2026] **Joint Inverse Learning of Cognitive Radar Perception and Perception-Action Policy** [[paper](https://arxiv.org/abs/2603.07051)]
- [2026] **Generalized Sequential Monte Carlo Sampling for Redistricting Simulation** [[paper](https://arxiv.org/abs/2603.22188)]
- [2026] **Functional Bias and Tangent-Space Geometry in Variational Inference** [[paper](https://arxiv.org/abs/2603.08925)]
- [2026] **Flexible and Scalable Bayesian Modelling of Spatio-Temporal Hawkes Processes** [[paper](https://arxiv.org/abs/2603.28556)]
- [2026] **Fast Posterior Sampling in Tightly Identified SVARs Using 'Soft' Sign Restrictions** [[paper](https://arxiv.org/abs/2603.27088)]
- [2026] **Experimental Realization of the Markov Chain Monte Carlo Algorithm on a Quantum Computer** [[paper](https://arxiv.org/abs/2603.08395)]
- [2026] **Demonstration of Adapt4Me: An Uncertainty-Aware Authoring Environment for Personalizing Automatic Speech Recognition to Non-normative Speech** [[paper](https://arxiv.org/abs/2603.20112)]
- [2026] **Bayesian Uncertainty-Aware MRI Reconstruction** [[paper](https://arxiv.org/abs/2603.13439)]
- [2026] **Bayesian Learning of (n,p) Reaction Cross Sections with Quantified Uncertainties** [[paper](https://arxiv.org/abs/2603.04789)]
- [2026] **Bayesian Inference in Epidemic Modelling: A Beginner's Guide** [[paper](https://arxiv.org/abs/2603.15175)]
- [2026] **Adiabatic dressing of quantum enhanced Markov chains** [[paper](https://arxiv.org/abs/2603.28076)]
- [2026] **A Hybrid Particle Gaussian Mixture Filtering Method for Cislunar Orbit Determination Under Extreme Uncertainty** [[paper](https://arxiv.org/abs/2603.01428)]
- [2026] **The use of variational inference for lifetime data with spatial correlations** *Journal of Quality Technology* [[paper](https://arxiv.org/abs/2507.09559)]
- [2026] **b-transD: Spatial and temporal variation of b-value and their uncertainty using Bayesian trans-dimensional inference** [[paper](https://doi.org/10.5194/egusphere-egu26-8613)]
- [2026] **&lt;b&gt;Scalable Inference for Bayesian Proportion Models: Variational Approaches under Contaminated Likelihoods&lt;/b&gt;&lt;b&gt;&lt;/b&gt;** *مجلة العلوم الأساسـية* [[paper](https://doi.org/10.31185/bsj.vol21.iss35.1241)]
- [2026] **Bayesian Estimation of Nonlinear Time Series Models with Real Data Applications** *SCIREA Journal of Mathematics* [[paper](https://doi.org/10.54647/mathematics110563)]
- [2026] **Korvikemalleihin perustuvat menetelmät tehokkaaseen Bayesilaiseen posteriorilaskentaan** *Työväentutkimus Vuosikirja* [[paper](https://hdl.handle.net/10138/628873)]
- [2026] **Weak Poincaré inequalities for Deterministic-scan Metropolis-within-Gibbs samplers** [[paper](https://arxiv.org/abs/2602.14692)]
- [2026] **Variational and Monte Carlo Methods for Bayesian Inversion of Dynamic Subsurface Flow Simulations Using Seismic and Fluid Pressure Data** [[paper](https://arxiv.org/abs/2602.02993)]
- [2026] **VariBASed: Variational Bayes-Adaptive Sequential Monte-Carlo Planning for Deep Reinforcement Learning** [[paper](https://arxiv.org/abs/2602.18857)]
- [2026] **Unified Estimation--Guidance Framework Based on Bayesian Decision Theory** [[paper](https://arxiv.org/abs/2602.11373)]
- [2026] **TFTF: Training-Free Targeted Flow for Conditional Sampling** [[paper](https://arxiv.org/abs/2602.12932)]
- [2026] **Solving Poisson's equation for Wasserstein contractive Markov chains** [[paper](https://arxiv.org/abs/2602.19119)]
- [2026] **Self-Rewarding Sequential Monte Carlo for Masked Diffusion Language Models** [[paper](https://arxiv.org/abs/2602.01849)] [[code](https://github.com/Algolzw/self-rewarding-smc)]
- [2026] **PriorProbe: Recovering Individual-Level Priors for Personalizing Neural Networks in Facial Expression Recognition** [[paper](https://arxiv.org/abs/2602.03882)]
- [2026] **Non-centred Bayesian inference for discrete-valued state-transition models: the Rippler algorithm** [[paper](https://arxiv.org/abs/2602.10924)]
- [2026] **Lookahead Sample Reward Guidance for Test-Time Scaling of Diffusion Models** [[paper](https://arxiv.org/abs/2602.03211)] [[code](https://github.com/aailab-kaist/Diffusion-LiDAR-Sampling)]
- [2026] **Lookahead Path Likelihood Optimization for Diffusion LLMs** [[paper](https://arxiv.org/abs/2602.03496)]
- [2026] **Latent Matters: Learning Deep State-Space Models** *NeurIPS 2021* [[paper](https://arxiv.org/abs/2602.23050)]
- [2026] **Large-scale Score-based Variational Posterior Inference for Bayesian Deep Neural Networks** [[paper](https://arxiv.org/abs/2602.05873)]
- [2026] **Higher-Order Hit-&amp;-Run Samplers for Linearly Constrained Densities** [[paper](https://arxiv.org/abs/2602.14616)]
- [2026] **Functional Estimation of the Marginal Likelihood** [[paper](https://arxiv.org/abs/2602.07148)]
- [2026] **Function-Space Empirical Bayes Regularisation with Student's t Priors** [[paper](https://arxiv.org/abs/2602.22015)]
- [2026] **Function-Space Empirical Bayes Regularisation with Large Vision-Language Model Priors** [[paper](https://arxiv.org/abs/2602.03119)]
- [2026] **Fast Compute via MC Boosting** [[paper](https://arxiv.org/abs/2602.05032)]
- [2026] **Ergodicity of an Adaptive MCMC Sampler under a Probability Bound** [[paper](https://arxiv.org/abs/2602.06568)]
- [2026] **Diffusion Alignment Beyond KL: Variance Minimisation as Effective Policy Optimiser** [[paper](https://arxiv.org/abs/2602.12229)]
- [2026] **Diamond Maps: Efficient Reward Alignment via Stochastic Flow Maps** [[paper](https://arxiv.org/abs/2602.05993)]
- [2026] **DerivKit: stable numerical derivatives bridging Fisher forecasts and MCMC** [[paper](https://arxiv.org/abs/2602.08078)]
- [2026] **Counterdiabatic Hamiltonian Monte Carlo** [[paper](https://arxiv.org/abs/2602.21272)]
- [2026] **Compact Circulant Layers with Spectral Priors** [[paper](https://arxiv.org/abs/2602.21965)]
- [2026] **Bayesian PINNs for uncertainty-aware inverse problems (BPINN-IP)** [[paper](https://arxiv.org/abs/2602.04459)]
- [2026] **Amortised and provably-robust simulation-based inference** [[paper](https://arxiv.org/abs/2602.11325)]
- [2026] **A multifidelity approximate Bayesian computation with pre-filtering** [[paper](https://arxiv.org/abs/2602.01770)] [[code](https://github.com/caofff/MAPS)]
- [2026] **A Probabilistic Framework for LLM-Based Model Discovery** [[paper](https://arxiv.org/abs/2602.18266)]
- [2026] **A Comparison of Bayesian Prediction Techniques for Mobile Robot Trajectory Tracking** [[paper](https://arxiv.org/abs/2602.15354)]
- [2026] **Bayesian transfer learning with Monte Carlo Markov Chains for kinetic modelling of pilot plant and industrial data** *Digital Chemical Engineering* [[paper](https://doi.org/10.1016/j.dche.2026.100295)]
- [2026] **Bayesian Computation in Deep Learning** [[paper](https://doi.org/10.1201/9781003453420-22)]
- [2026] **Neural Markov chain Monte Carlo: Bayesian inversion via normalizing flows and variational autoencoders** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2602.19597)]
- [2026] **Zeroth-order parallel sampling** [[paper](https://arxiv.org/abs/2601.19722)]
- [2026] **Variational approximate penalized credible regions for Bayesian grouped regression** [[paper](https://arxiv.org/abs/2601.16585)]
- [2026] **Variational Autoencoder with Normalizing flow for X-ray spectral fitting** *NeurIPS 2025* [[paper](https://arxiv.org/abs/2601.07440)]
- [2026] **Toward Scalable Normalizing Flows for the Hubbard Model** [[paper](https://arxiv.org/abs/2601.18273)]
- [2026] **The Sequential Monte Carlo goes NUTS: Boosting Gravitational-Wave Inference** [[paper](https://arxiv.org/abs/2601.02336)]
- [2026] **Sub-Cauchy Sampling: Escaping the Dark Side of the Moon** [[paper](https://arxiv.org/abs/2601.11066)]
- [2026] **Soft Bayesian Context Tree Models for Real-Valued Time Series** [[paper](https://arxiv.org/abs/2601.11079)]
- [2026] **Probing a Lorentz-violating parameter from orbital precession of the S2 star around the galactic centre supermassive black hole** [[paper](https://arxiv.org/abs/2601.06491)]
- [2026] **Poisson Hyperplane Processes with Rectified Linear Units** [[paper](https://arxiv.org/abs/2601.05586)] [[code](https://github.com/ShufeiGe/Pois_Relu.git)]
- [2026] **Particle-Guided Diffusion Models for Partial Differential Equations** [[paper](https://arxiv.org/abs/2601.23262)]
- [2026] **Multilevel and Sequential Monte Carlo for Training-Free Diffusion Guidance** [[paper](https://arxiv.org/abs/2601.21104)]
- [2026] **Mean-field Variational Bayes for Sparse Probit Regression** [[paper](https://arxiv.org/abs/2601.21765)]
- [2026] **Lagrangian Grid-based Estimation of Nonlinear Systems with Invertible Dynamics** [[paper](https://arxiv.org/abs/2601.07721)] [[code](https://github.com/pesslovany/Matlab-LagrangianPMF)]
- [2026] **Flow Perturbation++: Multi-Step Unbiased Jacobian Estimation for High-Dimensional Boltzmann Sampling** [[paper](https://arxiv.org/abs/2601.21177)]
- [2026] **Efficient Stochastic Optimisation via Sequential Monte Carlo** [[paper](https://arxiv.org/abs/2601.22003)]
- [2026] **Diffusion Path Samplers via Sequential Monte Carlo** [[paper](https://arxiv.org/abs/2601.21951)]
- [2026] **Constraint-Aware Neurosymbolic Uncertainty Quantification with Bayesian Deep Learning for Scientific Discovery** [[paper](https://arxiv.org/abs/2601.12442)]
- [2026] **Adaptive Exponential Integration for Stable Gaussian Mixture Black-Box Variational Inference** [[paper](https://arxiv.org/abs/2601.14855)]
- [2026] **A forward-only scheme for online learning of proposal distributions in particle filters** [[paper](https://arxiv.org/abs/2601.16089)]
- [2026] **A Kernel Approach for Semi-implicit Variational Inference** [[paper](https://arxiv.org/abs/2601.12023)]

##### 2025

- [2025] **Variational Inference for Fully Bayesian Hierarchical Linear Models** [[paper](https://arxiv.org/abs/2512.12857)]
- [2025] **Uncertainty-Preserving QBNNs: Multi-Level Quantization of SVI-Based Bayesian Neural Networks for Image Classification** [[paper](https://arxiv.org/abs/2512.10602)]
- [2025] **Uncertainty quantification for mixed membership in multilayer networks with degree heterogeneity using Gaussian variational inference** [[paper](https://arxiv.org/abs/2512.08146)]
- [2025] **Topic-informed dynamic mixture model for occupational heterogeneity in health risk behaviors** [[paper](https://arxiv.org/abs/2512.20408)]
- [2025] **Scrutinizing the KNT model with vacuum stability conditions** [[paper](https://arxiv.org/abs/2512.23662)]
- [2025] **Revisiting the Reported Period of FRB 20201124A Using MCMC Methods** [[paper](https://arxiv.org/abs/2512.23392)]
- [2025] **PSI3D: Plug-and-Play 3D Stochastic Inference with Slice-wise Latent Diffusion Prior** [[paper](https://arxiv.org/abs/2512.18367)]
- [2025] **On the efficiency of parameter space exploration: A scotogenic case study** [[paper](https://arxiv.org/abs/2512.06378)]
- [2025] **Laplace Approximation For Tensor Train Kernel Machines In System Identification** [[paper](https://arxiv.org/abs/2512.02532)]
- [2025] **Gradient-Informed Monte Carlo Fine-Tuning of Diffusion Models for Low-Thrust Trajectory Design** [[paper](https://arxiv.org/abs/2512.08705)]
- [2025] **Gaussian Process State-Space Modeling and Particle Filtering for Time Series Decomposition and Nonlinear Signal Extraction** [[paper](https://arxiv.org/abs/2512.01162)]
- [2025] **Feasibility to probe the dynamical scotogenic model at the LHC** [[paper](https://arxiv.org/abs/2512.17903)]
- [2025] **Exact inference via quasi-conjugacy in two-parameter Poisson-Dirichlet hidden Markov models** [[paper](https://arxiv.org/abs/2512.22098)]
- [2025] **Efficient sequential Bayesian inference for state-space epidemic models using ensemble data assimilation** [[paper](https://arxiv.org/abs/2512.05650)]
- [2025] **Dynamical Dark Energy in light of DESI BAO and Full-Shape Data** [[paper](https://arxiv.org/abs/2512.07104)]
- [2025] **Diffusion differentiable resampling** *ICML 2026* [[paper](https://arxiv.org/abs/2512.10401)]
- [2025] **Designing an Optimal Sensor Network via Minimizing Information Loss** [[paper](https://arxiv.org/abs/2512.05940)]
- [2025] **Cosmological Models with Symmetric Teleparallel Gravity and its Extension** [[paper](https://arxiv.org/abs/2512.15096)]
- [2025] **Bayesian Symbolic Regression via Posterior Sampling** [[paper](https://arxiv.org/abs/2512.10849)]
- [2025] **A Novel Framework Using Variational Inference with Normalizing Flows to Train Transport Reversible Jump Proposals** [[paper](https://arxiv.org/abs/2512.12742)]
- [2025] **samsara: A Continuous-Time Markov Chain Monte Carlo Sampler for Trans-Dimensional Bayesian Analysis** [[paper](https://arxiv.org/abs/2511.07385)]
- [2025] **Viscous Dark Energy and Mass-Varying Dark Matter in Lyra Manifold: Cosmological Dynamics and Observational Constraints** [[paper](https://arxiv.org/abs/2511.15422)]
- [2025] **Twice Sequential Monte Carlo for Tree Search** [[paper](https://arxiv.org/abs/2511.14220)]
- [2025] **Theory and computation for structured variational inference** [[paper](https://arxiv.org/abs/2511.09897)]
- [2025] **Sequential Markov Chain Monte Carlo for Filtering of State-Space Models with Low or Degenerate Observation Noise** [[paper](https://arxiv.org/abs/2511.04975)]
- [2025] **SIMBA: Scalable Image Modeling using a Bayesian Approach, A Consistent Framework for Including Spatial Dependencies in fMRI Studies** [[paper](https://arxiv.org/abs/2511.12825)]
- [2025] **Rényi's α-divergence variational Bayes for spike-and-slab high-dimensional linear regression** [[paper](https://arxiv.org/abs/2512.00627)]
- [2025] **Particle Monte Carlo methods for Lattice Field Theory** [[paper](https://arxiv.org/abs/2511.15196)]
- [2025] **Particle Filter Made Simple: A Step-by-Step Beginner-friendly Guide** [[paper](https://arxiv.org/abs/2511.01281)]
- [2025] **PAC-Bayes Meets Online Contextual Optimization** [[paper](https://arxiv.org/abs/2511.20413)]
- [2025] **Natural gradient descent for improving variational inference based classification of radio galaxies** [[paper](https://arxiv.org/abs/2511.13224)]
- [2025] **Measuring gravitational wave spectrum from electroweak phase transition and Higgs self-couplings** [[paper](https://arxiv.org/abs/2511.00996)]
- [2025] **Maxitive Donsker-Varadhan Formulation for Possibilistic Variational Inference** [[paper](https://arxiv.org/abs/2511.21223)]
- [2025] **Machine Learning the Conformal Manifold of Holographic CFT_{2}s** [[paper](https://arxiv.org/abs/2511.02981)]
- [2025] **Low redshift observational constraints on dark energy models using ANN - CosmicANNEstimator** [[paper](https://arxiv.org/abs/2511.04033)]
- [2025] **Latent Modularity in Multi-View Data** [[paper](https://arxiv.org/abs/2511.00455)]
- [2025] **Incorporating Bayesian Transfer Learning into Particle Filter for Dual-Tracking System with Asymmetric Noise Intensities** [[paper](https://arxiv.org/abs/2511.17440)]
- [2025] **High-dimensional Bayesian filtering through deep density approximation** [[paper](https://arxiv.org/abs/2511.07261)]
- [2025] **High-Dimensional Covariate-Dependent Discrete Graphical Models and Dynamic Ising Models** [[paper](https://arxiv.org/abs/2511.14123)]
- [2025] **Hierarchical Besov-Laplace priors for spatially inhomogeneous binary classification** [[paper](https://arxiv.org/abs/2511.21441)]
- [2025] **Gaussian approximations for fast Bayesian inference of partially observed branching processes with applications to epidemiology** [[paper](https://arxiv.org/abs/2511.22833)]
- [2025] **Enhancing NTRUEncrypt Security Using Markov Chain Monte Carlo Methods: Theory and Practice** [[paper](https://arxiv.org/abs/2511.02365)]
- [2025] **Downlink Channel Estimation for mmWave Systems with Impulsive Interference** [[paper](https://arxiv.org/abs/2511.02291)]
- [2025] **Convergence of a Sequential Monte Carlo algorithm towards multimodal distributions on Rd** [[paper](https://arxiv.org/abs/2511.22564)]
- [2025] **Bridging the Gap Between Bayesian Deep Learning and Ensemble Weather Forecasts** [[paper](https://arxiv.org/abs/2511.14218)]
- [2025] **Bayesian compartmental modelling of MRSA transmission within hospitals in Edmonton, Canada** [[paper](https://arxiv.org/abs/2511.07353)]
- [2025] **Bayesian Topological Analysis of Functional Brain Networks** [[paper](https://arxiv.org/abs/2511.03605)]
- [2025] **Bayesian Risk-averse Model Predictive Control with Consistency and Stability Guarantees** [[paper](https://arxiv.org/abs/2511.21871)]
- [2025] **Accelerated Sequential Posterior Inference via Reuse for Gravitational-Wave Analyses** [[paper](https://arxiv.org/abs/2511.04218)]
- [2025] **A Scalable Variational Bayes Approach for Fitting Non-Conjugate Spatial Generalized Linear Mixed Models via Basis Expansions** [[paper](https://arxiv.org/abs/2512.00895)]
- [2025] **A Comparison of Kernels for ABC-SMC** [[paper](https://arxiv.org/abs/2511.06351)]
- [2025] **3D Bayesian Variational Surface Wave Tomography and Application to the Southwest China** [[paper](https://arxiv.org/abs/2511.03278)]
- [2025] **Variational Polya Tree** [[paper](https://arxiv.org/abs/2510.22651)] [[code](https://github.com/howardchanth/var-polya-tree)]
- [2025] **Variational Inference for Count Response Semiparametric Regression: A Convex Solution** [[paper](https://arxiv.org/abs/2510.12356)]
- [2025] **Uniform ergodicity of geodesic slice sampling** [[paper](https://arxiv.org/abs/2510.06748)]
- [2025] **The Marked Edge Walk: A Novel MCMC Algorithm for Sampling of Graph Partitions** [[paper](https://arxiv.org/abs/2510.17714)]
- [2025] **Semi-Implicit Approaches for Large-Scale Bayesian Spatial Interpolation** [[paper](https://arxiv.org/abs/2510.19722)]
- [2025] **Rotated Mean-Field Variational Inference and Iterative Gaussianization** [[paper](https://arxiv.org/abs/2510.07732)]
- [2025] **Relaxed Sequence Sampling for Diverse Protein Design** [[paper](https://arxiv.org/abs/2510.23786)]
- [2025] **Oracle-based Uniform Sampling from Convex Bodies** [[paper](https://arxiv.org/abs/2510.02983)]
- [2025] **Neural variational inference for cutting feedback during uncertainty propagation** [[paper](https://arxiv.org/abs/2510.10268)]
- [2025] **Latent Chain-of-Thought for Visual Reasoning** [[paper](https://arxiv.org/abs/2510.23925)]
- [2025] **Knots and variance ordering of sequential Monte Carlo algorithms** [[paper](https://arxiv.org/abs/2510.01901)]
- [2025] **IrisML: Neural Posterior Estimation for the Spectral Energy Distribution fitting** [[paper](https://arxiv.org/abs/2510.26964)]
- [2025] **Input Adaptive Bayesian Model Averaging** [[paper](https://arxiv.org/abs/2510.22054)]
- [2025] **Group-Equivariant Diffusion Models for Lattice Field Theory** [[paper](https://arxiv.org/abs/2510.26081)]
- [2025] **Geometric Convergence Analysis of Variational Inference via Bregman Divergences** [[paper](https://arxiv.org/abs/2510.15548)]
- [2025] **False Discovery Rate Control via Bayesian Mirror Statistic** [[paper](https://arxiv.org/abs/2510.00875)]
- [2025] **Efficient Inference for Coupled Hidden Markov Models in Continuous Time and Discrete Space** [[paper](https://arxiv.org/abs/2510.12916)]
- [2025] **BI-DCGAN: A Theoretically Grounded Bayesian Framework for Efficient and Diverse GANs** [[paper](https://arxiv.org/abs/2510.26892)]
- [2025] **An integrated neural wavefunction solver for spinful Fermi systems** [[paper](https://arxiv.org/abs/2510.18621)]
- [2025] **Active Measuring in Reinforcement Learning With Delayed Negative Effects** [[paper](https://arxiv.org/abs/2510.14315)]
- [2025] **A coupling-based approach to f-divergences diagnostics for Markov chain Monte Carlo** [[paper](https://arxiv.org/abs/2510.07559)]
- [2025] **A Systematic Literature Review of Machine Learning Techniques for Observational Constraints in Cosmology** [[paper](https://arxiv.org/abs/2510.09876)]
- [2025] **A Frequentist Statistical Introduction to Variational Inference, Autoencoders, and Diffusion Models** [[paper](https://arxiv.org/abs/2510.18777)]
- [2025] **A Black Box Variational Inference Scheme for Inverse Problems with Demanding Physics-Based Models** [[paper](https://arxiv.org/abs/2510.25038)]
- [2025] **Two-scale criteria for Poincaré and log-Sobolev inequalities with applications to Markov chain Monte Carlo** [[paper](https://arxiv.org/abs/2509.15410)]
- [2025] **The-Bodega: A Matlab Toolbox for Biologically Dynamic Microbubble Simulations on Realistic Hemodynamic Microvascular Graphs** [[paper](https://arxiv.org/abs/2509.08149)]
- [2025] **Simulation-based Inference of Massive Black Hole Binaries using Sequential Neural Likelihood** [[paper](https://arxiv.org/abs/2509.13842)]
- [2025] **Quantum Markov Chain Monte Carlo for Cosmological Functions** [[paper](https://arxiv.org/abs/2509.09395)]
- [2025] **PDE-Based Bayesian Hierarchical Modeling for Event Spread, with Application to COVID-19 Infection** [[paper](https://arxiv.org/abs/2509.13174)]
- [2025] **Objective Bayesian inference for the Dhillon distribution** [[paper](https://arxiv.org/abs/2509.06344)]
- [2025] **Numerical Verification of Perturbative Schwinger-Dyson Resummation on Lattice Models** [[paper](https://arxiv.org/abs/2509.08501)]
- [2025] **Multi-modal Bayesian Neural Network Surrogates with Conjugate Last-Layer Estimation** [[paper](https://arxiv.org/abs/2509.21711)]
- [2025] **Misspecification-robust amortised simulation-based inference using variational methods** [[paper](https://arxiv.org/abs/2509.05724)]
- [2025] **Influence of supermassive primordial black holes on ultraviolet luminosity of high-redshift galaxies** [[paper](https://arxiv.org/abs/2509.03152)]
- [2025] **Inferring Soil Drydown Behaviour with Adaptive Bayesian Online Changepoint Analysis** [[paper](https://arxiv.org/abs/2509.13293)]
- [2025] **Feynman-Kac-Flow: Inference Steering of Conditional Flow Matching to an Energy-Tilted Posterior** [[paper](https://arxiv.org/abs/2509.01543)] [[code](https://github.com/heid-lab/fkflow)]
- [2025] **Extrapolation of Tempered Posteriors** [[paper](https://arxiv.org/abs/2509.12173)]
- [2025] **DriftLite: Lightweight Drift Control for Inference-Time Scaling of Diffusion Models** *ICLR 2026* [[paper](https://arxiv.org/abs/2509.21655)] [[code](https://github.com/yinuoren/DriftLite)]
- [2025] **Domain-Aware Probability Sampling for Hybrid Quantum Systems using Bayesian Optimization** [[paper](https://arxiv.org/abs/2510.00145)]
- [2025] **Diffusion Bridge Variational Inference for Deep Gaussian Processes** [[paper](https://arxiv.org/abs/2509.19078)]
- [2025] **CREPE: Controlling Diffusion with Replica Exchange** [[paper](https://arxiv.org/abs/2509.23265)]
- [2025] **Bayesian inference for velocity-jump models for movement** [[paper](https://arxiv.org/abs/2509.21226)]
- [2025] **Bayesian Parametric Matrix Models: Principled Uncertainty Quantification for Spectral Learning** [[paper](https://arxiv.org/abs/2509.12406)]
- [2025] **Bayesian Neural Networks versus deep ensembles for uncertainty quantification in machine learning interatomic potentials** [[paper](https://arxiv.org/abs/2509.19180)]
- [2025] **Adaptive Bayesian computation for efficient biobank-scale genomic inference** [[paper](https://arxiv.org/abs/2509.10736)]
- [2025] **A Hierarchical Variational Graph Fused Lasso for Recovering Relative Rates in Spatial Compositional Data** [[paper](https://arxiv.org/abs/2509.20636)]
- [2025] **Towards Instance-wise Personalized Federated Learning via Semi-Implicit Bayesian Prompt Tuning** [[paper](https://arxiv.org/abs/2508.19621)]
- [2025] **Static Factorisation of Probabilistic Programs With User-Labelled Sample Statements and While Loops** [[paper](https://arxiv.org/abs/2508.20922)]
- [2025] **Spherical latent space models for social network analysis** [[paper](https://arxiv.org/abs/2508.16556)]
- [2025] **SANVI: A Fast Spectral-Assisted Network Variational Inference Method with an Extended Surrogate Likelihood Function** [[paper](https://arxiv.org/abs/2509.00562)]
- [2025] **High-Order Langevin Monte Carlo Algorithms** [[paper](https://arxiv.org/abs/2508.17545)]

[⬆ Back to top](#paper-list)

#### Theory

##### 2026

- [2026] **Diffeomorphic Markov Chain Monte Carlo: fast mixing for heavy-tailed distributions** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2608.04284)]
- [2026] **Greedy stein variational gradient descent for inverse wave propagation problems** *Ingeniería Investigación y Tecnología* [[paper](https://doi.org/10.22201/fi.25940732e.2026.27.3.020)]
- [2026] **Can We Trust Item Response Theory for AI Evaluation?** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2607.15190)]
- [2026] **Statistical foundation of variational Bayes computer models** *Digital Repository at the University of Maryland (University of Maryland College Park)* [[paper](https://doi.org/10.13016/m2gckj-wq95)]
- [2026] **Inference on covariance structure in high-dimensional multi-view data** *Biometrika* [[paper](https://arxiv.org/abs/2509.02772)]
- [2026] **Bayesian Inference of Nonlinear Malaria Dynamics in Ghana via an Ensemble Markov Chain Monte Carlo Sampler** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2606.00783)]
- [2026] **Large-scale Uncertainty Quantification for Latent Variable Models Using Subsampling Markov Chain Monte Carlo** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2606.00309)]
- [2026] **Stabilised weighted data subsampling for accelerated inference in models with recursive likelihoods** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2605.13397)]
- [2026] **Post-Bayesian A2: Structural Openness, Essential Non-Ergodicity, and the Boundary of Statistical Inference: An Analysis Based on the Evolution of Number-Theoretic Constraint Systems** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19992569)]
- [2026] **Convergence analysis of stochastic gradient descent with MCMC estimators** *Science China Mathematics* [[paper](https://doi.org/10.1007/s11425-024-2557-7)]
- [2026] **Scalable Bayesian–XAI Framework for Multi-Objective Decision-Making in Uncertain Dynamic Systems** *Algorithms* [[paper](https://doi.org/10.3390/a19050340)]
- [2026] **Data-efficient neural operator surrogates for nonlinear pitch dynamics of blunt-body re-entry vehicles** *Aerospace Science and Technology* [[paper](https://doi.org/10.1016/j.ast.2026.112360)]
- [2026] **Heterogeneous Variational Inference for Markov Degradation Hazard Models: Discretized Mixture with Interpretable Clusters** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2604.24818)]
- [2026] **A Particle Algorithm for Mean-Field Variational Inference** *SIAM Journal on Optimization* [[paper](https://arxiv.org/abs/2412.20385)]
- [2026] **Post-Monte Carlo F; Path Tracking and Attractor Dynamics Sampling in Non-Ergodic Systems** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19731249)]
- [2026] **Hierarchical structured Stochastic Variational Inference for uncertainty quantification of viscoplastic constitutive models** *European Journal of Mechanics - A/Solids* [[paper](https://doi.org/10.1016/j.euromechsol.2026.106139)]
- [2026] **Amortized Variational Inference for Scalable Bayesian Tensor Factorization in Spatial Transcriptomics** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19852037)]
- [2026] **A New Exponential-Type Model Under Unified Progressive Hybrid Censoring: Computational Inference and Its Applications** *Mathematics* [[paper](https://doi.org/10.3390/math14071182)]
- [2026] **Advanced Bayesian modeling of fluorinated gas emissions in East Asia: Comparative performance of MCMC algorithms under censoring** *Ain Shams Engineering Journal* [[paper](https://doi.org/10.1016/j.asej.2026.104144)]
- [2026] **Efficient Estimation Methods for the QR Distribution with Type-II Censored Data: An Empirical Validation on Lung Cancer Prognosis** *Entropy* [[paper](https://doi.org/10.3390/e28050502)]
- [2026] **Restricted Search Space Graph MCMC via Birth-Death Processes** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2604.10863)]
- [2026] **Variational Inference of Bayesian Dynamic Generalized Additive Models for Mortality Analysis** *Figshare* [[paper](https://doi.org/10.6084/m9.figshare.31836148)]
- [2026] **Variational Inference of Bayesian Dynamic Generalized Additive Models for Mortality Analysis** *Journal of Computational and Graphical Statistics* [[paper](https://doi.org/10.1080/10618600.2026.2648593)]
- [2026] **Approximate Bayesian Inference for Structural Equation Models using Integrated Nested Laplace Approximations** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2603.25690)]
- [2026] **Inverse design of stochastic metamaterials via multi-physical knowledge fusion driven by deep-generative-prior Bayesian inference** *Computers & Structures* [[paper](https://doi.org/10.1016/j.compstruc.2026.108162)]
- [2026] **Three-dimensional magnetotelluric Bayesian inversion based on Stein variational gradient descent** [[paper](https://doi.org/10.5194/egusphere-egu26-8800)]
- [2026] **A Theoretical Framework for Hybrid Deterministic SIRS Modeling and Bayesian Hierarchical Inference in Burnout Propagation in Medical Education: Calibrated Simulations, Risk Factor Analysis, and Intervention Projections** *Open MIND* [[paper](https://doi.org/10.5281/zenodo.18927221)]
- [2026] **Bayesian inference for interfacial fracture energy variability in soft adhesive structures** *Engineering Fracture Mechanics* [[paper](https://doi.org/10.1016/j.engfracmech.2026.112032)]
- [2026] **A Provably-Correct Geometric-Bayesian Self-Healing Framework for Deep-Space Cyber-Physical Systems: Full SO(3) Attitude Dynamics, Multi-Physics Energy-Thermal Coupling, Lyapunov Stability, Geometric MPC, Sobol Sensitivity, and MCMC Inference -- Lessons from the Lunar Trailblazer Catastrophe (2025)** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.18883998)]
- [2026] **DE-BNN: An evolutionary approach to Bayesian neural network posterior sampling** *Neurocomputing* [[paper](https://doi.org/10.1016/j.neucom.2026.133103)]

[⬆ Back to top](#paper-list)

#### Application

##### 2026

- [2026] **Variational inference for the Bingham mixture model and applications** *Pattern Recognition* [[paper](https://doi.org/10.1016/j.patcog.2026.114560)]

[⬆ Back to top](#paper-list)

#### Development

##### 2026

- [2026] **Robust Surrogate-Based Bayesian Inference via Sampling-Based Adaptive Active Learning (SALE)** [[paper](https://arxiv.org/abs/2608.00841)]
- [2026] **LazyHMC: Hamiltonian Monte Carlo Simulation for Lazy, Infinite Dimensional Probabilistic Programs** [[paper](https://arxiv.org/abs/2608.08588)]
- [2026] **Hierarchical Bayesian Calibration with Bayesian Committee Machine** [[paper](https://arxiv.org/abs/2608.12603)]
- [2026] **Bayesian Modeling of Gibbs Point Processes via Basis Function Expansions** [[paper](https://arxiv.org/abs/2608.12510)]
- [2026] **Predicting subjective rage and facial expressions in human driving: A Bayesian network approach with beta-distributed nodes** [[paper](https://arxiv.org/abs/2607.18030)]
- [2026] **On the Computation of Normalized Power Priors** [[paper](https://arxiv.org/abs/2607.05579)]
- [2026] **Mixing efficiency of trans-model Markov chain Monte Carlo algorithms with applications in Bayesian phylogenetics** [[paper](https://arxiv.org/abs/2607.07188)]
- [2026] **Maximum Likelihood and Bayesian Estimation for State-Space Models Using the Non-Gaussian Filter** [[paper](https://arxiv.org/abs/2607.27576)]
- [2026] **Marginal Data Augmentation for Efficient Bayesian Modeling of Counts and Rates with a Demographic Application** [[paper](https://arxiv.org/abs/2607.24055)]
- [2026] **Geometry-Consistent Bayesian Filtering under Structural Model Uncertainty: A Geometric Projection Particle Filter** [[paper](https://arxiv.org/abs/2607.17781)]
- [2026] **DCEDesignSA: A MATLAB-based Graphical User Interface for Discrete Choice Experiment Design Using Simulated Annealing** [[paper](https://arxiv.org/abs/2607.04066)]
- [2026] **smoothbp: Fast Bayesian Hierarchical Piecewise Regression with Smoothed Transitions and Spike-and-Slab Model Selection** [[paper](https://arxiv.org/abs/2606.19044)]
- [2026] **The CRISTAL Method: Neurosymbolic analysis from AI-synthesized world models** [[paper](https://arxiv.org/abs/2606.29799)]
- [2026] **ShrinkageTrees: An R Package for Bayesian Tree Ensembles for Survival Analysis and Causal Inference** [[paper](https://arxiv.org/abs/2606.12317)]
- [2026] **Reactive Graphs for Efficient Markov Chain Monte Carlo Inference in Probabilistic Programming Languages** [[paper](https://arxiv.org/abs/2606.30137)]
- [2026] **Making Recursive Bayesian Inference Robust** [[paper](https://arxiv.org/abs/2606.07981)]
- [2026] **Logistic Gaussian process density regression: a generalized Bayesian approach** [[paper](https://arxiv.org/abs/2606.22915)]
- [2026] **Learning the distance for ABC and localized neural posterior estimation** [[paper](https://arxiv.org/abs/2606.22981)]
- [2026] **Inverse Probability Weighting in a Post-Bayesian World** [[paper](https://arxiv.org/abs/2606.28685)]
- [2026] **Forecasting with Bayesian Panel Vector Autoregressions Using the R Package bpvars** [[paper](https://arxiv.org/abs/2606.14143)]
- [2026] **Dynestyx: A Probabilistic Programming Library for Dynamical Systems** [[paper](https://arxiv.org/abs/2606.16985)]
- [2026] **Constrained Weighted Bayesian Bootstrap** [[paper](https://arxiv.org/abs/2606.04237)]
- [2026] **Calibration, Not Compilation: Detecting and Repairing Misspecified Probabilistic Programs Written by Language Models** [[paper](https://arxiv.org/abs/2606.31630)]
- [2026] **Bayesian learning for the stochastic shortest path problem** [[paper](https://arxiv.org/abs/2606.04845)]
- [2026] **Bayesian Variable Selection in Generalized Linear Models** [[paper](https://arxiv.org/abs/2606.24357)]
- [2026] **gemlib.mcmc: composable kernels for Metropolis-within-Gibbs sampling schemes** [[paper](https://arxiv.org/abs/2605.10914)]
- [2026] **Variational predictive resampling** [[paper](https://arxiv.org/abs/2605.11168)]
- [2026] **Trans-dimensional Bayesian model averaging for ^{13}C-based metabolic flux analysis: Evidence-based flux inference under structural model uncertainty** [[paper](https://arxiv.org/abs/2605.25079)]
- [2026] **To discretize continually: Mean shift interacting particle systems for Bayesian inference** [[paper](https://arxiv.org/abs/2605.14142)]
- [2026] **The Pearson IV distribution: Random variate generation and applications** [[paper](https://arxiv.org/abs/2605.01586)]
- [2026] **SIKA-GP: Accelerating Gaussian Process Inference with Sparse Inducing Kernel Approximations for Bayesian Deep Learning** [[paper](https://arxiv.org/abs/2605.26509)]
- [2026] **Particle filtering methods for partially observed branching processes** [[paper](https://arxiv.org/abs/2605.20987)]
- [2026] **Parameter Estimation for Partially Observed Time-Changed SDEs** [[paper](https://arxiv.org/abs/2605.09880)]
- [2026] **Fast Computation of Conditional Probabilities in MDPs and Markov Chain Families** [[paper](https://arxiv.org/abs/2605.11897)]
- [2026] **Bayesian perspectives on exponential random graph models** [[paper](https://arxiv.org/abs/2605.25873)]
- [2026] **BEND: An R Package for the Bayesian Estimation of Nonlinear Longitudinal Data** [[paper](https://arxiv.org/abs/2605.31341)]
- [2026] **Amortized Variational Inference for Joint Posterior and Predictive Distributions in Bayesian Uncertainty Quantification** [[paper](https://arxiv.org/abs/2605.03710)]
- [2026] **AI4BayesCode: From Natural Language Descriptions to Validated Modular Stateful Bayesian Samplers** [[paper](https://arxiv.org/abs/2605.18476)]
- [2026] **A computationally-tractable measure of global sensitivity for sampling-based Bayesian inference** [[paper](https://arxiv.org/abs/2605.28099)]
- [2026] **A Bayesian Approach to Membership Inference for Statistical Release** [[paper](https://arxiv.org/abs/2605.30203)]
- [2026] **Theoretical guarantees for stochastic gradient sampling methods via Gaussian convolution inequalities** [[paper](https://arxiv.org/abs/2604.24632)]
- [2026] **State estimations and noise identifications with intermittent corrupted observations via Bayesian variational inference** [[paper](https://arxiv.org/abs/2604.02738)]
- [2026] **Safe, Scalable, and Accurate Bayes Posterior Sampling for Large-Data Generalized Linear Mixed Models** [[paper](https://arxiv.org/abs/2604.26029)]
- [2026] **Multirate Stein Variational Gradient Descent for Efficient Bayesian Sampling** [[paper](https://arxiv.org/abs/2604.03981)]
- [2026] **Mean--Variance Risk-Aware Bayesian Optimal Experimental Design for Nonlinear Models** [[paper](https://arxiv.org/abs/2604.04315)]
- [2026] **Implementation and Workflows for INLA-Based Approximate Bayesian Structural Equation Modelling** [[paper](https://arxiv.org/abs/2604.00671)]
- [2026] **Efficient Bayes Factor Sensitivity Analysis via Posterior Density Ratios** [[paper](https://arxiv.org/abs/2604.21596)]
- [2026] **A new wavelet-based variational family with copula dependence structures** [[paper](https://arxiv.org/abs/2604.02116)]
- [2026] **Sequential Bayesian Experimental Design for Prediction in Physical Experiments Informed by Computer Models** [[paper](https://arxiv.org/abs/2603.16756)]
- [2026] **Sampling through iterated approximation: Gradient-free and multi-fidelity Bayesian inference via transport** [[paper](https://arxiv.org/abs/2603.12448)]
- [2026] **Likelihood hacking in probabilistic program synthesis** [[paper](https://arxiv.org/abs/2603.24126)]
- [2026] **GPU-Accelerated Sequential Monte Carlo for Bayesian Spectral Analysis** [[paper](https://arxiv.org/abs/2604.03271)]
- [2026] **Bayesian structured additive quantile regression for inflated bounded data** [[paper](https://arxiv.org/abs/2603.03987)]
- [2026] **A practical introduction to ODE modelling in Stan for biological systems** [[paper](https://arxiv.org/abs/2603.20343)]
- [2026] **A Probabilistic Generative Model for Spectral Speech Enhancement** [[paper](https://arxiv.org/abs/2603.28436)]
- [2026] **bayesics: Core Statistical Methods via Bayesian Inference in R** [[paper](https://arxiv.org/abs/2602.15150)]
- [2026] **Posterior Uncertainty for Targeted Parameters in Bayesian Bootstrap Procedures** [[paper](https://arxiv.org/abs/2602.02216)]
- [2026] **Nested Sampling with Slice-within-Gibbs: Efficient Evidence Calculation for Hierarchical Bayesian Models** [[paper](https://arxiv.org/abs/2602.17414)]
- [2026] **Multiproposal Elliptical Slice Sampling** [[paper](https://arxiv.org/abs/2602.22358)]
- [2026] **A note on the area under the likelihood and the fake evidence for model selection** [[paper](https://arxiv.org/abs/2602.22965)]
- [2026] **SunBURST: Deterministic GPU-Accelerated Bayesian Evidence via Mode-Centric Laplace Integration** [[paper](https://arxiv.org/abs/2601.19957)]
- [2026] **Neural-Inspired Posterior Approximation (NIPA)** [[paper](https://arxiv.org/abs/2601.22539)]
- [2026] **Censored Graphical Horseshoe: Bayesian sparse precision matrix estimation with censored and missing data** [[paper](https://arxiv.org/abs/2601.06671)] [[code](https://github.com/tienmt/ghscenmis)]
- [2026] **A Framework for the Bayesian Calibration of Complex and Data-Scarce Models in Applied Sciences** [[paper](https://arxiv.org/abs/2601.22890)]

##### 2025

- [2025] **Two Bayesian Approaches to Dynamic Gaussian Bayesian Networks with Intra- and Inter-Slice Edges** [[paper](https://arxiv.org/abs/2512.14512)]
- [2025] **StochTree: BART-based modeling in R and Python** [[paper](https://arxiv.org/abs/2512.12051)]
- [2025] **On a class of constrained Bayesian filters and their numerical implementation in high-dimensional state-space Markov models** [[paper](https://arxiv.org/abs/2512.11012)]
- [2025] **Exact two-stage finite-mixture representations for species sampling processes** [[paper](https://arxiv.org/abs/2512.24414)]
- [2025] **Divergence-based Robust Generalised Bayesian Inference for Directional Data via von Mises-Fisher models** [[paper](https://arxiv.org/abs/2512.05668)]
- [2025] **Detecting Model Misspecification in Bayesian Inverse Problems via Variational Gradient Descent** [[paper](https://arxiv.org/abs/2512.01667)]
- [2025] **Bayesian inference for functional extreme events defined via partially unobserved processes** [[paper](https://arxiv.org/abs/2512.24356)]
- [2025] **On a Reinforcement Learning Methodology for Epidemic Control, with application to COVID-19** [[paper](https://arxiv.org/abs/2511.18035)]
- [2025] **Modified Delayed Acceptance MCMC for Quasi-Bayesian Inference with Linear Moment Conditions** [[paper](https://arxiv.org/abs/2511.17117)]
- [2025] **Bayesian copula-based spatial random effects models for inference with complex spatial data** [[paper](https://arxiv.org/abs/2511.02551)]
- [2025] **Approximate Bayesian Computation Made Easy: A Practical Guide to ABC-SMC for Dynamical Systems with \texttt{pymc}** [[paper](https://arxiv.org/abs/2511.21587)] [[code](https://github.com/mariocastro73/ABCSMC_pymc_by_example)]
- [2025] **An Infinite BART model** [[paper](https://arxiv.org/abs/2511.20087)]
- [2025] **A BGe score for tied-covariance mixtures of Gaussian Bayesian networks** [[paper](https://arxiv.org/abs/2511.07050)]
- [2025] **The Interplay between Bayesian Inference and Conformal Prediction** [[paper](https://arxiv.org/abs/2510.26930)]
- [2025] **TabMGP: Martingale Posterior with TabPFN** *ICML 2026. Extra plots in https* [[paper](https://arxiv.org/abs/2510.25154)]
- [2025] **Phantom types for robust hierarchical models with typegeist** [[paper](https://arxiv.org/abs/2510.26726)]
- [2025] **Model Falsification for Predicting Dynamical Responses of Uncertain Structural Systems** [[paper](https://arxiv.org/abs/2510.02612)]
- [2025] **Fast Bayesian Multilevel Quasi-Monte Carlo** [[paper](https://arxiv.org/abs/2510.24604)]
- [2025] **Expectation-Propagation for Bayesian Empirical Likelihood Inference** [[paper](https://arxiv.org/abs/2510.21174)]
- [2025] **Efficient Prior Sensitivity and Tipping-point Analysis for Medical Research: Revisiting Sampling Importance Resampling** [[paper](https://arxiv.org/abs/2510.10034)]
- [2025] **Compressed Bayesian Tensor Regression** [[paper](https://arxiv.org/abs/2510.01861)]
- [2025] **Bayesian Transfer Learning for High-Dimensional Linear Regression via Adaptive Shrinkage** [[paper](https://arxiv.org/abs/2510.03449)]
- [2025] **Bayesian Optimization on Networks** [[paper](https://arxiv.org/abs/2510.27643)]
- [2025] **A fast non-reversible sampler for Bayesian finite mixture models** [[paper](https://arxiv.org/abs/2510.03226)]
- [2025] **nsEVDx: A Python library for modeling Non-Stationary Extreme Value Distributions** [[paper](https://arxiv.org/abs/2509.07261)]
- [2025] **Stochastic Path Planning in Correlated Obstacle Fields** [[paper](https://arxiv.org/abs/2509.19559)]
- [2025] **Simulation-based Inference via Langevin Dynamics with Score Matching** [[paper](https://arxiv.org/abs/2509.03853)]
- [2025] **Sampling as Bandits: Evaluation-Efficient Design for Black-Box Densities** [[paper](https://arxiv.org/abs/2509.01437)]
- [2025] **Robust Survival Estimation under Interval Censoring: Expectation-Maximization and Bayesian Accelerated Failure Time Assessment via Simulation and Application** [[paper](https://arxiv.org/abs/2509.02634)]
- [2025] **Recursive Adaptive Importance Sampling with Optimal Replenishment** [[paper](https://arxiv.org/abs/2509.08102)]
- [2025] **Preconditioned Regularized Wasserstein Proximal Sampling** [[paper](https://arxiv.org/abs/2509.01685)]
- [2025] **Nonparametric Bayesian Calibration of Computer Models** [[paper](https://arxiv.org/abs/2509.22597)]
- [2025] **Meta-Analysis with JASP, Part II: Bayesian Approaches** [[paper](https://arxiv.org/abs/2509.09850)]
- [2025] **Generalized Bayesian Inference for Dynamic Random Dot Product Graphs** [[paper](https://arxiv.org/abs/2509.19748)]
- [2025] **Covariance-Corrected WAIC for Bayesian Sequential Data Models** [[paper](https://arxiv.org/abs/2509.17980)]
- [2025] **Bayesian model updating via streamlined Bayesian active learning cubature** [[paper](https://arxiv.org/abs/2509.11204)]
- [2025] **A Bayesian thinning algorithm for the point source identification of heat equation** [[paper](https://arxiv.org/abs/2509.14245)]
- [2025] **Generalized promotion time cure model: A new modeling framework to identify cell-type-specific genes and improve survival prognosis** [[paper](https://arxiv.org/abs/2509.01001)]
- [2025] **A nonstationary spatial model of PM2.5 with localized transfer learning from numerical model output** [[paper](https://arxiv.org/abs/2508.15978)]

[⬆ Back to top](#paper-list)

### Prior Specification & Elicitation

#### Method

##### 2026

- [2026] **estimateW: a Bayesian R package for estimating spatial weight matrices, with an application to European regional growth** *Empirica* [[paper](https://doi.org/10.1007/s10663-026-09697-z)]
- [2026] **Rationale and guidance for implementing the continual reassessment method for dose-finding in controlled human infection model studies** *medRxiv* [[paper](https://doi.org/10.64898/2026.07.16.26358128)]
- [2026] **CWWhitney/ev_ambiguity: v0.4.0 adds three analytical functions** *Open MIND* [[paper](https://github.com/CWWhitney/ev_ambiguity/tree/v0.1.2-alpha)]
- [2026] **Statistical methods for the forensic examination of handwriting and dynamic signatures data** *Athens University of Economics & Business* [[paper](https://doi.org/10.26219/heal.aueb.10280)]

[⬆ Back to top](#paper-list)

#### Theory

##### 2026

- [2026] **Posterior Ramifications of Prior Dependence Structures** *Statistical Science* [[paper](https://arxiv.org/abs/2312.06437)]
- [2026] **On the Interplay Between Prior Weight and Variance of the Robustification Component in Robust Mixture Prior Bayesian Dynamic Borrowing Approach** *Statistics in Medicine* [[paper](https://arxiv.org/abs/2509.01435)]
- [2026] **Elicitation Matters: How Prompts and Query Protocols Shape LLM Surrogates under Sparse Observations** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2605.04764)]
- [2026] **Exact Bayesian Planning for Simple Step-Stress Accelerated Life Testing with Competing Risks** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2604.09259)]
- [2026] **PREreview of "RAPTOR-GEN: RApid PosTeriOR GENerator for Bayesian Learning in Biomanufacturing"** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.18741398)]
- [2026] **PREreview of "Interpretable Biomanufacturing Process Risk and Sensitivity Analyses for Quality-by-Design and Stability Control"** *Open MIND* [[paper](https://prereview.org/reviews/18770706)]

[⬆ Back to top](#paper-list)

### Model Selection & Averaging

#### Method

##### 2026

- [2026] **Structured Dimension-Matched Joint Variational Transdimensional Inference** [[paper](https://arxiv.org/abs/2608.05607)]
- [2026] **Bayesian Inference Procedures for A/B Testing: An Overview** [[paper](https://arxiv.org/abs/2608.12949)]
- [2026] **Longitudinal patterns of kidney function in children with HIV: insights from group-based trajectory modeling** *AIDS* [[paper](https://doi.org/10.1097/qad.0000000000004592)]
- [2026] **Simulation-Free Bayesian Power and Sample Size Calculations for Bayes Factors in Single-Arm Phase II Trials with Binary Endpoints** [[paper](https://arxiv.org/abs/2607.24084)]
- [2026] **Is S301 the Captured Companion of the Hypervelocity Star S5-HVS1?** [[paper](https://arxiv.org/abs/2607.22517)]
- [2026] **Extracting Bayesian Evidence from Frequentist p-Values** [[paper](https://arxiv.org/abs/2607.12132)]
- [2026] **Comparative Periodogram Analysis of 22 Years of Super-Kamiokande Solar ^{8}B Neutrino Data: Classical, Phase-Based, and Information Theoretic Methods** [[paper](https://arxiv.org/abs/2607.27979)]
- [2026] **Bounds on Intrinsic Bayes Factors and Least Favorable Intrinsic Priors for General Statistical Hypothesis Testing** [[paper](https://arxiv.org/abs/2607.10035)]
- [2026] **Black hole spin-mass correlation and vector resonant relaxation in gaseous star clusters: the origin of GW231123?** [[paper](https://arxiv.org/abs/2607.17869)]
- [2026] **A population of LIGO-Virgo-KAGRA mergers happening inside active galactic nuclei** [[paper](https://arxiv.org/abs/2607.03674)]
- [2026] **Cosmological Validation of the UAT/UCP Framework without Boltzmann Codes: Om(z) Diagnostic, Cosmic Chronometers, and Bayesian Model Selection** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.21504719)]
- [2026] **Influence Diagnostics for Bayesian Spatial Econometrics** *Monash University* [[paper](https://doi.org/10.26180/32930648)]
- [2026] **A Bayesian Multi-Model Inference Method for Reliability Analysis Considering Vine Structure Uncertainty Under Limited Data** *Applied Sciences* [[paper](https://doi.org/10.3390/app16157624)]
- [2026] **Light Dark Matter Discovery Potential and Model Selection at LDMX** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2607.24524)]
- [2026] **Reclaiming the "frequentist" role of marginal likelihood in Bayesian belief revision** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2607.26259)]
- [2026] **Reversible jumps for the joint modeling of the dimension of pseudo-functional models in chromosomal windows in genome-wide selection** *BMC Genomics* [[paper](https://doi.org/10.1186/s12864-026-13073-3)]
- [2026] **rsx: A high-performance streaming toolkit for RAD-seq sex determination** [[paper](https://arxiv.org/abs/2606.06434)]
- [2026] **Two fully specified Bayes factors for hypothesis testing and sensitivity analysis in process tracing** [[paper](https://arxiv.org/abs/2606.16683)]
- [2026] **The NANOGrav 15 yr Data Set: Impacts of Customized Chromatic Noise Models on Gravitational Wave Analyses** [[paper](https://arxiv.org/abs/2606.28554)]
- [2026] **Optimal sequential two-stage Bayes Factor Design for two-arm clinical Phase II Trials with binary Endpoints** [[paper](https://arxiv.org/abs/2606.02410)]
- [2026] **Modeling semantic association in self-paced reading with language model embeddings** [[paper](https://arxiv.org/abs/2606.07066)]
- [2026] **Memory Retrieval for Changing Preferences** [[paper](https://arxiv.org/abs/2606.02976)]
- [2026] **From Evidence to Evident: Decisive Cosmological Evidence for the Normal Neutrino Mass Hierarchy** [[paper](https://arxiv.org/abs/2606.18987)]
- [2026] **An Ultramassive White Dwarf with a Likely Oxygen-Neon Core** [[paper](https://arxiv.org/abs/2606.19441)]
- [2026] **Temporal dynamics of Chilean dolphins: How environmental variables modulate occupancy and group size patterns in an estuarine environment** [[paper](https://doi.org/10.22541/authorea.15004517/v1)]
- [2026] **Machine Learning Methods to Predict the Length of Stay for Acute Stroke: A Scoping Review and Meta‐Analysis** *Health care science* [[paper](https://doi.org/10.1002/hcs2.70083)]
- [2026] **Cross-Continental Analysis of Vampire Bat Betaherpesvirus Reveals Limited Interference Among Strains and Local Geographic Spread** *Figshare* [[paper](https://figshare.com/articles/dataset/Cross-Continental_Analysis_of_Vampire_Bat_Betaherpesvirus_Reveals_Limited_Interference_Among_Strains_and_Local_Geographic_Spread/32569182)]
- [2026] **On the Presence of a Tertiary Compact Object in GW190814** [[paper](https://arxiv.org/abs/2605.21955)]
- [2026] **Modeling the probability distribution for cosmological analysis with photometrically classified samples** [[paper](https://arxiv.org/abs/2605.16513)]
- [2026] **Instruction Adherence in Coding Agent Configuration Files: A Factorial Study of Four File-Structure Variables** [[paper](https://arxiv.org/abs/2605.10039)]
- [2026] **Guiding Multi-Objective Genetic Programming with Description Length Improves Symbolic Regression Solutions** [[paper](https://arxiv.org/abs/2605.22374)]
- [2026] **Gravitational Wave Hyperbolic Catalog: Reanalyzing High-Mass Gravitational Wave Signals Using Hyperbolic Waveforms** [[paper](https://arxiv.org/abs/2605.21640)]
- [2026] **Constraining Gravitational Wave Memory with Hierarchical Inference** [[paper](https://arxiv.org/abs/2605.27500)]
- [2026] **Bayesian Modeling of NICER Cometary X-ray Spectra: A Legacy Survey of Solar-Wind Charge Exchange** [[paper](https://arxiv.org/abs/2605.21684)]
- [2026] **BB plot: A Tool for Accurate Model Selection Using Bayes factors** [[paper](https://arxiv.org/abs/2605.10333)]
- [2026] **Bayesian Model Averaging in Causal Instrumental Variable Models** *Journal of Applied Econometrics* [[paper](https://doi.org/10.1002/jae.70070)]
- [2026] **Bayesian Model Averaging in Causal Instrumental Variable Models (Replication Data)** *Open MIND* [[paper](https://journaldata.zbw.eu/dataset/342909cd-8232-4da0-9bc3-afa3886f9cce/resource/89c37efb-48b7-4709-9396-70dcbcc76a3f/download/readme.ss.txt)]
- [2026] **Stellar separation shapes spin-orbit alignment in visual binaries** [[paper](https://arxiv.org/abs/2604.18921)]
- [2026] **Bayesian Geometrical Modeling of IXPE Polarization Angle Curves of the Magnetars 1E 2259+586 and 1E 1547.0-5408** [[paper](https://arxiv.org/abs/2604.10477)]
- [2026] **Bayesian Analysis of Gravitational Wave Microlensing Effects from Galactic Double White Dwarfs** [[paper](https://arxiv.org/abs/2604.13930)]
- [2026] **Basilic: An end-to-end pipeline for Bayesian burst inference and model classification in gravitational-wave data** [[paper](https://arxiv.org/abs/2604.13839)]
- [2026] **Agnostically decoding gravitational wave model deficiencies in GWTC-3** [[paper](https://arxiv.org/abs/2604.27185)]
- [2026] **A Bayes-Factor-Guided Approach to Post-Double Selection with Bootstrapped Multiple Imputation** [[paper](https://arxiv.org/abs/2604.12783)]
- [2026] **Bayesian Methods for Spatio-temporal Individual-level Epidemic Models: Composite Methods, Behavioural Change and Model Choice** *Open MIND* [[paper](https://hdl.handle.net/1880/124640)]
- [2026] **A multi-stage data- and knowledge-coupled decision support framework for sustainable CCUS project site selection** *Sustainable Energy Technologies and Assessments* [[paper](https://doi.org/10.1016/j.seta.2026.104970)]
- [2026] **Topologically quantized macroscopic attractor states in hydrated DNA** [[paper](https://arxiv.org/abs/2603.26847)]
- [2026] **Testing for Endogeneity: A Moment-Based Bayesian Approach** [[paper](https://arxiv.org/abs/2603.07780)]
- [2026] **Power and Sample Size Calculations for Bayes Factors in two-arm clinical Phase II Trials with binary Endpoints** [[paper](https://arxiv.org/abs/2603.01715)]
- [2026] **Multi-dimensional Mortality (MDMx): Sex-Age-Specific Model Life Tables, Fitting, Prediction from Summary Mortality Indicators, and Forecasting** [[paper](https://arxiv.org/abs/2603.20518)]
- [2026] **E-values as statistical evidence: A comparison to Bayes factors, likelihoods, and p-values** [[paper](https://arxiv.org/abs/2603.24421)]
- [2026] **Context Tree Prior Distributions based on Node Weighting with exact Bayes Factors** [[paper](https://arxiv.org/abs/2603.25806)]
- [2026] **Conditional Neural Bayes Ratio Estimation for Experimental Design Optimisation** [[paper](https://arxiv.org/abs/2603.26489)]
- [2026] **Bayesian Model Comparison of R_h=ct versus ΛCDM using HII galaxy Hubble diagram** [[paper](https://arxiv.org/abs/2603.28019)]
- [2026] **Breaking the Winner's Curse with Bayesian Hybrid Shrinkage** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2603.12867)]
- [2026] **Principled Default Priors for Bayesian Hypothesis Testing in Binomial GLMs: A Matched-Prior Framework with Empirical Evaluation** [[paper](https://doi.org/10.31234/osf.io/q7byw_v1)]
- [2026] **Core Distinguishability Relativity (CDR): A Relative-Entropy Reweighting Framework for Testing Information-Driven Selection in Markov Kernels** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.18841328)]
- [2026] **When Is Generalized Bayes Bayesian? A Decision-Theoretic Characterization of Loss-Based Updating** [[paper](https://arxiv.org/abs/2602.01573)]
- [2026] **Testing the wormhole echo hypothesis for GW231123** [[paper](https://arxiv.org/abs/2602.01615)]
- [2026] **Testing black hole space-times with the S2 star orbit: a Bayesian comparison** [[paper](https://arxiv.org/abs/2602.04980)]
- [2026] **Optimality of the Half-Order Exponent in the Turing-Good Identities for Bayes Factors** [[paper](https://arxiv.org/abs/2602.19838)]
- [2026] **Inspiral tests of general relativity and waveform geometry** [[paper](https://arxiv.org/abs/2602.17524)]
- [2026] **Addressing Heterogeneity with Bayesian Meta-Analytic Mixture Modelling** [[paper](https://doi.org/10.31234/osf.io/nkyqm_v1)]
- [2026] **Flux-ratio anomalies in cusp quasars reveal dark matter beyond CDM** [[paper](https://arxiv.org/abs/2601.16818)]
- [2026] **Evidence Slopes and Effective Dimension in Singular Linear Models** [[paper](https://arxiv.org/abs/2601.01238)]
- [2026] **Bayes Factor Group Sequential Designs** [[paper](https://arxiv.org/abs/2601.02851)]
- [2026] **A nonlinear voice from GW250114 ringdown** [[paper](https://arxiv.org/abs/2601.05734)]
- [2026] **A Modified Bayesian Criterion for Model Selection in Mixed and Hierarchical Frameworks** [[paper](https://arxiv.org/abs/2601.01190)]

##### 2025

- [2025] **Search for Annual Modulation in Combined ANAIS 112 and COSINE 100 Data using Bayesian Model Comparison** [[paper](https://arxiv.org/abs/2512.23191)]
- [2025] **Observational constraints on early time non-phantom behaviour of dynamical dark energy** [[paper](https://arxiv.org/abs/2512.19888)]
- [2025] **Improved Identification of Strongly Lensed Gravitational Waves with Host Galaxy Locations** [[paper](https://arxiv.org/abs/2512.10344)]
- [2025] **Data-driven inverse uncertainty quantification: application to the Chemical Vapor Deposition Reactor Modeling** [[paper](https://arxiv.org/abs/2512.13354)]
- [2025] **Bayesian Model Selection with an Application to Cosmology** [[paper](https://arxiv.org/abs/2512.09724)]
- [2025] **Applying the BF method on the DESI evidence for dynamical dark energy models** [[paper](https://arxiv.org/abs/2512.10763)]
- [2025] **A Primer on Bayesian Parameter Estimation and Model Selection for Battery Simulators** [[paper](https://arxiv.org/abs/2512.10055)]
- [2025] **A Bayes-Motivated Quadratic-Form Test for High-Dimensional Mean Testing** [[paper](https://arxiv.org/abs/2512.10537)]
- [2025] **The NANOGrav 12.5-year Data Set: Chromatic Noise Characterization &amp; Mitigation with Time-Domain Kernels** [[paper](https://arxiv.org/abs/2511.22597)]
- [2025] **The Bayes Factor Reversal Paradox** [[paper](https://arxiv.org/abs/2511.22152)]
- [2025] **Statistical Indications of Toponium Formation in Top Quark Pair Production** [[paper](https://arxiv.org/abs/2511.02040)]
- [2025] **Methane on the temperate exo-Saturn TOI-199b** [[paper](https://arxiv.org/abs/2511.15835)]
- [2025] **Kepler-1624b Has No Significant Transit Timing Variations** [[paper](https://arxiv.org/abs/2511.17709)]
- [2025] **Improved Bounds for Context-Dependent Evolutionary Models Using Sequential Monte Carlo** [[paper](https://arxiv.org/abs/2511.07736)]
- [2025] **CP Prediction from Residual \mathbb Z_2^s and \overline{\mathbb Z}_2^s Symmetries with JUNO First Data** [[paper](https://arxiv.org/abs/2511.15442)]
- [2025] **Bayes Factor Hypothesis Testing in Meta-Analyses: Practical Advantages and Methodological Considerations** [[paper](https://arxiv.org/abs/2511.22535)]
- [2025] **Validating Open Cluster Candidates with Photometric Bayesian Evidence** [[paper](https://arxiv.org/abs/2510.23375)]
- [2025] **Strong gravitational-wave lensing posterior odds** [[paper](https://arxiv.org/abs/2510.15463)]
- [2025] **Scalar fields around black hole binaries in LIGO-Virgo-KAGRA** [[paper](https://arxiv.org/abs/2510.17967)]
- [2025] **Non-Minimally Coupled Quintessence in Light of DESI** [[paper](https://arxiv.org/abs/2510.14941)]
- [2025] **Learning constitutive models and rheology from partial flow measurements** [[paper](https://arxiv.org/abs/2510.24673)]
- [2025] **J-PAS: forecast on the primordial power spectrum reconstruction** [[paper](https://arxiv.org/abs/2510.18595)]
- [2025] **Generalized Jeffreys's approximate objective Bayes factor: Model-selection consistency, finite-sample accuracy, and statistical evidence in 71,126 clinical trial findings** [[paper](https://arxiv.org/abs/2510.10358)]
- [2025] **Discriminating Between Models of the Nanohertz Gravitational-Wave Background with Pulsar Timing Arrays** [[paper](https://arxiv.org/abs/2510.22713)]
- [2025] **Contribution from Nonlinear Quasi-normal Modes in GW250114** [[paper](https://arxiv.org/abs/2510.16903)]
- [2025] **Approximating evidence via bounded harmonic means** [[paper](https://arxiv.org/abs/2510.20617)]
- [2025] **Precision measurement of neutrino oscillation parameters with 10 years of data from the NOvA experiment** [[paper](https://arxiv.org/abs/2509.04361)]
- [2025] **Is GW190521 a gravitational wave echo of wormhole remnant from another universe?** [[paper](https://arxiv.org/abs/2509.07831)]
- [2025] **High-Dimensional Bayesian Model Comparison in Cosmology with GPU-accelerated Nested Sampling and Neural Emulators** [[paper](https://arxiv.org/abs/2509.13307)]
- [2025] **First Overtone Mode in the Ringdown Signal of GW231028** [[paper](https://arxiv.org/abs/2509.08657)]
- [2025] **Dynamic or Systematic? Bayesian model selection between dark energy and supernova biases** [[paper](https://arxiv.org/abs/2509.13220)]
- [2025] **Cosmological constraints on Galileon dark energy with broken shift symmetry** [[paper](https://arxiv.org/abs/2509.17586)]
- [2025] **CosmoGen: A genetic algorithm framework for the exploration of dark energy dynamics** [[paper](https://arxiv.org/abs/2509.15453)]
- [2025] **Bayesian Model Comparison and Significance: Widespread Errors and how to Correct Them** [[paper](https://arxiv.org/abs/2510.00169)]
- [2025] **Aligned Hierarchical Black Hole Mergers in Active-Galactic-Nuclei Disks Revealed by GWTC-4** [[paper](https://arxiv.org/abs/2509.23897)]
- [2025] **A dense dark matter core of the subhalo in the strong lensing system JVAS B1938+666** [[paper](https://arxiv.org/abs/2509.07808)]
- [2025] **A Unified Probabilistic Framework for Dictionary Learning with Parsimonious Activation** [[paper](https://arxiv.org/abs/2509.25690)]
- [2025] **Using gravitational wave dark sirens to choose between host galaxy weighting models** [[paper](https://arxiv.org/abs/2508.15574)]
- [2025] **The NANOGrav 15 yr Data Set: Targeted Searches for Supermassive Black Hole Binaries** [[paper](https://arxiv.org/abs/2508.16534)]
- [2025] **Comment on García-Donato et al. (2025) "Model uncertainty and missing data: An objective Bayesian perspective"** [[paper](https://arxiv.org/abs/2508.19939)]
- [2025] **A Multimessenger Search for the Supermassive Black Hole Binary in 3C 66B with the Parkes Pulsar Timing Array** [[paper](https://arxiv.org/abs/2508.20007)]

[⬆ Back to top](#paper-list)

#### Theory

##### 2026

- [2026] **BayesSplineUR: Bayesian Unit Root Test for AR(1) Model with Trend Approximated by Linear Spline Function** [[paper](https://doi.org/10.32614/cran.package.bayessplineur)]
- [2026] **Robust Functional-Input Hypothesis Testing and Multi-Task Regression on Mixed-Type Graphs for High-Dimensional, Complex-Structured Data** *VTechWorks (Virginia Tech)* [[paper](https://hdl.handle.net/10919/143706)]
- [2026] **Growth of Cosmic Structure in the UAT Framework: Bayesian Model Selection, Parameter Sweep, and the Decisive Preference for Predictive Rigidity over Parametric Freedom** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.21367301)]
- [2026] **Bayesian Evidence Profiles in Aetherium Cosmology V1** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.21176062)]
- [2026] **Path-length dependence of parton energy loss across collision systems: a Bayesian analysis of charged-particle RAA, consistent with a universal exponent from O+O to Pb+Pb** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2607.25727)]
- [2026] **The UAT/UCP Universe: A Complete Cosmological Description with a Single Free Parameter — Methodology, Audit, and Comparison with ΛCDM** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.21433731)]
- [2026] **Experimental Tests of the Black Hole Entropy Prediction of the Order Parameter Spacetime Theory — Gravitational Wave and Black Hole Shadow Observations** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.21554501)]
- [2026] **Primordial helium and effective neutrino species from CMB data: A Bayesian analysis of extended cosmological models** *Journal of High Energy Astrophysics* [[paper](https://doi.org/10.1016/j.jheap.2026.100673)]
- [2026] **Structural Gravitational Waves v1.2: Statistical Inference Framework** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.20994263)]
- [2026] **Convergent evolution of ST2 and ST164 mediates dissemination of the blaNDM-1/blaOXA-23 profile in Acinetobacter baumannii** *Annals of Clinical Microbiology and Antimicrobials* [[paper](https://doi.org/10.1186/s12941-026-00872-5)]
- [2026] **PIU-Ψ: The Principle of Universal Integrity — A Single Scalar Substrate from Which Gravity, Quantum Mechanics, and Cosmology Emerge (V4.8)** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.20719383)]
- [2026] **A Compressed Infrastructure Sequence in the History of Mathematical and Physical Thought: Evidence for Access-Mediated Synthesis at the Web Transition** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.20726503)]
- [2026] **A Domain-Agnostic Fractal-Correction-Engine Framework for Decomposing the Neutron Lifetime Discrepancy** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.20933231)]
- [2026] **Which predicts better with limited data? Comparing learning curve and Bayesian models for improved construction duration estimation** *International Journal of Construction Management* [[paper](https://doi.org/10.1080/15623599.2026.2669835)]
- [2026] **Auto-Encoding Variational Bayesian Inference in High-Dimensional Skew-Normal Linear Mixed Models** *Journal of Systems Science and Complexity* [[paper](https://doi.org/10.1007/s11424-026-5387-1)]
- [2026] **From Distinction to the Standard Model: An Algebraic Framework** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.20069952)]
- [2026] **The Time-Domain Lattice in EHT Visibilities: A Glass–Crystal Audit Across Sgr A and M87**** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19563372)]
- [2026] **IsadoreNabi/HTDV: HTDV package** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19839234)]
- [2026] **An example of identifying conditional dependence in graphical models using Bayesian model averaging: general and disease specific anxiety in a cardiovascular patient sample** *Journal of Behavioral Medicine* [[paper](https://doi.org/10.1007/s10865-026-00641-x)]
- [2026] **Random irregular histograms** *Computational Statistics & Data Analysis* [[paper](https://arxiv.org/abs/2505.22034)]
- [2026] **Evaluating the Bayes factor under model misspecification in repeated-measures designs** *Journal of Mathematical Psychology* [[paper](https://doi.org/10.1016/j.jmp.2026.102972)]
- [2026] **On Bayesian inference in pulsar timing arrays: identifiability and choice of the priors** *Research Square* [[paper](https://doi.org/10.21203/rs.3.rs-8351930/v1)]
- [2026] **CMB Axis of Evil Simulator: Recursive Attractor Field Theory for Large-Scale Cosmic Anomalies** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19059391)]
- [2026] **A robust analysis of QU-fitting behaviour for 800–1088 MHz and 1296–1440 MHz** *Monthly Notices of the Royal Astronomical Society* [[paper](https://arxiv.org/abs/2602.21739)]

[⬆ Back to top](#paper-list)

#### Application

##### 2026

- [2026] **Quantifying Evidential Rigor in Meta-Analytic Corpora: A Simulation-Characterized, Bias-Robust Bayesian Workflow with a Nutrition Case Study** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2606.01428)]
- [2026] **Evidential Audit Workflow (RoBMA-PSMA, RoBMA 4.0)** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.20467257)]

[⬆ Back to top](#paper-list)

#### Evaluation

##### 2026

- [2026] **Is the compact-object lower mass gap a threshold? A logistic-gate description, a Bayesian assessment with current events, and a discrimination forecast** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.20854768)]
- [2026] **Dark Energy Equation of State from the Critical Dimension of Parallelizable Spheres** *Open MIND* [[paper](https://doi.org/10.5281/zenodo.18703947)]

[⬆ Back to top](#paper-list)

### Hierarchical & Multilevel Models

#### Method

##### 2026

- [2026] **SpikeRestormer: Towards Energy-Efficient All-in-One Image Restoration via Unified Event Reasoning** [[paper](https://arxiv.org/abs/2608.02290)]
- [2026] **Soft-Noncrossing Bayesian Panel Quantile Regression for Measuring Climate Tail Risk** [[paper](https://arxiv.org/abs/2608.04664)]
- [2026] **Small Area Bayesian Dynamic Borrowing: Adaptive Subgroup Estimation for Large-Scale Educational Assessments** [[paper](https://arxiv.org/abs/2608.07708)]
- [2026] **Multi-Signal Safety Surveillance with Bayesian Latent Factor Modeling and Bias Correction** [[paper](https://arxiv.org/abs/2608.03775)]
- [2026] **Latent space models for networks with nodal multiplicative effects** [[paper](https://arxiv.org/abs/2608.06676)]
- [2026] **Hierarchical Spline-Based Bayesian Beta-Binomial Regression for Estimating Time-Varying Risk in Power Outages** [[paper](https://arxiv.org/abs/2608.12560)]
- [2026] **A Bayesian Weakest-Link Framework for Joint Estimation of Material Strength and Stress Profile** [[paper](https://arxiv.org/abs/2608.01261)]
- [2026] **Fake news detection via wisdom of synthetic and representative crowds** *Journal of the Royal Statistical Society Series A (Statistics in Society)* [[paper](https://doi.org/10.1093/jrsssa/qnag095)]
- [2026] **Sociodemographic and Clinical Predictors of Cognitive Performance in Lupus** *The Journal of Rheumatology* [[paper](https://doi.org/10.3899/jrheum.2026-0447.200)]
- [2026] **metasignal: A Python Package for Comprehensive Metacognitive Analysis and Decision-Making** [[paper](https://arxiv.org/abs/2607.29093)]
- [2026] **Using hierarchical statistical learning models to model individual statistical learning** [[paper](https://arxiv.org/abs/2607.05822)]
- [2026] **Tabular Foundation Models for Discrete Choice Estimation** [[paper](https://arxiv.org/abs/2607.13314)]
- [2026] **Population statistics of nanohertz gravitational wave sources** [[paper](https://arxiv.org/abs/2607.07477)]
- [2026] **Nuclear γ-Ray Cascades as Markov Processes** [[paper](https://arxiv.org/abs/2608.00176)]
- [2026] **No Evidence for Superradiant Axions in LIGO-Virgo-KAGRA GWTC-5 Binary Black Hole Spins** [[paper](https://arxiv.org/abs/2607.01317)]
- [2026] **Modeling Memory-Dependent Reliability of LLMs: A Hidden Markov Model** [[paper](https://arxiv.org/abs/2607.22951)]
- [2026] **Joint constraints on gravity and stellar orbital anisotropy in massive galaxies** [[paper](https://arxiv.org/abs/2607.06755)]
- [2026] **Fast Radio Bursts Trace Cosmic Star Formation with Little Delay** [[paper](https://arxiv.org/abs/2607.09109)]
- [2026] **Amortized low-rank approximation for hyperparameter marginalization in PDE-governed Bayesian inverse problems** [[paper](https://arxiv.org/abs/2607.03355)]
- [2026] **Multilevel structured additive regression modelling of the determinants of childhood malnutrition in Nigeria** *Discover Public Health* [[paper](https://doi.org/10.1186/s12982-026-02457-1)]
- [2026] **Prediction-guided hierarchical clustering for population-level regression** *International Journal of Data Science and Analytics* [[paper](https://doi.org/10.1007/s41060-026-01197-4)]
- [2026] **The Dynamic Hierarchy of Personal Space Regulation and its Modulation by Childhood Traumatic Experiences** [[paper](https://doi.org/10.31234/osf.io/p9qak_v1)]
- [2026] **Stroke burden and associated predictors in Ghana: a Bayesian analysis of the WHO study on global ageing and adult health** *Aging Clinical and Experimental Research* [[paper](https://doi.org/10.1007/s40520-026-03462-9)]
- [2026] **Neural Conjugate Aggregation: Identifiable Unsupervised Multi-Sensor Regression under Heterogeneous Sensor Bias** [[paper](https://arxiv.org/abs/2606.22200)]
- [2026] **Learning Dynamical Systems from Multiple Sparse Datasets: A Hierarchical Bayesian Modeling Approach** [[paper](https://arxiv.org/abs/2606.24966)]
- [2026] **Hierarchical Projection for Adaptive Knowledge Transfer** [[paper](https://arxiv.org/abs/2606.08691)]
- [2026] **Estimating Supply Incrementality in Two-sided Marketplaces: A Causal Machine Learning Approach** [[paper](https://arxiv.org/abs/2606.30999)]
- [2026] **Credibility-Weighted Pricing of Autonomous Vehicle Liability Under Operational Design Domain Shift** [[paper](https://arxiv.org/abs/2606.17451)]
- [2026] **Context-Aware Hierarchical Bayesian Modeling of IVF Laboratory Environmental Conditions** [[paper](https://arxiv.org/abs/2606.20459)]
- [2026] **Bridging Data Gaps in Structural Fragility Modeling through Transfer Learning: Methodology and Case Studies** [[paper](https://arxiv.org/abs/2606.18567)]
- [2026] **BIM-Loc: BIM-Integrated Discrepancy-Aware LiDAR-based Indoor Localization** [[paper](https://arxiv.org/abs/2606.14237)]
- [2026] **A multilevel hierarchical framework for quantification of experimental heterogeneity in population snapshot data** *PLoS Computational Biology* [[paper](https://doi.org/10.1371/journal.pcbi.1014379)]
- [2026] **Dynamic Load Balancing for Uncertainty Quantification with Applications in Bayesian Inversion** *Durham Research Online (Durham University)* [[paper](https://arxiv.org/abs/2606.25693)]
- [2026] **Toward Efficient Edge AI With Heterogeneous Computing and Multilevel Optimization** *IEEE Transactions on Very Large Scale Integration (VLSI) Systems* [[paper](https://doi.org/10.1109/tvlsi.2026.3697086)]
- [2026] **Effects of mind-body training on upper-limb function in stroke patients: a multilevel dose-response meta-analysis** *Frontiers in Medicine* [[paper](https://doi.org/10.3389/fmed.2026.1827942)]
- [2026] **Table 3_Effects of mind-body training on upper-limb function in stroke patients: a multilevel dose-response meta-analysis.docx** *Figshare* [[paper](https://figshare.com/articles/dataset/Table_3_Effects_of_mind-body_training_on_upper-limb_function_in_stroke_patients_a_multilevel_dose-response_meta-analysis_docx/32655582)]
- [2026] **Table 2_Effects of mind-body training on upper-limb function in stroke patients: a multilevel dose-response meta-analysis.docx** *Figshare* [[paper](https://figshare.com/articles/dataset/Table_2_Effects_of_mind-body_training_on_upper-limb_function_in_stroke_patients_a_multilevel_dose-response_meta-analysis_docx/32655564)]
- [2026] **Table 1_Effects of mind-body training on upper-limb function in stroke patients: a multilevel dose-response meta-analysis.docx** *Figshare* [[paper](https://figshare.com/articles/dataset/Table_1_Effects_of_mind-body_training_on_upper-limb_function_in_stroke_patients_a_multilevel_dose-response_meta-analysis_docx/32655579)]
- [2026] **Three-level vector autoregressive models.** *Psychological Methods* [[paper](https://doi.org/10.1037/met0000848)]
- [2026] **2248-P: Diabetes Diagnosis Patterns in Medicaid: How State Policy, Managed Care, and Social Vulnerability Shape Detection in Medicaid** *Diabetes* [[paper](https://doi.org/10.2337/db26-2248-p)]
- [2026] **Hormones, rank, and aggression during periods of social stability: examining the Challenge Hypothesis and the Dual Hormone Hypotheses in male white-faced capuchins (Cebus imitator)** *Physiology & Behavior* [[paper](https://doi.org/10.1016/j.physbeh.2026.115423)]
- [2026] **Institutional Variation in Life-Sustaining Treatments and Mortality Among Older Patients** *JAMA Health Forum* [[paper](https://doi.org/10.1001/jamahealthforum.2026.1451)]
- [2026] **What You Don't Know Won't Hurt You: Self-Consistent Hierarchical Inference with Unknown Follow-up Selection Strategies** [[paper](https://arxiv.org/abs/2605.06636)]
- [2026] **Spin Demographics of Active Supermassive Black Holes: Updated Estimates from X-ray reflection and Future opportunities** [[paper](https://arxiv.org/abs/2605.13949)]
- [2026] **On the Need for Spatial Random Effects in Bayesian Regression Models for Multilevel Areal Data** [[paper](https://arxiv.org/abs/2605.09673)]
- [2026] **End-to-End Population Inference from Gravitational-Wave Strain using Transformers** [[paper](https://arxiv.org/abs/2605.11274)]
- [2026] **Cross-Predictive Sparse Bayesian Learning with Application to XL-MIMO Channel Estimation** [[paper](https://arxiv.org/abs/2605.28182)]
- [2026] **Coating Breakdown Prediction for Ships and Inspection Planning** [[paper](https://arxiv.org/abs/2605.29196)]
- [2026] **Context or composition? Spatial Bayesian analysis of sexual violence against adolescent girls and young women in Namibia** *Social Science & Medicine* [[paper](https://doi.org/10.1016/j.socscimed.2026.119433)]
- [2026] **Robust Bayesian multilevel meta-analysis: Adjusting for publication bias in the presence of dependent effect sizes** *Behavior Research Methods* [[paper](https://doi.org/10.3758/s13428-026-03023-y)]
- [2026] **School and Student Variables of Reading Achievement: A Multilevel Mediation Model** *Participatory Educational Research* [[paper](https://doi.org/10.17275/per.26.43.13.3)]
- [2026] **Advanced Statistical Modeling of Xenobiotic Exposure in Maternal–Neonatal Systems: A Censored and Hierarchical Data Approach** *Applied Sciences* [[paper](https://doi.org/10.3390/app16104992)]
- [2026] **Multi‐Level Variable Selection Using a <scp>BART</scp> ‐Enhanced Mixed‐Effects Framework** *Statistics in Medicine* [[paper](https://doi.org/10.1002/sim.70593)]
- [2026] **Spatial heterogeneity and drivers of pulmonary tuberculosis in Guangzhou: a street-level analysis of residents and migrant subgroups from 2015 to 2023** *BMC Public Health* [[paper](https://doi.org/10.1186/s12889-026-27774-7)]
- [2026] **Query-Conditioned Graph Retrieval for Contextualized LLM Reasoning in Personalized Wearable Data** [[paper](https://arxiv.org/abs/2605.18763)]
- [2026] **Data-Driven Constraints on Magnetar Population: No Evidence for a Distinct White Dwarf Channel** [[paper](https://arxiv.org/abs/2604.06472)]
- [2026] **Bayesian Inference for Incomplete 2x2 Diagnostic Tables** [[paper](https://arxiv.org/abs/2604.20611)]
- [2026] **Depression and psychiatric help-seeking as joint outcomes: a Bayesian multilevel analysis of household-level dependence** *Health and Quality of Life Outcomes* [[paper](https://doi.org/10.1186/s12955-026-02531-x)]
- [2026] **MAI-GAN: An Inferentially Calibrated Generative Framework for Multilevel Longitudinal Data with Applications to Educational Intersectionality** *Stats* [[paper](https://doi.org/10.3390/stats9020042)]
- [2026] **Social determinants of subjective well-being among Nigerian women** *BMC Women s Health* [[paper](https://doi.org/10.1186/s12905-026-04425-y)]
- [2026] **The Effect of Atmospheric Chemistry on the Optical Geometric Albedos of Hot Jupiters** [[paper](https://arxiv.org/abs/2603.02409)]
- [2026] **Terahertz Beamforming and Group Sparse Channel Estimation Relying on Low-Resolution ADCs in MU Hybrid MIMO systems** [[paper](https://arxiv.org/abs/2603.20878)]
- [2026] **Hierarchical Latent Structure Learning through Online Inference** [[paper](https://arxiv.org/abs/2603.19139)]
- [2026] **Gravitational Anomaly Measurement in Wide Binaries is Sensitive to Orbital Modeling** [[paper](https://arxiv.org/abs/2603.11015)]
- [2026] **Evolutionary Structural Shift in Security Screening Sensitivity within the U.S. Aviation Network: A 15-Year Longitudinal Bayesian Assessment (2010-2024)** [[paper](https://arxiv.org/abs/2603.16813)]
- [2026] **Efficient Hallucination Detection: Adaptive Bayesian Estimation of Semantic Entropy with Guided Semantic Exploration** [[paper](https://arxiv.org/abs/2603.22812)]
- [2026] **Chemo-dynamical reconstruction of Milky Way globular cluster progenitors: Age-metallicity relations and the universality of multiple stellar populations** [[paper](https://arxiv.org/abs/2603.11814)]
- [2026] **Bayesian Conservative Policy Optimization (BCPO): A Novel Uncertainty-Calibrated Offline Reinforcement Learning with Credible Lower Bounds** [[paper](https://arxiv.org/abs/2603.12284)]
- [2026] **Comparing Bayesian random coefficient prediction and latent interaction models for multilevel moderated mediation** *Frontiers in Psychology* [[paper](https://doi.org/10.3389/fpsyg.2025.1543330)]
- [2026] **Bayesian multilevel analysis of multimorbidity among women in Somalia: prevalence, patterns, and determinants** *Archives of Public Health* [[paper](https://doi.org/10.1186/s13690-026-01905-3)]
- [2026] **Modeling and Analyzing Workers’ Hazard Perception in Construction Equipment Operations: A Hierarchical Bayesian Cognitive Modeling Approach Integrating Multisource Data** *Journal of Construction Engineering and Management* [[paper](https://doi.org/10.1061/jcemd4.coeng-17349)]
- [2026] **STAMP: A shot-type-aware areal multilevel Poisson model for league-wide comparison of basketball shot charts** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2603.24015)]
- [2026] **Mitigating Retest Effects in Cognitive Ecological Momentary Assessment Data - A Tutorial in PyMC, Stan and JAGS** *PsyArXiv (OSF Preprints)* [[paper](https://osf.io/sywbh)]
- [2026] **PT3:07 Sociodemographic, clinical and biomarker predictors of cognitive performance in lupus** [[paper](https://doi.org/10.1136/lupus-2026-el.46)]
- [2026] **Variance of gravitational-wave populations** [[paper](https://arxiv.org/abs/2603.00239)]
- [2026] **Smoothness and other hyperparameter estimation for inverse problems related to data assimilation** [[paper](https://arxiv.org/abs/2602.18328)]
- [2026] **Impact of Spin Priors on the Population Inference of Merging Binary Black Holes** [[paper](https://arxiv.org/abs/2602.12509)]
- [2026] **Density-Informed Pseudo-Counts for Calibrated Evidential Deep Learning** [[paper](https://arxiv.org/abs/2602.01477)]
- [2026] **A context-specific causal model for estimating the effect of extended length of overnight stay on traveller's total expenditure** [[paper](https://arxiv.org/abs/2602.18039)]
- [2026] **A Hierarchical Bayesian Analysis of Neutron-Skin Thicknesses and Implications for the Symmetry-Energy Slope** [[paper](https://arxiv.org/abs/2602.04794)]
- [2026] **Anemia and its associated factors among women of reproductive Age in Zambia: A multilevel mixed-effects analysis** *PLoS ONE* [[paper](https://doi.org/10.1371/journal.pone.0330400)]
- [2026] **pymc-devs/pymc-examples: 2026.02.0** *Open MIND* [[paper](https://github.com/pymc-devs/pymc-examples/tree/2026.02.0)]
- [2026] **Revealing massive black hole astrophysics: The potential of hierarchical inference with extreme mass-ratio inspiral observations** [[paper](https://arxiv.org/abs/2601.15198)]
- [2026] **On the Nonasymptotic Scaling Guarantee of Hyperparameter Estimation in Inhomogeneous, Weakly-Dependent Complex Network Dynamical Systems** [[paper](https://arxiv.org/abs/2601.15603)]
- [2026] **Bayesian Matrix Completion Under Geometric Constraints** [[paper](https://arxiv.org/abs/2601.22765)]
- [2026] **A framework for LISA population inference** [[paper](https://arxiv.org/abs/2601.04168)]
- [2026] **A Hierarchical Bayesian Framework for Model-based Prognostics** [[paper](https://arxiv.org/abs/2601.15942)]

##### 2025

- [2025] **Universality and Falsifiability of Quantum Spacetime Decoherence: A Gauge-Invariant Framework for Gravitational-Wave Phase Diffusion** [[paper](https://arxiv.org/abs/2512.02782)]
- [2025] **Multi state neurons** [[paper](https://arxiv.org/abs/2512.08815)]
- [2025] **Inferring black hole formation channels in GWTC-4.0 via parametric mass-spin correlations derived from first principles** [[paper](https://arxiv.org/abs/2512.03152)]
- [2025] **Hierarchical Bayesian Framework for Multisource Domain Adaptation** [[paper](https://arxiv.org/abs/2512.18553)]
- [2025] **Calibrating hierarchical Bayesian domain inference for a proportion** [[paper](https://arxiv.org/abs/2512.18479)]
- [2025] **A Bayesian approach with persistent homology prior for Robin coefficient identification in a parabolic problem** [[paper](https://arxiv.org/abs/2512.24046)]
- [2025] **The Impacts of Increasingly Complex Matchup Models on Baseball Win Probability** [[paper](https://arxiv.org/abs/2511.17733)]
- [2025] **Taxonomy-Conditioned Hierarchical Bayesian TSB Models for Heterogeneous Intermittent Demand Forecasting** [[paper](https://arxiv.org/abs/2511.12749)]
- [2025] **Reducing normalizing flow complexity for MCMC preconditioning** [[paper](https://arxiv.org/abs/2511.02345)]
- [2025] **Hierarchical Bayesian spectral analysis of multiple stationary time series** [[paper](https://arxiv.org/abs/2511.19406)]
- [2025] **Early evidence for isotropic planetary obliquities in young super-Jupiter systems** [[paper](https://arxiv.org/abs/2511.04091)]
- [2025] **A Clustering Approach for Basket Trials Based on Treatment Response Trajectories** [[paper](https://arxiv.org/abs/2511.09890)]
- [2025] **Out-of-Distribution Detection in LiDAR Semantic Segmentation Using Epistemic Uncertainty from Hierarchical GMMs** [[paper](https://arxiv.org/abs/2510.08631)]
- [2025] **Joint Signal Recovery and Uncertainty Quantification via the Residual Prior Transform** [[paper](https://arxiv.org/abs/2510.20136)]
- [2025] **Inferring neutron-star Love-Q relations from gravitational waves in the hierarchical Bayesian framework** [[paper](https://arxiv.org/abs/2510.22137)]
- [2025] **Hierarchical Bayesian Model for Gene Deconvolution and Functional Analysis in Human Endometrium Across the Menstrual Cycle** [[paper](https://arxiv.org/abs/2510.27097)]
- [2025] **A hierarchical Bayesian approach for population-based structural health monitoring in ship hull structures** [[paper](https://arxiv.org/abs/2510.16316)]
- [2025] **A Honest Cross-Validation Estimator for Prediction Performance** [[paper](https://arxiv.org/abs/2510.07649)]
- [2025] **When (not) to trust Monte Carlo approximations for hierarchical Bayesian inference** [[paper](https://arxiv.org/abs/2509.07221)]
- [2025] **The Bayesian SIAC filter** [[paper](https://arxiv.org/abs/2509.14771)]
- [2025] **Modeling Spatial Heterogeneity in Exposure Buffers and Risk: A Hierarchical Bayesian Approach** [[paper](https://arxiv.org/abs/2509.25708)]
- [2025] **How many patients could we save with LLM priors?** [[paper](https://arxiv.org/abs/2509.04250)]
- [2025] **Causal Inference under Threshold Manipulation: Bayesian Mixture Modeling and Heterogeneous Treatment Effects** [[paper](https://arxiv.org/abs/2509.19814)]
- [2025] **Modeling Human Spatial Mobility Patterns with the Lévy Flight Cluster Model** [[paper](https://arxiv.org/abs/2509.00298)]
- [2025] **Constraints on the extreme mass-ratio inspiral population from LISA data** [[paper](https://arxiv.org/abs/2508.16399)]

[⬆ Back to top](#paper-list)

#### Theory

##### 2026

- [2026] **Age-Stratified Bayesian Hierarchical Modeling of Colorectal Cancer Treatment Outcomes** *Research Square* [[paper](https://doi.org/10.21203/rs.3.rs-9783555/v1)]
- [2026] **Exact computation of posterior distribution of mixture weights in hierarchical Bayesian models** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2607.05692)]
- [2026] **The Cognitive–Social Coupling Theory A Unified Computational Framework for Individual Cognition and Collective Behavior** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.21492857)]
- [2026] **Bayesian Analysis for Wildfire Classification in the United States and Australia Through Spatial Hierarchical Models** *Lecture notes in computer science* [[paper](https://doi.org/10.1007/978-3-032-30488-9_25)]
- [2026] **A Multilevel Beta Mixed-effects Analysis of the Non-linear Evolution of HIV Prevalence in Females Aged 15-24 Years** *International STD Research & Reviews* [[paper](https://doi.org/10.9734/isrr/2026/v15i2201)]
- [2026] **Real-time prices and sustainability metrics in retail: Impacts on satisfaction, value, and repurchase intent** *Journal of Retailing and Consumer Services* [[paper](https://doi.org/10.1016/j.jretconser.2026.104913)]
- [2026] **Bayesian Predictive Ensembles for Random Effects Specification Uncertainty: Capturing Individual Heterogeneity in Large-Scale Assessments** [[paper](https://doi.org/10.31234/osf.io/u6qgc_v1)]
- [2026] **Rigid boundaries, selective salience: How classroom gender composition shapes adolescent friendships** *Social Networks* [[paper](https://doi.org/10.1016/j.socnet.2026.04.013)]
- [2026] **FBartos/RoBMA: RoBMA 4.0.0** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.20070712)]
- [2026] **Predicting Optimal Colorectal Cancer Treatments Across Age Groups Using Bayesian Hierarchical Modeling** *Research Square* [[paper](https://doi.org/10.21203/rs.3.rs-9450455/v1)]
- [2026] **Bayesian Inference for Generalized Linear Models** [[paper](https://doi.org/10.1201/9781003715924-5)]
- [2026] **An In-Depth Review of The Uses of Bayesian Methods in Biostatistics In Drug Safety and Pharmacovigilance** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19754317)]
- [2026] **Beyond discretization: why cognitive science should embrace continuity** *Frontiers in Psychology* [[paper](https://doi.org/10.3389/fpsyg.2026.1777565)]
- [2026] **Lamarckian Replicators in Darwinian Hierarchies: Reconciling Gene-Centered and Multilevel Selection Approaches to Legal Evolution** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19199269)]
- [2026] **Unified Estimation Framework for Multilevel Logistic Regression: Integrating Maximum Likelihood, Entropy-Based Regularization, and Bayesian MAP via Newton-Raphson Optimization** *Statistics Optimization & Information Computing* [[paper](https://doi.org/10.19139/soic-2310-5070-3225)]
- [2026] **PREreview of "Analyzing Binary Judgments: A Comparison of ANOVA, Signal Detection Theory, and Generalized Linear Mixed Models in the Context of the Illusory Truth Effect"** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19185902)]
- [2026] **Civic Education and Anti-Corruption Attitudes Among Colombian Youth: Findings from the International Civic and Citizenship Education Study (ICCS)** *Research Square* [[paper](https://doi.org/10.21203/rs.3.rs-8744214/v1)]

[⬆ Back to top](#paper-list)

#### Application

##### 2026

- [2026] **Bayesian Hierarchical Moderated Factor Analysis for Testing Measurement Invariance in Multilevel Data: Model Development, Simulation Studies, and Experience Sampling Application** *Structural Equation Modeling A Multidisciplinary Journal* [[paper](https://doi.org/10.1080/10705511.2026.2642783)]

[⬆ Back to top](#paper-list)

#### Development

##### 2026

- [2026] **Regional inequalities in maternal-level under-five mortality in Ethiopia: evidence from the 2019 Mini-DHS using multilevel negative binomial and Bayesian models** *BMC Public Health* [[paper](https://doi.org/10.1186/s12889-026-28921-w)]
- [2026] **Constraining on- and off-fault nonlinear dynamic rupture parameters via hierarchical Bayesian inversion for the 2019 Mw 7.1 ridgecrest earthquake** *Earth and Planetary Science Letters* [[paper](https://doi.org/10.1016/j.epsl.2026.120061)]
- [2026] **When Bayes goes bad: Weakly-regularized covariate adjustment leads to a biased estimate of prevalence** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2603.29134)]

[⬆ Back to top](#paper-list)

#### Systems

##### 2026

- [2026] **The Prosody of Emojis** *Underline Science Inc.* [[paper](https://doi.org/10.48448/p587-xj92)]
- [2026] **BAYESIAN HIERARCHICAL AND MULTILEVEL MODELS FOR PREDICTING THE IMPACT OF CLIMATE CHANGE ON ENVIRONMENTAL SYSTEMS WITH UNCERTAINTY QUANTIFICATION** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19723224)]
- [2026] **Mapping circulating microRNA signatures in type 1 diabetic microvascular disease: A systematic review and Bayesian multilevel meta-analysis with bioinformatic integration of molecular dysregulation** *Metabolism* [[paper](https://doi.org/10.1016/j.metabol.2026.156591)]

[⬆ Back to top](#paper-list)

#### Survey

##### 2026

- [2026] **Bayesian hierarchical analysis of gender and socioeconomic inequalities in HIV testing uptake in Ghana** *BMC Infectious Diseases* [[paper](https://doi.org/10.1186/s12879-026-14085-w)]
- [2026] **Socio-demographic and contextual drivers of insecticide-treated net (ITN) utilization among women of reproductive age in Togo: a Bayesian multilevel analysis of the 2017 Togo Malaria Indicator Survey** *Research Square* [[paper](https://doi.org/10.21203/rs.3.rs-8849056/v1)]

[⬆ Back to top](#paper-list)

### Bayesian Nonparametrics

#### Method

##### 2026

- [2026] **Finding the Needle in a Haystack: Test-Time Analog Circuit Representation Adaptation for Bayesian Optimization** [[paper](https://arxiv.org/abs/2608.12687)]
- [2026] **Bayesian ACCESS for Understanding Latent Epidemic Trajectories from Publicly Released Suppressed Data: Application to U.S. Opioid-related Overdose Mortality** [[paper](https://arxiv.org/abs/2608.09103)]
- [2026] **A Bayesian Proof of the Bernoulli Theorem** [[paper](https://arxiv.org/abs/2608.11031)]
- [2026] **A hyperspherical deep Bayesian model for interpretable clustering and relationship prediction in microbiome multi-omics integration** *bioRxiv (Cold Spring Harbor Laboratory)* [[paper](https://doi.org/10.64898/2026.07.28.741374)]
- [2026] **The Dirichlet Process as sampling distribution** [[paper](https://arxiv.org/abs/2607.26185)]
- [2026] **Pitfalls and Remedies for Multi-Task Bayesian Optimization** [[paper](https://arxiv.org/abs/2607.09073)]
- [2026] **PYPM-GGD: Pitman-Yor Process Mixture with Generalized Gaussian Density using ADAM** [[paper](https://arxiv.org/abs/2607.24583)]
- [2026] **Bayesian nonparametric estimation of correlated gravitational wave detector network noise using matrix-gamma process priors** [[paper](https://arxiv.org/abs/2607.26619)]
- [2026] **Bayesian Inference for Extracting Barrier Distributions from Fusion Excitation Functions** [[paper](https://arxiv.org/abs/2607.14422)]
- [2026] **Assessing Preferential Sampling in Retail Survival Data: A Bayesian Joint LGCP and Spatial Probit Model for Mini-Supermarket Closure in Tokyo** [[paper](https://arxiv.org/abs/2607.14860)]
- [2026] **Active Learning for Calibrating Entangling Gates via Surrogate-Based Optimization** [[paper](https://arxiv.org/abs/2607.00284)]
- [2026] **A unified perspective of Gaussian process approximation for differential equations** [[paper](https://arxiv.org/abs/2607.06292)]
- [2026] **Sequential sparse Gaussian process quantile regression** [[paper](https://arxiv.org/abs/2606.31284)]
- [2026] **Posterior consistency of Pólya trees for deconvolution under the linear model** [[paper](https://arxiv.org/abs/2606.11406)]
- [2026] **On two overlooked stick-breaking constructions of the normalized inverse Gaussian process** [[paper](https://arxiv.org/abs/2606.19306)]
- [2026] **Modeling Nonlinear Ability Trajectories and Learner Heterogeneity in Online Learning: A Bayesian Nonparametric Dynamic IRT Framework** [[paper](https://arxiv.org/abs/2606.15525)]
- [2026] **Learning Nonlinear Dynamics: Improving the Estimation Efficiency and Reliability of Gaussian Process State-Space Models** [[paper](https://arxiv.org/abs/2606.24691)]
- [2026] **Improving exoplanet mass characterisation with Bayesian model selection using the Learned Harmonic Mean Estimator** [[paper](https://arxiv.org/abs/2606.27252)]
- [2026] **How Deep Are Deep GPs, Really? A Sharp Threshold and a Non-Gaussian Limit for Compositional GPs** [[paper](https://arxiv.org/abs/2606.08218)]
- [2026] **From data to decisions: Bayesian modelling and global sensitivity analysis for flotation control** [[paper](https://arxiv.org/abs/2606.06173)]
- [2026] **Bayesian nonparametric Mallows model for clustering preference data** [[paper](https://arxiv.org/abs/2606.12305)]
- [2026] **Bayesian Nonparametric Privacy-Preserving Synthetic Data Generation: I. Discrete Data** [[paper](https://arxiv.org/abs/2606.26073)]
- [2026] **Bayesian Nonparametric Detection of Anomalies in Multivariate Functional Data** [[paper](https://arxiv.org/abs/2606.18412)]
- [2026] **A case study of causal mediation using Bayesian nonparametrics and semiparametric corrections** [[paper](https://arxiv.org/abs/2606.20148)]
- [2026] **A Bayesian Approach for Nonignorable Dropout in Bivariate Longitudinal Models** [[paper](https://arxiv.org/abs/2606.25749)]
- [2026] **Radioactive Source Seeking using Bayesian Optimisation with Movement Penalty** [[paper](https://arxiv.org/abs/2605.14942)]
- [2026] **Progressive Autonomy as Preference Learning: A Formalization of Trust Calibration for Agentic Tool Use** [[paper](https://arxiv.org/abs/2605.19151)]
- [2026] **Posterior Contraction of Lévy Adaptive B-spline Regression in Besov Spaces** [[paper](https://arxiv.org/abs/2605.19610)]
- [2026] **Laplace Variational Inference for Dirichlet Process Mixtures of Marked Poisson Point Processes** [[paper](https://arxiv.org/abs/2605.09562)]
- [2026] **Heterogeneous Ordinal Structure Learning with Bayesian Nonparametric Complexity Discovery** [[paper](https://arxiv.org/abs/2605.04191)]
- [2026] **Efficient multidisciplinary design via Bayesian optimization** [[paper](https://arxiv.org/abs/2607.22560)]
- [2026] **Clustering Craters on the Moon with Dysfunctional Families** [[paper](https://arxiv.org/abs/2605.21387)]
- [2026] **Central limit theorem for the homozygosity of the hierarchical Pitman-Yor process** [[paper](https://arxiv.org/abs/2605.12475)]
- [2026] **Bayesian Nonparametrics: Principles and Practice** [[paper](https://arxiv.org/abs/2605.22253)]
- [2026] **Bayesian Nonparametric Mixed-Effect ODEs with Gaussian Processes** [[paper](https://arxiv.org/abs/2605.13088)]
- [2026] **Bayesian Modelling of Nonstationary Extreme Values Using a Nonparametric Hawkes Process** [[paper](https://arxiv.org/abs/2605.03331)]
- [2026] **Newton's Algorithm as a Gradient Flow: A Geometric Framework for Recursive Mixture Estimation** [[paper](https://arxiv.org/abs/2604.13341)]
- [2026] **Nested Atoms Model with Application to Clustering Big Population-Scale Single-Cell Data** [[paper](https://arxiv.org/abs/2604.11731)]
- [2026] **Modelling spatial heterogeneity in the effects of area-level covariates on income distributions using Bayesian nonparametric methods** [[paper](https://arxiv.org/abs/2604.23357)]
- [2026] **Bayesian policy gradient and actor-critic algorithms** [[paper](https://arxiv.org/abs/2604.27563)]
- [2026] **Bayesian Nonparametric Modeling for Multivariate Conditional Copula Regression with Varying Coefficients** [[paper](https://arxiv.org/abs/2604.12859)]
- [2026] **Variational Bayes and Truncation approximations for Enriched Dirichlet process mixtures** [[paper](https://arxiv.org/abs/2603.12427)]
- [2026] **Tree-Embedded Bayesian Factor Models for Multidimensional Categorical Distributions** [[paper](https://arxiv.org/abs/2603.02502)]
- [2026] **Tree-Based Predictive Models for Noisy Input Data** [[paper](https://arxiv.org/abs/2603.07409)]
- [2026] **The minimax optimal convergence rate of posterior density in the weighted orthogonal polynomials** [[paper](https://arxiv.org/abs/2603.18490)]
- [2026] **Joint Bayesian analysis of soft and high-p_\perp probes yields tighter constraints on QGP properties** [[paper](https://arxiv.org/abs/2603.09584)]
- [2026] **Analysis of lane-changing primitives in highway merging areas based on nonparametric Bayesian models** [[paper](https://doi.org/10.1117/12.3101130)]
- [2026] **Weighted Wasserstein Barycenter of Gaussian Processes for exotic Bayesian Optimization tasks** [[paper](https://arxiv.org/abs/2602.09181)]
- [2026] **Species Sensitivity Distribution revisited: a Bayesian nonparametric approach** [[paper](https://arxiv.org/abs/2602.04788)]
- [2026] **Sample Efficient Active Algorithms for Offline Reinforcement Learning** [[paper](https://arxiv.org/abs/2602.01260)]
- [2026] **Prognostics of Multisensor Systems with Unknown and Unlabeled Failure Modes via Bayesian Nonparametric Process Mixtures** [[paper](https://arxiv.org/abs/2602.19263)]
- [2026] **Nonparametric Bayesian Optimization for General Rewards** [[paper](https://arxiv.org/abs/2602.07411)]
- [2026] **Lecture notes: From Gaussian processes to feature learning** [[paper](https://arxiv.org/abs/2602.12855)]
- [2026] **Estimating the Shannon Entropy Using the Pitman--Yor Process** [[paper](https://arxiv.org/abs/2602.08347)]
- [2026] **Bayesian Nonparametrics for Gene-Gene and Gene-Environment Interactions in Case-Control Studies: A Synthesis and Extension** [[paper](https://arxiv.org/abs/2602.15387)]
- [2026] **Analytical Results for Two Exponential Family Distributions in Hierarchical Dirichlet Processes** [[paper](https://arxiv.org/abs/2602.12527)]
- [2026] **An Efficient Bayesian Framework for Inverse Problems via Optimization and Inversion: Surrogate Modeling, Parameter Inference, and Uncertainty Quantification** [[paper](https://arxiv.org/abs/2602.04537)]
- [2026] **Activation-Space Uncertainty Quantification for Pretrained Networks** [[paper](https://arxiv.org/abs/2602.14934)]
- [2026] **On the contraction rate of the posterior distribution for nonlinear PDE parameter identification** [[paper](https://arxiv.org/abs/2601.17805)]
- [2026] **Bayesian nonparametric modeling of dynamic pollution clusters through an autoregressive logistic-beta Stirling-gamma process** [[paper](https://arxiv.org/abs/2601.04625)]
- [2026] **Approximate Likelihood-Based Inference for Spatial Generalized Linear Mixed Models** [[paper](https://arxiv.org/abs/2601.16022)]

##### 2025

- [2025] **Uncertainty Quantification for Scientific Machine Learning using Sparse Variational Gaussian Process Kolmogorov-Arnold Networks (SVGP KAN)** [[paper](https://arxiv.org/abs/2512.05306)]
- [2025] **Tolerance Intervals Using Dirichlet Processes** [[paper](https://arxiv.org/abs/2512.02178)]
- [2025] **Spatially Varying Gene Regulatory Networks via Bayesian Nonparametric Covariate-Dependent Directed Cyclic Graphical Models** [[paper](https://arxiv.org/abs/2512.11732)]
- [2025] **Repulsive g-Priors for Regression Mixtures** [[paper](https://arxiv.org/abs/2512.16276)]
- [2025] **L^2-posterior contraction rates for Gaussian process and random series priors in Bayesian nonparametric regression models** [[paper](https://arxiv.org/abs/2512.20503)]
- [2025] **Improving Semantic Uncertainty Quantification in LVLMs with Semantic Gaussian Processes** [[paper](https://arxiv.org/abs/2512.14177)]
- [2025] **Exchangeable Gaussian Processes with application to epidemics** [[paper](https://arxiv.org/abs/2512.05227)]
- [2025] **Dynamic sparse graphs with overlapping communities** [[paper](https://arxiv.org/abs/2512.10717)]
- [2025] **Design-marginal calibration of Gaussian process predictive distributions: Bayesian and conformal approaches** [[paper](https://arxiv.org/abs/2512.05611)]
- [2025] **A Novel Geometry-Aware GPR-Based Energy-Efficient and Low-Overhead Channel Estimation Scheme** [[paper](https://arxiv.org/abs/2512.22578)]
- [2025] **We Still Don't Understand High-Dimensional Bayesian Optimization** [[paper](https://arxiv.org/abs/2512.00170)]
- [2025] **Resolving Ratio Redundancy in Chemical Freeze-out Studies with Principal Component Analysis and Bayesian Calibration** [[paper](https://arxiv.org/abs/2511.15707)]
- [2025] **Efficient bayesian spatially varying coefficients modeling for censored data using the vecchia approximation** [[paper](https://arxiv.org/abs/2511.21553)]
- [2025] **Data-driven Learning of Interaction Laws in Multispecies Particle Systems with Gaussian Processes: Convergence Theory and Applications** [[paper](https://arxiv.org/abs/2511.02053)]
- [2025] **Calibrated Bayes analysis of cluster-randomized trials** [[paper](https://arxiv.org/abs/2511.20833)]
- [2025] **Bayesian Nonparametric Marked Hawkes Processes for Earthquake Modeling** [[paper](https://arxiv.org/abs/2511.22538)]
- [2025] **Bayesian Causal Effect Estimation for Categorical Data using Staged Tree Models** [[paper](https://arxiv.org/abs/2511.03399)]
- [2025] **Bayesian Bridge Gaussian Process Regression** [[paper](https://arxiv.org/abs/2511.17415)]
- [2025] **BITS for GAPS: Bayesian Information-Theoretic Sampling for hierarchical GAussian Process Surrogates** [[paper](https://arxiv.org/abs/2511.16815)]
- [2025] **A General Bayesian Nonparametric Approach for Estimating Population-Level and Conditional Causal Effects** [[paper](https://arxiv.org/abs/2511.23085)]
- [2025] **Total robustness in Bayesian Nonlinear Regression** [[paper](https://arxiv.org/abs/2510.03131)]
- [2025] **Revisiting Gaussian Process Reconstruction for Cosmological Inference: The Generalised GP (Gen GP) Framework** [[paper](https://arxiv.org/abs/2510.03742)]
- [2025] **Quasinormal modes from numerical relativity with Bayesian inference** [[paper](https://arxiv.org/abs/2510.11783)]
- [2025] **On Misspecified Error Distributions in Bayesian Functional Clustering: Consequences and Remedies** [[paper](https://arxiv.org/abs/2510.17215)]
- [2025] **Identification and estimation of causal mechanisms in cluster-randomized trials with post-treatment confounding using Bayesian nonparametrics** [[paper](https://arxiv.org/abs/2510.16673)]
- [2025] **Hierarchical shot-noise Cox process mixtures for clustering across groups** [[paper](https://arxiv.org/abs/2510.14681)]
- [2025] **Gaussian Processes for Inferring Parton Distributions** [[paper](https://arxiv.org/abs/2510.21041)]
- [2025] **Defensive Model Expansion for Robust Bayesian Inference** [[paper](https://arxiv.org/abs/2510.09598)]
- [2025] **Bayesian nonparametric modeling of multivariate count data with an unknown number of traits** [[paper](https://arxiv.org/abs/2510.24526)]
- [2025] **State Estimation for Linear Systems with Non-Gaussian Measurement Noise via Dynamic Programming** [[paper](https://arxiv.org/abs/2509.05482)]
- [2025] **Multiomics Tissue Segmentation via Spatially-Informed Nested Biclustering Methods** [[paper](https://arxiv.org/abs/2509.02482)]
- [2025] **Monitoring Adverse Events Through Bayesian Nonparametric Clustering Across Studies** [[paper](https://arxiv.org/abs/2509.07267)]
- [2025] **Global-Local Dirichlet Processes for Identifying Pan-Cancer Subpopulations Using Both Shared and Cancer-Specific Data** [[paper](https://arxiv.org/abs/2509.22884)]
- [2025] **GS-BART: Bayesian Additive Regression Trees with Graph-split Decision Rules** [[paper](https://arxiv.org/abs/2509.07166)]
- [2025] **Efficient Estimation of Unfactorizable Systematic Uncertainties** [[paper](https://arxiv.org/abs/2509.15500)]
- [2025] **Bayesian Mixture Models for Heterogeneous Extremes** [[paper](https://arxiv.org/abs/2509.15359)]
- [2025] **Updated Astrophysical Equation-of-State Constraints on the Color-Superconducting Gap** [[paper](https://arxiv.org/abs/2508.20763)]
- [2025] **Untangling Sample and Population Level Estimands in Bayesian Causal Computation** [[paper](https://arxiv.org/abs/2508.15016)]
- [2025] **From Partial Exchangeability to Predictive Probability: A Bayesian Perspective on Classification** [[paper](https://arxiv.org/abs/2508.16716)]
- [2025] **CONAN: A Python package for modeling lightcurve and radial velocity data of exoplanetary systems** [[paper](https://arxiv.org/abs/2508.20196)]

[⬆ Back to top](#paper-list)

#### Theory

##### 2026

- [2026] **Large parameter asymptotic analysis for homogeneous normalized random measures with independent increments** *Canadian Journal of Statistics* [[paper](https://arxiv.org/abs/2403.14032)]
- [2026] **DP-Splat: Bayesian Nonparametric Complexity Control for Gaussian Splatting** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2607.10912)]
- [2026] **Robust Nonparametric Inference in High Dimensions: A Bayesian-Frequentist Synthesis** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.21347703)]
- [2026] **Operating mode analysis of new power systems based on TCN–LSTM–AAE and DPGMM** *DOAJ (DOAJ: Directory of Open Access Journals)* [[paper](https://doaj.org/article/5c74dae9e3e743d8bf20d8791e9558a8)]
- [2026] **Bayesian Nonparametric Methods in Textile Spinning:A Comprehensive Framework for Modeling Comparing Parameters in Quality Control** *Open MIND* [[paper](https://doi.org/10.5281/zenodo.18753904)]

[⬆ Back to top](#paper-list)

### Bayesian Deep Learning

#### Method

##### 2026

- [2026] **Uncertainty-Aware Deep Learning for Genomics Applications: Insights from an Empirical Study** [[paper](https://arxiv.org/abs/2608.11054)]
- [2026] **The Bayesian Reflex: A Predictive Coding Engine for Artificial Intelligence** [[paper](https://arxiv.org/abs/2608.00492)]
- [2026] **Scaling Limits for Ising Models on Inhomogeneous Random Graphs and Applications** [[paper](https://arxiv.org/abs/2608.12804)]
- [2026] **SVI-DAG: A Structured Variational Inference Approach to Bayesian Causal Discovery** [[paper](https://arxiv.org/abs/2608.04930)]
- [2026] **Revisiting 2D and 3D Dainotti Correlations for GRBs Using Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2608.07044)]
- [2026] **Comment on "Modeling rapid language learning by distilling Bayesian priors into artificial neural networks"** [[paper](https://arxiv.org/abs/2608.12974)]
- [2026] **Uncertainty Quantification in Deep Neural Networks** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.21765338)]
- [2026] **An interpretable uncertainty-aware intelligent framework based on generalized multi-scale formal contexts and Bayesian deep neural networks** *Information Sciences* [[paper](https://doi.org/10.1016/j.ins.2026.123987)]
- [2026] **Physics-informed Bayesian neural SDEs with uncertainty quantification: A unified framework for biomedical dynamics and financial market modeling** *Physica A Statistical Mechanics and its Applications* [[paper](https://doi.org/10.1016/j.physa.2026.131885)]
- [2026] **Uncertainty quantification for trustworthy deep learning: Methods and measures** [[paper](https://arxiv.org/abs/2607.28248)]
- [2026] **Rethinking Likelihood distributions: Student's t Likelihood Boosts Bayesian Neural Network Performance** [[paper](https://arxiv.org/abs/2607.25376)]
- [2026] **Probabilistic Memory for Trustworthy Edge Intelligence** [[paper](https://arxiv.org/abs/2607.02465)]
- [2026] **PAC-DP: PAC-Bayesian Diffusion Policy Learning** [[paper](https://arxiv.org/abs/2607.24296)]
- [2026] **Modernizing HEBO: a robust Bayesian optimization baseline for practical heteroskedastic and non-stationary problems** [[paper](https://arxiv.org/abs/2607.10669)]
- [2026] **Human population dynamics as a Bayesian inverse transport problem** [[paper](https://arxiv.org/abs/2607.13171)]
- [2026] **Hierarchical Bayesian Quadrature** [[paper](https://arxiv.org/abs/2607.10793)]
- [2026] **Guiding Posterior Exploration with Optimizer-Derived Geometry** [[paper](https://arxiv.org/abs/2607.25312)]
- [2026] **Evaluation of U-235 and U-238 Fission Product Yields Using Bayesian Neural Networks: Comparison of Baseline and Physics-Informed Models** [[paper](https://arxiv.org/abs/2607.04148)]
- [2026] **Efficient Bayesian Deep Ensembles via Analytic Predictive Inference** [[paper](https://arxiv.org/abs/2607.06776)]
- [2026] **Disentangling Model and Human Data Uncertainty in Apparent Facial Age Estimation** [[paper](https://arxiv.org/abs/2607.16378)]
- [2026] **Bayesian Complete-Pooling in Cross-Subject Classification for Motor Imagery Electroencephalogram** [[paper](https://arxiv.org/abs/2607.22980)]
- [2026] **Deep probabilistic regression via ensemble Bayesian neural networks for uncertainty-aware prediction of long-span bridge vibrations** *Journal of Infrastructure Intelligence and Resilience* [[paper](https://doi.org/10.1016/j.iintel.2026.100228)]
- [2026] **Academic Performance Forecasting via Data Imputation and Bayesian Neural Networks** *Applied Sciences* [[paper](https://doi.org/10.3390/app16147350)]
- [2026] **DYNAMIC UNCERTAINTY-AWARE BAYESIAN NEURAL MODEL FOR REAL-TIME WORKFORCE DISPLACEMENT RISK UNDER AI AUTOMATION** *International Journal of Computer Information Systems and Industrial Management Applications* [[paper](https://doi.org/10.70917/ijcisim-2026-4563)]
- [2026] **Bayesian inference based physics informed neural network approach for infectious disease forecasting** *Computers & Chemical Engineering* [[paper](https://doi.org/10.1016/j.compchemeng.2026.109832)]
- [2026] **Uncertainty Estimation and Generalization Bounds for Modern Deep Learning** [[paper](https://arxiv.org/abs/2606.13818)]
- [2026] **TreeGRNG: Binary Tree Gaussian Random Number Generator for Efficient Probabilistic AI Hardware** [[paper](https://arxiv.org/abs/2606.16599)]
- [2026] **Transformer Architectures as Complete Bayes Processes: A Formal Proof in the Measure-Theoretic Kernel Framework** [[paper](https://arxiv.org/abs/2606.30440)]
- [2026] **Reconstructing Galactic Gravitational Potentials from Stellar Kinematics with Physics-Informed Neural Networks** [[paper](https://arxiv.org/abs/2606.18386)]
- [2026] **Multi-Task Bayesian In-Context Learning** [[paper](https://arxiv.org/abs/2606.20538)] [[code](https://github.com/martianmartina/multi-task-bayesian-icl)]
- [2026] **Function-Space Priors for Bayesian Neural ODEs with Application to Vessel Trajectory Prediction** [[paper](https://arxiv.org/abs/2606.06351)]
- [2026] **Equivariance and Augmentation for Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2606.26273)]
- [2026] **Bayesian three-dimensional seismic travel-time tomography for active- and passive-source seismic data using physics-informed neural network** [[paper](https://arxiv.org/abs/2606.21789)]
- [2026] **Bayesian Adaptation Gym: A Benchmark for the Bayesian Low-Rank Adaptation of Multi-Modal Language Models** [[paper](https://arxiv.org/abs/2606.22188)] [[code](https://github.com/SRI-CSL/BayesAdapt)]
- [2026] **A Short Review of Estimators for the GLM predictive of Laplace Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2607.00214)]
- [2026] **A Bayesian Filtering Approach for Learning Lagrangian Dynamics from Noisy Measurements** [[paper](https://arxiv.org/abs/2606.31137)]
- [2026] **A 65 nm Multi-Modal Bayesian Inference Engine with 16.3 fJ/Sample Calibration-Free GRNG for Risk-Aware At-Home Skin Lesion Screening** [[paper](https://arxiv.org/abs/2606.07439)]
- [2026] **Bayesian Uncertainty-aware Deep Learning with noisy labels: Tackling annotation ambiguity in EEG seizure detection** *PLoS ONE* [[paper](https://arxiv.org/abs/2410.19815)]
- [2026] **Understanding Active Fire Detection Uncertainty with Bayesian Neural Networks** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.20547810)]
- [2026] **Score-Based Martingale Posteriors for Deep Neural Networks** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2606.15725)]
- [2026] **Uncertainty aware pre-stack seismic inversion using probabilistic neural networks** *Franklin Open* [[paper](https://doi.org/10.1016/j.fraope.2026.100652)]
- [2026] **Uncertainty-aware classification and triage of structural heart disease using electrocardiography and echocardiography metrics** [[paper](https://arxiv.org/abs/2605.22968)]
- [2026] **Training Neural Networks with Optimal Double-Bayesian Learning** [[paper](https://arxiv.org/abs/2605.20009)]
- [2026] **Regularized Offline Policy Optimization with Posterior Hybrid Bayesian Belief** [[paper](https://arxiv.org/abs/2606.00680)]
- [2026] **Quantized Probabilistic AI for Gear Fault Diagnosis in Motor Drives** [[paper](https://arxiv.org/abs/2605.05032)]
- [2026] **Position: The Time for Sampling Is Now! Charting a New Course for Bayesian Deep Learning** [[paper](https://arxiv.org/abs/2605.21765)]
- [2026] **LLMs are not (consistently) Bayesian: Quantifying internal (in)consistencies of LLMs' probabilistic beliefs** [[paper](https://arxiv.org/abs/2605.06915)]
- [2026] **Infra-Bayesian Reinforcement Learning Agents Outperform Classical RL For Worst-Case Robustness** [[paper](https://arxiv.org/abs/2605.23146)]
- [2026] **IV-ICL: Bounding Causal Effects with Instrumental Variables via In-Context Learning** [[paper](https://arxiv.org/abs/2605.12924)]
- [2026] **Federated Martingale Posterior Samping** [[paper](https://arxiv.org/abs/2605.18554)]
- [2026] **Dirichlet-Based Monte Carlo Dropout for Uncertainty Estimation in Neural Networks** [[paper](https://arxiv.org/abs/2605.23635)]
- [2026] **Direct Bethe Free Energy Minimization for Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2605.08446)]
- [2026] **Deep Bayesian spectral learning for the discovery of hot subdwarf binaries in LAMOST** *Astronomy and Astrophysics* [[paper](https://doi.org/10.1051/0004-6361/202659415)]
- [2026] **Optimization of risk-based and cost-minimized maintenance strategy for corroded pipeline using reinforcement learning** *Reliability Engineering & System Safety* [[paper](https://doi.org/10.1016/j.ress.2026.112929)]
- [2026] **Bayesian neural networks with Dirichlet process priors for reinforcement learning** *HAL (Le Centre pour la Communication Scientifique Directe)* [[paper](https://hal.science/hal-05624371)]
- [2026] **Bayesian deep learning for uncertainty aware medical image segmentation correction and feature engineering: Applications to OCT imaging** *Informatics in Medicine Unlocked* [[paper](https://doi.org/10.1016/j.imu.2026.101763)]
- [2026] **Eﬃcient Deep Neural Networks for Autonomous Perception** *Journal of the Arkansas Academy of Science* [[paper](https://scholarworks.uark.edu/etd/6180)]
- [2026] **Calibrated Network Security Situation Prediction Based on Neural Granger Causal Representation and Bayesian Graph Neural Networks** *Concurrency and Computation Practice and Experience* [[paper](https://doi.org/10.1002/cpe.70760)]
- [2026] **Uncertainty quantification of deep learning model for mineral prospectivity mapping** [[paper](https://doi.org/10.5194/egusphere-2026-1293)]
- [2026] **Bayesian Deep Learning and Probabilistic Forecasting of Stock Prices** *Algorithms* [[paper](https://doi.org/10.3390/a19050391)]
- [2026] **Transfer learning for nonparametric Bayesian networks** [[paper](https://arxiv.org/abs/2604.01021)]
- [2026] **Towards E-Value Based Stopping Rules for Bayesian Deep Ensembles** [[paper](https://arxiv.org/abs/2604.18089)]
- [2026] **Quantum Measurement Statistics as Bayesian Uncertainty Estimators for Physics-Constrained Learning** [[paper](https://arxiv.org/abs/2604.10896)]
- [2026] **Minimaxity and Admissibility of Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2604.04673)]
- [2026] **Instantiating Bayesian CVaR lower bounds in Interactive Decision Making Problems** [[paper](https://arxiv.org/abs/2604.12519)]
- [2026] **Fast and principled equation discovery from chaos to climate** [[paper](https://arxiv.org/abs/2604.11929)]
- [2026] **Collaborative Contextual Bayesian Optimization** [[paper](https://arxiv.org/abs/2604.18912)] [[code](https://github.com/cchihyu/Collaborative-Contextual-Bayesian-Optimization)]
- [2026] **BaLoRA: Bayesian Low-Rank Adaptation of Large Scale Models** [[paper](https://arxiv.org/abs/2605.08110)]
- [2026] **BVFLMSP : Bayesian Vertical Federated Learning for Multimodal Survival with Privacy** [[paper](https://arxiv.org/abs/2604.02248)]
- [2026] **A Physics Informed Bayesian Neural Network for the Neutron Star Equation of State** [[paper](https://arxiv.org/abs/2604.24949)]
- [2026] **A Primer on Bayesian Neural Networks: Review and Debates** *Statistical Science* [[paper](https://arxiv.org/abs/2309.16314)]
- [2026] **Machine learning-driven probabilistic framework for uncertainty quantification and reliability-based design of radiation shielding concrete structures** *Engineering Applications of Artificial Intelligence* [[paper](https://doi.org/10.1016/j.engappai.2026.114752)]
- [2026] **Abstract 4189: Quantifying uncertainty in virtual spatial transcriptomics using Bayesian neural networks** *Cancer Research* [[paper](https://doi.org/10.1158/1538-7445.am2026-4189)]
- [2026] **Robust investment portfolio management for dynamic financial markets using Bayesian neural networks** *International Review of Economics & Finance* [[paper](https://doi.org/10.1016/j.iref.2026.105244)]
- [2026] **Trustworthy Deep Learning: Robustness, Uncertainty Quantification, and Adversarial Resilience** [[paper](https://doi.org/10.70593/978-93-7185-510-5)]
- [2026] **Towards Reliable Simulation-based Inference** [[paper](https://arxiv.org/abs/2603.08947)]
- [2026] **On the Relationship between Bayesian Networks and Probabilistic Structural Causal Models** [[paper](https://arxiv.org/abs/2603.27406)]
- [2026] **On the Interplay of Priors and Overparametrization in Bayesian Neural Network Posteriors** [[paper](https://arxiv.org/abs/2603.22030)]
- [2026] **Improving Infinitely Deep Bayesian Neural Networks with Nesterov's Accelerated Gradient Method** [[paper](https://arxiv.org/abs/2603.25024)]
- [2026] **Identifiability and amortized inference limitations in Kuramoto models** [[paper](https://arxiv.org/abs/2603.21752)]
- [2026] **Efficient Controller Learning from Human Preferences and Numerical Data Via Multi-Modal Surrogate Models** [[paper](https://arxiv.org/abs/2603.24138)]
- [2026] **Bayesian-Symbolic Integration for Uncertainty-Aware Parking Prediction** [[paper](https://arxiv.org/abs/2603.27119)]
- [2026] **Bayesian neural network with autoencoder for model-based description of α-particle preformation factor** [[paper](https://arxiv.org/abs/2603.07976)]
- [2026] **Reliable uncertainty estimates in deep learning with efficient Metropolis-Hastings algorithms** *Nature Communications* [[paper](https://doi.org/10.1038/s41467-026-70015-z)]
- [2026] **Power System state prediction method based on improved long short-term memory considering renewable energy uncertainty** *Engineering Applications of Artificial Intelligence* [[paper](https://doi.org/10.1016/j.engappai.2026.114313)]
- [2026] **Incorporating uncertainty quantification into deep-learning-based travel mode choice modeling: A Bayesian Neural Network approach and an uncertainty-guided active survey framework** *Travel Behaviour and Society* [[paper](https://doi.org/10.1016/j.tbs.2026.101282)]
- [2026] **Basic: Bayesian Spiral Attention Classifier for Interpretable Medical Image Classification** [[paper](https://doi.org/10.1109/wacvw68408.2026.00039)]
- [2026] **An active learning multi-fidelity metamodel method considering arbitrary fidelity level** *Aerospace Science and Technology* [[paper](https://doi.org/10.1016/j.ast.2026.112054)]
- [2026] **Artificial Intelligence Methods in Cephalometric Image Analysis—A Systematic Narrative Review** *Journal of Clinical Medicine* [[paper](https://doi.org/10.3390/jcm15051920)]
- [2026] **Bayesian Deep Learning for Convective Initiation Nowcasting Uncertainty Estimation** *Artificial Intelligence for the Earth Systems* [[paper](https://doi.org/10.1175/aies-d-25-0064.1)]
- [2026] **FlareCast: A Solar Flare Forecasting System Utilizing Deep Bayesian Neural Networks and the Concept of Machine Learning Operations** *The Astrophysical Journal Supplement Series* [[paper](https://doi.org/10.3847/1538-4365/ae43dc)]
- [2026] **Uncertainty analysis of bathymetry inversion in the South China Sea: a comparison of deep learning and Bayesian approaches** *Geophysical Journal International* [[paper](https://doi.org/10.1093/gji/ggag093)]
- [2026] **Beyond Accuracy: Reliability and Uncertainty Estimation in Convolutional Neural Networks** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2603.10731)]
- [2026] **Variational Graph Neural Networks for Uncertainty Quantification in Inverse Problems** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2603.29515)]
- [2026] **Stochastic Spiking Neuron Based SNN Can be Inherently Bayesian** [[paper](https://arxiv.org/abs/2602.07037)]
- [2026] **Robust design optimization for a nonlinear system via Bayesian neural network enhanced polynomial dimensional decomposition** [[paper](https://arxiv.org/abs/2602.08161)]
- [2026] **Robust Predictive Uncertainty and Double Descent in Contaminated Bayesian Random Features** [[paper](https://arxiv.org/abs/2602.19126)]
- [2026] **MPL-HMC: A Tunable Parameterized Leapfrog Framework for Robust Hamiltonian Monte Carlo** [[paper](https://arxiv.org/abs/2602.14061)]
- [2026] **General Proximal Flow Networks** [[paper](https://arxiv.org/abs/2603.00751)]
- [2026] **From Shallow Bayesian Neural Networks to Gaussian Processes: General Convergence, Identifiability and Scalable Inference** [[paper](https://arxiv.org/abs/2602.22492)]
- [2026] **Dirichlet Scale Mixture Priors for Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2602.19859)]
- [2026] **Curiosity is Knowledge: Self-Consistent Learning and No-Regret Optimization with Active Inference** [[paper](https://arxiv.org/abs/2602.06029)]
- [2026] **Calibrated Test-Time Guidance for Bayesian Inference** [[paper](https://arxiv.org/abs/2602.22428)]
- [2026] **Beyond NNGP: Large Deviations and Feature Learning in Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2602.22925)]
- [2026] **Bayesian Online Model Selection** [[paper](https://arxiv.org/abs/2602.17958)]
- [2026] **Bayesian Lottery Ticket Hypothesis** [[paper](https://arxiv.org/abs/2602.18825)]
- [2026] **Bayesian Conformal Prediction as a Decision Risk Problem** *NeurIPS 2025* [[paper](https://arxiv.org/abs/2602.03331)]
- [2026] **A fast Bayesian surrogate for the photon flux in ultra-peripheral collisions** [[paper](https://arxiv.org/abs/2602.10692)]
- [2026] **Deep Bayesian Networks for Failure Probability Estimation in Biomedical Sensors** *Eksploatacja i Niezawodnosc - Maintenance and Reliability* [[paper](https://doi.org/10.17531/ein/218121)]
- [2026] **Acoustic signals-based probabilistic fault diagnosis for expansion joints of small and medium bridges using Bayesian ensemble learning** *Engineering Structures* [[paper](https://doi.org/10.1016/j.engstruct.2026.122379)]
- [2026] **Physics-Guided Bayesian Neural Networks for Reliable Fault Detection in Wind Energy Systems** *Figshare* [[paper](https://doi.org/10.6084/m9.figshare.31424507.v1)]
- [2026] **VBO-MI: A Fully Gradient-Based Bayesian Optimization Framework Using Variational Mutual Information Estimation** [[paper](https://arxiv.org/abs/2601.08172)]
- [2026] **Singular Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2602.00387)]
- [2026] **Reconstructing Gamma Ray Burst Energy Relations with Observational H(z) data in Neural Network Framework** [[paper](https://arxiv.org/abs/2601.08550)]
- [2026] **Going NUTS with ADVI: Exploring various Bayesian Inference techniques with Facebook Prophet** [[paper](https://arxiv.org/abs/2601.20120)]
- [2026] **EviNAM: Intelligibility and Uncertainty via Evidential Neural Additive Models** [[paper](https://arxiv.org/abs/2601.08556)]
- [2026] **Bayesian Interpolating Neural Network (B-INN): a scalable and reliable Bayesian model for large-scale physical systems** [[paper](https://arxiv.org/abs/2601.22860)]
- [2026] **Bayes-PD: Exploring a Sequence to Binding Bayesian Neural Network model trained on Phage Display data** [[paper](https://arxiv.org/abs/2601.03930)]
- [2026] **Accelerated Regularized Wasserstein Proximal Sampling Algorithms** [[paper](https://arxiv.org/abs/2601.09848)]

##### 2025

- [2025] **Walking on the Fiber: A Simple Geometric Approximation for Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2512.01500)]
- [2025] **Unreliable Uncertainty Estimates with Monte Carlo Dropout** [[paper](https://arxiv.org/abs/2512.14851)]
- [2025] **Uncertainty Reasoning with Photonic Bayesian Machines** [[paper](https://arxiv.org/abs/2512.02217)]
- [2025] **Real-Time Structural Health Monitoring with Bayesian Neural Networks: Distinguishing Aleatoric and Epistemic Uncertainty for Digital Twin Frameworks** [[paper](https://arxiv.org/abs/2512.03115)]
- [2025] **Nanosecond-Scale Proton Emission from Triaxially Deformed Lu-148 Predicted with High Accuracy Qp Value via Novel Bayesian Evaluation** [[paper](https://arxiv.org/abs/2512.01663)]
- [2025] **Many Minds from One Model: Bayesian-Inspired Transformers for Population Diversity** [[paper](https://arxiv.org/abs/2512.25063)]
- [2025] **Long-Horizon Model-Based Offline Reinforcement Learning Without Explicit Conservatism** [[paper](https://arxiv.org/abs/2512.04341)]
- [2025] **Learning-Augmented Ski Rental with Discrete Distributions: A Bayesian Approach** [[paper](https://arxiv.org/abs/2512.07313)]
- [2025] **High-Dimensional Surrogate Modeling for Closed-Loop Learning of Neural-Network-Parameterized Model Predictive Control** [[paper](https://arxiv.org/abs/2512.11705)]
- [2025] **Geometric Scaling of Bayesian Inference in LLMs** [[paper](https://arxiv.org/abs/2512.23752)]
- [2025] **Generalised Linear Models in Deep Bayesian RL with Learnable Basis Functions** [[paper](https://arxiv.org/abs/2512.20974)]
- [2025] **From Overfitting to Reliability: Introducing the Hierarchical Approximate Bayesian Neural Network** [[paper](https://arxiv.org/abs/2512.13111)]
- [2025] **DTI-GP: Bayesian operations for drug-target interactions using deep kernel Gaussian processes** [[paper](https://arxiv.org/abs/2512.24810)]
- [2025] **Bayes-DIC Net: Estimating Digital Image Correlation Uncertainty with Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2512.04323)]
- [2025] **Uncertainty of Network Topology with Applications to Out-of-Distribution Detection** [[paper](https://arxiv.org/abs/2511.18813)]
- [2025] **SE3D: Building a radiative transfer emulator to fit panchromatic resolved galaxy observations with 3D models of dust and stars** [[paper](https://arxiv.org/abs/2511.19623)]
- [2025] **ReBaPL: Repulsive Bayesian Prompt Learning** [[paper](https://arxiv.org/abs/2511.17339)]
- [2025] **Probabilistic Digital Twin for Misspecified Structural Dynamical Systems via Latent Force Modeling and Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2511.22133)]
- [2025] **Physics-guided Bayesian neural networks for zonal corrections and uncertainty quantification in separated flows** [[paper](https://arxiv.org/abs/2511.14534)]
- [2025] **LUME-DBN: Full Bayesian Learning of DBNs from Incomplete data in Intensive Care** [[paper](https://arxiv.org/abs/2511.04333)]
- [2025] **J-HERTz: J-PLUS Heritage Exploration of Radio Targets at z &lt; 5** [[paper](https://arxiv.org/abs/2511.14844)]
- [2025] **Intrinsic Dimension Estimation for Radio Galaxy Zoo using Diffusion Models** [[paper](https://arxiv.org/abs/2511.11490)]
- [2025] **How to Marginalize in Causal Structure Learning?** [[paper](https://arxiv.org/abs/2511.14001)]
- [2025] **Full-Atom Peptide Design via Riemannian-Euclidean Bayesian Flow Networks** [[paper](https://arxiv.org/abs/2511.14516)]
- [2025] **Fast Bayesian Updates via Harmonic Representations** [[paper](https://arxiv.org/abs/2511.06978)]
- [2025] **Epistemic and Aleatoric Uncertainty Quantification in Weather and Climate Models** [[paper](https://arxiv.org/abs/2511.23448)]
- [2025] **Efficient RF Passive Components Modeling with Bayesian Online Learning and Uncertainty Aware Sampling** [[paper](https://arxiv.org/abs/2511.15125)]
- [2025] **Bayesian Neural Networks with Monte Carlo Dropout for Probabilistic Electricity Price Forecasting** [[paper](https://arxiv.org/abs/2511.11701)]
- [2025] **Bayesian Mixture of Experts For Large Language Models** [[paper](https://arxiv.org/abs/2511.08968)]
- [2025] **Adaptive Stepsizing for Stochastic Gradient Langevin Dynamics in Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2511.11666)]
- [2025] **Transformers can do Bayesian Clustering** [[paper](https://arxiv.org/abs/2510.24318)]
- [2025] **Sample-efficient and Scalable Exploration in Continuous-Time RL** *ICLR 2026* [[paper](https://arxiv.org/abs/2510.24482)]
- [2025] **Resource-Efficient and Robust Inference of Deep and Bayesian Neural Networks on Embedded and Analog Computing Platforms** [[paper](https://arxiv.org/abs/2510.24951)]
- [2025] **Reinforcement Learning with Imperfect Transition Predictions: A Bellman-Jensen Approach** [[paper](https://arxiv.org/abs/2510.18687)]
- [2025] **Incorporating Expert Knowledge into Bayesian Causal Discovery of Mixtures of Directed Acyclic Graphs** [[paper](https://arxiv.org/abs/2510.06735)]
- [2025] **How Regularization Terms Make Invertible Neural Networks Bayesian Point Estimators** [[paper](https://arxiv.org/abs/2510.26704)]
- [2025] **Empirical Bayesian Multi-Bandit Learning** [[paper](https://arxiv.org/abs/2510.26284)]
- [2025] **Bayesian and Deterministic Neural Network approaches to Faraday Cup calibration and plasma parameter estimation** [[paper](https://arxiv.org/abs/2510.20946)]
- [2025] **Bayesian Topological Convolutional Neural Nets** [[paper](https://arxiv.org/abs/2510.11704)]
- [2025] **Bayesian Neural Networks vs. Mixture Density Networks: Theoretical and Empirical Insights for Uncertainty-Aware Nonlinear Modeling** [[paper](https://arxiv.org/abs/2510.25001)]
- [2025] **Bayesian Inference of Primordial Magnetic Field Parameters from CMB with Spherical Graph Neural Networks** [[paper](https://arxiv.org/abs/2510.20795)]
- [2025] **Bayesian E(3)-Equivariant Interatomic Potential with Iterative Restratification of Many-body Message Passing** [[paper](https://arxiv.org/abs/2510.03046)]
- [2025] **Adaptive Defense against Harmful Fine-Tuning for Large Language Models via Bayesian Data Scheduler** [[paper](https://arxiv.org/abs/2510.27172)] [[code](https://github.com/Egg-Hu/Bayesian-Data-Scheduler)]
- [2025] **The Sensitivity of Variational Bayesian Neural Network Performance to Hyperparameters** [[paper](https://arxiv.org/abs/2509.20574)]
- [2025] **Structural Refinement of Bayesian Networks for Efficient Model Parameterisation** [[paper](https://arxiv.org/abs/2510.00334)]
- [2025] **Split Conformal Prediction in the Function Space with Neural Operators** [[paper](https://arxiv.org/abs/2509.04623)]
- [2025] **Scalable bayesian shadow tomography for quantum property estimation with set transformers** [[paper](https://arxiv.org/abs/2509.18674)]
- [2025] **Probabilistic Graybox Characterization of Quantum Devices with Bayesian Neural Networks** [[paper](https://arxiv.org/abs/2509.24232)]
- [2025] **Online Bayesian Risk-Averse Reinforcement Learning** [[paper](https://arxiv.org/abs/2509.14077)]
- [2025] **Kalman Bayesian Transformer** [[paper](https://arxiv.org/abs/2509.10695)]
- [2025] **Iterative HOMER with uncertainties** [[paper](https://arxiv.org/abs/2509.03592)]
- [2025] **Is Sequence Information All You Need for Bayesian Optimization of Antibodies?** [[paper](https://arxiv.org/abs/2509.24933)]
- [2025] **Graph Random Features for Scalable Gaussian Processes** [[paper](https://arxiv.org/abs/2509.03691)]
- [2025] **Bayesian Surrogates for Risk-Aware Pre-Assessment of Aging Bridge Portfolios** [[paper](https://arxiv.org/abs/2509.25031)]
- [2025] **Bayesian Physics Informed Neural Networks for Reliable Transformer Prognostics** [[paper](https://arxiv.org/abs/2509.15933)]
- [2025] **Priors Matter: Addressing Misspecification in Bayesian Deep Q-Learning** [[paper](https://arxiv.org/abs/2508.21488)]
- [2025] **Online Incident Response Planning under Model Misspecification through Bayesian Learning and Belief Quantization** [[paper](https://arxiv.org/abs/2508.14385)]
- [2025] **Integrating Large Language Models with Network Optimization for Interactive and Explainable Supply Chain Planning: A Real-World Case Study** [[paper](https://arxiv.org/abs/2508.21622)]
- [2025] **Deep Active Learning for Lung Disease Severity Classification from Chest X-rays: Learning with Less Data in the Presence of Class Imbalance** [[paper](https://arxiv.org/abs/2508.21263)]
- [2025] **Combined Stochastic and Robust Optimization for Electric Autonomous Mobility-on-Demand with Nested Benders Decomposition** [[paper](https://arxiv.org/abs/2508.19933)]

[⬆ Back to top](#paper-list)

#### Theory

##### 2026

- [2026] **Evidence-based Bayesian neural network for uncertainty quantification of industrial robots** *Advanced Engineering Informatics* [[paper](https://doi.org/10.1016/j.aei.2026.105056)]
- [2026] **Explainable Bayesian Deep Learning through Input-skip Latent Binary Bayesian Neural Networks** *Journal of Artificial Intelligence Research* [[paper](https://arxiv.org/abs/2503.10496)]
- [2026] **BAYESIAN DEEP LEARNING FOR DYNAMIC SYSTEMS: CAUSAL DISCOVERY AND DIGITAL TWINS** *Purdue* [[paper](https://doi.org/10.25394/pgs.33103685)]
- [2026] **Neutrosophic deep learning framework for uncertainty-aware prediction in chemical process optimization** [[paper](https://doi.org/10.3897/arphapreprints.e209240)]
- [2026] **Exoformer: Accelerating Bayesian atmospheric retrievals with transformer neural networks** [[paper](https://doi.org/10.5194/epsc2026-594)]
- [2026] **Physics-assisted deep probability learning for natural gas leakage detection from infrared cameras without anomaly data** *Engineering Applications of Artificial Intelligence* [[paper](https://doi.org/10.1016/j.engappai.2026.115416)]
- [2026] **Evaluating the reliability of fault diagnosis in nuclear facility via uncertainty analysis** *Annals of Nuclear Energy* [[paper](https://doi.org/10.1016/j.anucene.2026.112468)]
- [2026] **Possibilistic Predictive Uncertainty for Deep Learning** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2605.00600)]
- [2026] **Template-fitting meets deep learning: redshift estimation using physics-guided neural networks** *Journal of Astrophysics and Astronomy* [[paper](https://arxiv.org/abs/2507.00866)]
- [2026] **Probabilistic Prediction and Uncertainty Quantification of Bearing Capacity of Lime-Treated, Geotextile-Reinforced Silty Sand Using Bayesian Neural Network** *Indian geotechnical journal* [[paper](https://doi.org/10.1007/s40098-026-01529-y)]
- [2026] **Temporal adaptive neural ordinary differential equations with deep spatio-temporal point processes for real-time network intrusion detection** *Complex & Intelligent Systems* [[paper](https://doi.org/10.1007/s40747-026-02291-7)]
- [2026] **A hybrid machine learning approach for scalable and uncertainty-aware RSU-based tracking and performance optimization in VANETs** *Journal on Wireless Communications and Networking* [[paper](https://doi.org/10.1186/s13638-026-02616-7)]
- [2026] **Diagnostic of erosive cavitation in hydraulic turbines from indirect measurements using SCADA data with uncertainty quantification** *Results in Engineering* [[paper](https://doi.org/10.1016/j.rineng.2026.110456)]
- [2026] **Learning to Estimate: Bayesian Filtering with Deep Density Methods** [[paper](https://doi.org/10.63959/chalmers.dt/5867)]
- [2026] **Bayesian-deep-learning-based model with uncertainty quantification for cutting tool wear prediction** *Journal of Mechanical Science and Technology* [[paper](https://doi.org/10.1007/s12206-026-0306-x)]
- [2026] **DSB-net: An effective dynamic sparse Bayesian network for underwater sonar object detection** *Neurocomputing* [[paper](https://doi.org/10.1016/j.neucom.2026.133288)]
- [2026] **physically interpretable residual strength prediction of corroded pipelines via symbolic Bayesian networks** *Scientific Reports* [[paper](https://doi.org/10.1038/s41598-026-41914-4)]
- [2026] **Physics-informed deep learning and finite element integration for mesoscale impact response of concrete targets** *International Journal of Impact Engineering* [[paper](https://doi.org/10.1016/j.ijimpeng.2026.105724)]
- [2026] **Sample-efficient LIBS quantitative analysis of steel based on Bayesian convolutional neural networks and active learning** *Spectrochimica Acta Part B Atomic Spectroscopy* [[paper](https://doi.org/10.1016/j.sab.2026.107512)]
- [2026] **Uncertainty-Aware Bayesian Deep Learning Framework for Safety-Critical Condition Monitoring** *TUbilio (Technical University of Darmstadt)* [[paper](https://tubiblio.ulb.tu-darmstadt.de/view/person/Mostafavi=3AAtabak=3A=3A.html>)]
- [2026] **Bayesian Deep Learning-Based Carbon Price Distribution Modeling and Uncertainty Quantification** *Journal of Energy and Climate Change* [[paper](https://doi.org/10.3724/j.issn.2097-4981.jecc-2025-0380)]
- [2026] **Bayesian Asymmetric Quantized Deep Learning with Triangulation Topology Aggregation Optimizer** *Research Square* [[paper](https://doi.org/10.21203/rs.3.rs-9112427/v1)]
- [2026] **Evidential Perfusion Physics-Informed Neural Networks with Residual Uncertainty Quantification** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2603.09359)]
- [2026] **Active operator learning with predictive uncertainty quantification for partial differential equations** *Journal of Computational Physics* [[paper](https://doi.org/10.1016/j.jcp.2026.114791)]
- [2026] **Remaining Useful Life Prediction Based on Interpretable Serialized Variational Autoencoder: A Drift-Diffusion Stochastic Equation Perspective** *IEEE Transactions on Industrial Informatics* [[paper](https://doi.org/10.1109/tii.2026.3657827)]
- [2026] **Physics-Informed Deep Learning for Bearing Remaining Useful Life: Adaptive Paris-Law Regularization with Gaussian Processes** *Integrating materials and manufacturing innovation* [[paper](https://doi.org/10.1007/s40192-026-00441-w)]

[⬆ Back to top](#paper-list)

#### Survey

##### 2026

- [2026] **Bayesian Deep Learning for Measurement Error Correction in Health Survey Data** *Research Square* [[paper](https://doi.org/10.21203/rs.3.rs-9983104/v1)]

[⬆ Back to top](#paper-list)

### Applications

#### Method

##### 2026

- [2026] **High-dimensional Multi-objective Bayesian Optimization with Learned Variable Interactions** [[paper](https://arxiv.org/abs/2608.11713)]
- [2026] **Can Bayesian Optimization Efficiently Find a Strong Single Expert in Neural Thickets?** [[paper](https://arxiv.org/abs/2608.10867)]
- [2026] **Battery Storage Co-Optimization in Day-Ahead and Real-Time Markets with Bayesian Optimization** [[paper](https://arxiv.org/abs/2608.00911)]
- [2026] **Active Learning Guided Design Space Refinement for Scalable Multi-Objective Bayesian Optimization in Materials Discovery** [[paper](https://arxiv.org/abs/2608.04651)]
- [2026] **Symbolic Discovery of Iterative Algorithms: A Continuous Latent Space Bayesian Optimization Framework** [[paper](https://arxiv.org/abs/2607.01552)]
- [2026] **Safe Bayesian Optimization with Counterfactual Policies** [[paper](https://arxiv.org/abs/2607.05620)]
- [2026] **Robust Wavelength Selection for Partial Least Squares Sugar Content Estimation Using Combinatorial Bayesian Optimization** [[paper](https://arxiv.org/abs/2607.27645)]
- [2026] **Robust Airfoil Design Optimization via a Bilevel Model-Based Methodology** [[paper](https://arxiv.org/abs/2607.29161)]
- [2026] **Privacy-Aware Collaborative and Distributed Bayesian Optimization** [[paper](https://arxiv.org/abs/2607.11600)]
- [2026] **Model-Guided Local Bayesian Optimization for Tuning of Interpretable Controllers in Injection Molding** [[paper](https://arxiv.org/abs/2607.05159)]
- [2026] **Maximally Robust Satisficing Bayesian Optimization** [[paper](https://arxiv.org/abs/2607.13652)]
- [2026] **Learning to Stay Fresh: A Self-Learning Semantic Framework for Underwater Internet of Things** [[paper](https://arxiv.org/abs/2607.16902)]
- [2026] **Frugal Bayesian Optimization: Scalable Surrogates for Data- and Resource-Limited Discovery** [[paper](https://arxiv.org/abs/2607.29225)]
- [2026] **Efficient Heteroscedastic Bayesian Optimization for Risk-Aware AutoRL** [[paper](https://arxiv.org/abs/2607.26680)]
- [2026] **Constraint-Bound Agnostic Bayesian Optimization: One Model for All Thresholds** [[paper](https://arxiv.org/abs/2607.23448)]
- [2026] **Collaborative Spatial Learning with Multi-LLM Agents in Networked Social Experiments** [[paper](https://arxiv.org/abs/2607.14574)]
- [2026] **Bayesian optimization approach for tracking a moving target from far-field data in three dimensions** [[paper](https://arxiv.org/abs/2607.21135)]
- [2026] **A Heavy-Tailed QLindley Distribution for Modelling Skewed Lifetime Data** *Mathematics* [[paper](https://doi.org/10.3390/math14132395)]
- [2026] **Bayesian Optimization on the Equilibrium Manifold** [[paper](https://arxiv.org/abs/2606.29299)]
- [2026] **B3O: Scalable Boltzmann Batch Bayesian Optimization** [[paper](https://arxiv.org/abs/2606.30228)]
- [2026] **A Novel Grant Prediction Method for 5G NR Terminals** [[paper](https://arxiv.org/abs/2606.22125)]
- [2026] **Model-based Deep Learning for Radar Artifact Mitigation** *TU/e Research Portal* [[paper](https://research.tue.nl/en/publications/90dae526-1bc6-441d-b48e-7d74fce6b74c)]
- [2026] **Transferring Information Across Interventions in Causal Bayesian Optimization** [[paper](https://arxiv.org/abs/2606.01457)]
- [2026] **Safe Bayesian Optimization for Uncertain Correlation Matrices in Linear Models of Co-Regionalization** [[paper](https://arxiv.org/abs/2605.13302)]
- [2026] **Online Sharp-Calibrated Bayesian Optimization** [[paper](https://arxiv.org/abs/2605.10572)]
- [2026] **ORTHOBO: Orthogonal Bayesian Hyperparameter Optimization** [[paper](https://arxiv.org/abs/2605.06454)]
- [2026] **MTRBO: Multiple trust-region based Bayesian optimization** [[paper](https://arxiv.org/abs/2605.06618)]
- [2026] **LEAP: A closed-loop framework for perovskite precursor additive discovery** [[paper](https://arxiv.org/abs/2605.20242)]
- [2026] **LABO: LLM-Accelerated Bayesian Optimization through Broad Exploration and Selective Experimentation** [[paper](https://arxiv.org/abs/2605.22054)]
- [2026] **Kernel-based guarantees for nonlinear parametric models in Bayesian optimization** [[paper](https://arxiv.org/abs/2605.13160)]
- [2026] **Inducing Permutation Invariant Priors in Bayesian Optimization for Carbon Capture and Storage Applications** [[paper](https://arxiv.org/abs/2605.02409)]
- [2026] **Embedding by Elicitation: Dynamic Representations for Bayesian Optimization of System Prompts** [[paper](https://arxiv.org/abs/2605.19093)]
- [2026] **Bayesian Optimization with Structured Measurements: A Vector-Valued RKHS Framework** [[paper](https://arxiv.org/abs/2605.09775)]
- [2026] **Automated Random Embedding for Practical Bayesian Optimization with Unknown Effective Dimension** [[paper](https://arxiv.org/abs/2605.23473)]
- [2026] **Bayesian and non-Bayesian inference for the inverse power induced XLindley distribution with applications to engineering and radiation data** *Journal of Radiation Research and Applied Sciences* [[paper](https://doi.org/10.1016/j.jrras.2026.102409)]
- [2026] **Robust Bayesian hypothesis testing with the hierarchical EZ-DDM** *Behavior Research Methods* [[paper](https://doi.org/10.3758/s13428-026-03066-1)]
- [2026] **A Novel Distribution on the Unit Interval with Properties and Applications for Electronic Components** *Axioms* [[paper](https://doi.org/10.3390/axioms15050359)]
- [2026] **Practical validation of synthetic pre-crash scenarios** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2605.04564)]
- [2026] **Provable and scalable quantum Gaussian processes for quantum learning** [[paper](https://arxiv.org/abs/2605.00099)]
- [2026] **Preferential Bayesian Optimization with Crash Feedback** [[paper](https://arxiv.org/abs/2604.01776)]
- [2026] **Multi-Objective Bayesian Optimization via Adaptive \varepsilon-Constraints Decomposition** [[paper](https://arxiv.org/abs/2604.15959)] [[code](https://github.com/YangYaohong1/STAGE-BO)]
- [2026] **HARBOR: Automated Harness Optimization** [[paper](https://arxiv.org/abs/2604.20938)]
- [2026] **BayMOTH: Bayesian optiMizatiOn with meTa-lookahead -- a simple approacH** [[paper](https://arxiv.org/abs/2604.12005)]
- [2026] **A Finite Time Analysis of Thompson Sampling for Bayesian Optimization with Preferential Feedback** [[paper](https://arxiv.org/abs/2604.25025)]
- [2026] **Novel DUS Topp-Leone Burr-Hatke exponential model with properties and application to COVID-19 datasets** *Modern Journal of Statistics* [[paper](https://doi.org/10.64389/mjs.2026.02268)]
- [2026] **The New Polynomial Single Parameter Distribution: Properties, Bayesian and Non-Bayesian Inference with Real-Data Applications** *AppliedMath* [[paper](https://doi.org/10.3390/appliedmath6040060)]
- [2026] **Constructing confidence intervals for constrained parameters via valid prior-free inferential models** *arXiv (Cornell University)* [[paper](https://arxiv.org/abs/2604.09055)]
- [2026] **A COMPARATIVE ANALYSIS OF THE PROPOSED WEIBULL- EXPONENTIAL-LOGISTIC POISSON DISTRIBUTION WITH EXISTING WEIBULL-EXPONENTIAL-LOGISTIC AND WEIBULL-LOGISTIC- DISTRIBUTION MODEL USING GLASS FIBRE STRENGTH DATA** *International Journal of Convergent and Informatics Science Research* [[paper](https://doi.org/10.70382/hijcisr.v11i9.051)]
- [2026] **Update of PHYSBO: Improving Usability and Portability of Bayesian Optimization for Physics and Materials Research** [[paper](https://arxiv.org/abs/2603.01349)]
- [2026] **Standard Acquisition Is Sufficient for Asynchronous Bayesian Optimization** [[paper](https://arxiv.org/abs/2603.13501)]
- [2026] **Self-Tuning Sparse Attention: Multi-Fidelity Hyperparameter Optimization for Transformer Acceleration** [[paper](https://arxiv.org/abs/2603.18417)]
- [2026] **Local Constrained Bayesian Optimization** *ICML 2026* [[paper](https://arxiv.org/abs/2603.07965)]
- [2026] **Information Theoretic Bayesian Optimization over the Probability Simplex** [[paper](https://arxiv.org/abs/2603.09793)]
- [2026] **Deep learning-guided evolutionary optimization for protein design** [[paper](https://arxiv.org/abs/2603.02753)] [[code](https://github.com/ErikHartman/bopep)]
- [2026] **Automatic Termination Strategy of Inelastic Neutron-scattering Measurement Using Bayesian Optimization for Bin-width Selection** [[paper](https://arxiv.org/abs/2603.16946)]
- [2026] **Adversarial Query Synthesis via Bayesian Optimization** [[paper](https://arxiv.org/abs/2603.01570)]
- [2026] **A Tutorial Review of Bayesian Optimization with Gaussian Processes to Accelerate Stationary Point Searches** [[paper](https://arxiv.org/abs/2603.10992)]
- [2026] **Bayesian and non-Bayesian inference for the induced XLindley distribution with data analysis** *Scientific African* [[paper](https://doi.org/10.1016/j.sciaf.2026.e03323)]
- [2026] **A Bayesian statistical method to estimate the climatology of extreme temperature under multiple scenarios: the ANKIALE package** *Geoscientific model development* [[paper](https://doi.org/10.5194/gmd-19-2349-2026)]
- [2026] **Wasserstein-enabled characterization of designs and myopic decisions in Bayesian Optimization** [[paper](https://arxiv.org/abs/2602.11289)]
- [2026] **RuleSmith: Multi-Agent LLMs for Automated Game Balancing** [[paper](https://arxiv.org/abs/2602.06232)]
- [2026] **Optimal Control of Microswimmers for Trajectory Tracking Using Bayesian Optimization** [[paper](https://arxiv.org/abs/2602.09563)]
- [2026] **Multi Objective Design Optimization of Non Pneumatic Passenger Car Tires Using Finite Element Modeling, Machine Learning, and Particle swarm Optimization and Bayesian Optimization Algorithms** [[paper](https://arxiv.org/abs/2602.04277)]
- [2026] **Cost-Aware Bayesian Optimization for Prototyping Interactive Devices** [[paper](https://arxiv.org/abs/2602.01774)]
- [2026] **Causal-Informed Hybrid Online Adaptive Optimization for Ad Load Personalization in Large-Scale Social Networks** [[paper](https://arxiv.org/abs/2602.10129)]
- [2026] **New Extension Odd Generalized Rayleigh-Nadarajah Haghighi Distribution with Application and Simulated Data** *F1000Research* [[paper](https://doi.org/10.12688/f1000research.173330.1)]
- [2026] **Correction: Parameter-optimized generative adversarial network framework for synthetic MRI generation: fine-tuning critical variables for enhanced image fidelity** *Frontiers in Medicine* [[paper](https://doi.org/10.3389/fmed.2026.1803906)]
- [2026] **Simulated Annealing-based Candidate Optimization for Batch Acquisition Functions** [[paper](https://arxiv.org/abs/2601.07258)]
- [2026] **SMOG: Scalable Meta-Learning for Multi-Objective Bayesian Optimization** [[paper](https://arxiv.org/abs/2601.22131)]
- [2026] **In-Situ Inverse Design of a Plasma Metamaterial Beam Steering Device** [[paper](https://arxiv.org/abs/2601.14670)]
- [2026] **Improving CMA-ES Convergence Speed, Efficiency, and Reliability in Noisy Robot Optimization Problems** [[paper](https://arxiv.org/abs/2601.09594)]
- [2026] **Hyperparameter Optimization of Constraint Programming Solvers** [[paper](https://arxiv.org/abs/2601.11389)]
- [2026] **Combinatorial Bandit Bayesian Optimization for Tensor Outputs** [[paper](https://arxiv.org/abs/2602.00640)]
- [2026] **Bgolearn: a Unified Bayesian Optimization Framework for Accelerating Materials Discovery** [[paper](https://arxiv.org/abs/2601.06820)] [[code](https://github.com/Bin-Cao/Bgolearn)]
- [2026] **Bayesian Optimization of Noisy Log-Likelihoods Evaluated by Particle Filters -- One Parameter Case --** [[paper](https://arxiv.org/abs/2601.06545)]

##### 2025

- [2025] **Profile Bayesian Optimization for Expensive Computer Experiments** [[paper](https://arxiv.org/abs/2512.23581)]
- [2025] **OPBO: Order-Preserving Bayesian Optimization** [[paper](https://arxiv.org/abs/2512.18980)] [[code](https://github.com/pengwei222/OPBO)]
- [2025] **Warm-Starting Iterative Gaussian Processes for Faster Sequential Inference** [[paper](https://arxiv.org/abs/2511.16340)]
- [2025] **MALBO: Optimizing LLM-Based Multi-Agent Teams via Multi-Objective Bayesian Optimization** [[paper](https://arxiv.org/abs/2511.11788)]
- [2025] **Local Entropy Search over Descent Sequences for Bayesian Optimization** [[paper](https://arxiv.org/abs/2511.19241)]
- [2025] **Hash Collisions in Molecular Fingerprints: Effects on Property Prediction and Bayesian Optimization** [[paper](https://arxiv.org/abs/2511.17078)]
- [2025] **Function-on-Function Bayesian Optimization** [[paper](https://arxiv.org/abs/2511.12783)]
- [2025] **Consecutive Preferential Bayesian Optimization** [[paper](https://arxiv.org/abs/2511.05163)]
- [2025] **Thompson Sampling via Fine-Tuning of LLMs** *ICLR 2026* [[paper](https://arxiv.org/abs/2510.13328)]
- [2025] **SemanticOpt: Towards LLM-Based Semantic Black-Box Optimization** [[paper](https://arxiv.org/abs/2510.25404)]
- [2025] **Optimizing the Unknown: Black Box Bayesian Optimization with Energy-Based Model and Reinforcement Learning** [[paper](https://arxiv.org/abs/2510.19530)]
- [2025] **MOBO-OSD: Batch Multi-Objective Bayesian Optimization via Orthogonal Search Directions** [[paper](https://arxiv.org/abs/2510.20872)] [[code](https://github.com/LamNgo1/mobo-osd)]
- [2025] **Informed Initialization for Bayesian Optimization and Active Learning** [[paper](https://arxiv.org/abs/2510.23681)]
- [2025] **Counterfactual Credit Guided Bayesian Optimization** [[paper](https://arxiv.org/abs/2510.04676)]
- [2025] **ARCO-BO: Adaptive Resource-aware COllaborative Bayesian Optimization for Heterogeneous Multi-Agent Design** [[paper](https://arxiv.org/abs/2510.16652)]
- [2025] **A Constrained Multi-Fidelity Bayesian Optimization Method** [[paper](https://arxiv.org/abs/2510.10984)]
- [2025] **Machine Learning Algorithms for Improving Black Box Optimization Solvers** [[paper](https://arxiv.org/abs/2509.25592)]
- [2025] **Guided Multi-Fidelity Bayesian Optimization for Data-driven Controller Tuning with Digital Twins** [[paper](https://arxiv.org/abs/2509.17952)]
- [2025] **Efficient Multi-Objective Constrained Bayesian Optimization of Bridge Girder** [[paper](https://arxiv.org/abs/2509.20161)]
- [2025] **Directed Evolution of Proteins via Bayesian Optimization in Embedding Space** [[paper](https://arxiv.org/abs/2509.04998)]
- [2025] **Active Learning of A Crystal Plasticity Flow Rule From Discrete Dislocation Dynamics Simulations** [[paper](https://arxiv.org/abs/2509.04788)]

[⬆ Back to top](#paper-list)

#### Theory

##### 2026

- [2026] **FE model bayesian updating with complex modal parameters for a lab-scale pedestrian bridge** *Journal of Civil Structural Health Monitoring* [[paper](https://doi.org/10.1007/s13349-026-01108-y)]
- [2026] **A new unit model with real data applications: classical, Bayesian, and regression analysis** *Japanese Journal of Statistics and Data Science* [[paper](https://doi.org/10.1007/s42081-026-00359-9)]
- [2026] **Constrained Matheron's update rule with application to Bayesian regression** *HAL (Le Centre pour la Communication Scientifique Directe)* [[paper](https://hal.science/hal-05651893)]
- [2026] **A Comprehensive Study of the Bernoulli-Transmuted Geometric Distribution: Theory and Applications** *Pakistan Journal of Statistics and Operation Research* [[paper](https://doi.org/10.18187/pjsor.v22i2.4783)]
- [2026] **FUTURE MATHEMATICS FOR DATA SCIENCE & AI by Prof. Shradha Harshal Chaudhari, Mrs. Ch. Dharani, Dr. T. Siva Krishna ,Dr. M. L. L. Phani Kanth** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.21131498)]
- [2026] **Editorial: Utilizing real world data and real world evidence in veterinary medicine: current practices and future potentials** *Frontiers in Veterinary Science* [[paper](https://doi.org/10.3389/fvets.2025.1745155)]
- [2026] **A New One-Parameter Model Supports an Upside-Down Bathtub Failure Rate: Theory, Inference, and Real-World Applications** *Mathematics* [[paper](https://doi.org/10.3390/math14091566)]
- [2026] **Bayesian Networks an introduction** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19589393)]
- [2026] **The “State of the Art” in MR Image Reconstruction? Knowledge, Culture, and What We Leave Behind in An Era of Big Data and Machine Learning** *Magnetic Resonance in Medicine* [[paper](https://doi.org/10.1002/mrm.70377)]
- [2026] **A Novel Multi-Scale Engineering Framework for Personalized Neuromodulation in Parkinson's Disease: Integrating Control Theory, Bayesian Inference, and Neural Dynamics** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.18820010)]
- [2026] **LorenzoRimella/CAL: Scalable calibration of individual-based epidemic models through categorical approximations** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.19337411)]
- [2026] **Bayesian Social Science Statistics** *Cambridge University Press eBooks* [[paper](https://doi.org/10.1017/9781009340984)]
- [2026] **Structural Correspondence Between Entangled Quantum Circuits and Non-Parametric Causal Estimators: An Empirical Demonstration in Bipolar II Disorder Prevention with IBM Quantum Hardware Validation** *Zenodo (CERN European Organization for Nuclear Research)* [[paper](https://doi.org/10.5281/zenodo.18742656)]

[⬆ Back to top](#paper-list)

### Surveys & Tutorials

## 📖 Citation

If you use this corpus, please cite:

```bibtex
@misc{bayesian-statistics-research,
  author = {Weiß, Tobias},
  title = {Bayesian Statistics Research Corpus: Data-Driven Agentic Literature Review},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/tobias-weiss-ai-xr/bayesian-statistics-research}
}
```

## 📄 License

MIT — see [LICENSE](LICENSE).
