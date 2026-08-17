<h1 align="center">
  <strong>Bayesian Statistics Research Corpus</strong>
</h1>
<h3 align="center">Data-driven, auto-validated literature review for Bayesian statistics</h3>

<div align="center">
  [![GitHub](https://img.shields.io/badge/GitHub-tobias-weiss-ai-xr/bayesian--statistics--research-181717.svg?logo=github)](https://github.com/tobias-weiss-ai-xr/bayesian-statistics-research)
  [![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
  [![CI](https://img.shields.io/github/actions/workflow/status/tobias-weiss-ai-xr/bayesian--statistics--research/validate.yml?label=CI&logo=github)](https://github.com/tobias-weiss-ai-xr/bayesian-statistics-research/actions/workflows/validate.yml)
  [![Decision-Making](https://img.shields.io/badge/Decision-Making-dm--research-blue.svg?logo=github)](https://github.com/tobias-weiss-ai-xr/dm-research) [![Robotics](https://img.shields.io/badge/Robotics-robotics--research-blue.svg?logo=github)](https://github.com/tobias-weiss-ai-xr/robotics-research) [![Learning](https://img.shields.io/badge/Learning-learning--research-blue.svg?logo=github)](https://github.com/tobias-weiss-ai-xr/learning-research)
</div>

> 📊 **Bayesian statistics research corpus:** inference, computation, priors, model
> selection, hierarchical, nonparametric, deep Bayesian, applications, and surveys —
> analyzed with the same pipeline as the other `*-research` corpus repos.

<p align="center">
  <img src="https://raw.githubusercontent.com/tobias-weiss-ai-xr/bayesian-statistics-research/main/assets/visualizations/category_distribution.png" alt="Teaser" width="600" />
</p>

---

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

## 📊 Corpus Statistics

**1,429 papers** across **8 categories**.  
Sources: **arXiv** 1,155 (80%) · **DOI** 254 (17%) · **Other** 20 (1%).  
Full paper list: [GitHub Pages site](https://tobias-weiss-ai-xr.github.io/bayesian-statistics-research).

### Top categories

| Category | Papers | Recent | |
|----------|--------|--------|-|
| computation | **415** | 0 | ████████████ |
| inference | **309** | 0 | ████████░░░░ |
| deep-bayesian | **206** | 0 | █████░░░░░░░ |
| hierarchical | **138** | 0 | ███░░░░░░░░░ |
| model-selection | **136** | 0 | ███░░░░░░░░░ |
| applications | **109** | 0 | ███░░░░░░░░░ |
| nonparametric | **106** | 0 | ███░░░░░░░░░ |
| priors | **10** | 0 | ░░░░░░░░░░░░ |


### By year

| Year | Papers | |
|------|--------|-|
| 2025 | 417 | ████░░░░░░░░ |
| 2026 | 1,012 | ████████████ |


### Momentum (hottest categories)

| Category | Total | Rate | Recent | Score |
|----------|-------|------|--------|-------|
| Applications | 109 | 9.1/mo | 100% | 100 |
| Computation | 415 | 34.6/mo | 100% | 100 |
| Deep Bayesian | 206 | 17.2/mo | 100% | 100 |
| Hierarchical | 138 | 11.5/mo | 100% | 100 |
| Inference | 309 | 25.8/mo | 100% | 100 |


### Trending keywords

| Keyword | Papers | Burst |
|---------|--------|-------|
| posterior | 578 | 1.00 |
| prior | 430 | 1.00 |
| uncertainty quantification | 191 | 1.00 |
| variational inference | 149 | 1.00 |
| model selection | 70 | 1.00 |
| hierarchical model | 42 | 1.00 |
| posterior approximation | 25 | 1.00 |
| normalizing flow | 24 | 1.00 |


### Top venues

| Venue | Papers |
|-------|--------|
| arXiv (Cornell University) | 39 |
| Zenodo (CERN European Organization for Nuclear Research) | 36 |
| Figshare | 8 |
| Open MIND | 8 |
| Research Square | 7 |
| Mathematics | 6 |
| ICML 2026 | 5 |
| ICLR 2026 | 4 |


### Research gaps (thinnest cells)

| Cell | Papers |
|------|--------|
| `inference/evaluation` | 1 |
| `inference/development` | 1 |
| `inference/systems` | 1 |
| `computation/application` | 1 |
| `hierarchical/application` | 1 |



*Generated 2026-08 by `scripts/standard_stats.py`.*

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
## 📊 Corpus Statistics

**1,429 papers** across **8 categories**.  
Sources: **arXiv** 1,155 (80%) · **DOI** 254 (17%) · **Other** 20 (1%).  
Full paper list: [GitHub Pages site](https://tobias-weiss-ai-xr.github.io/bayesian-statistics-research).

### Top categories

| Category | Papers | Recent | |
|----------|--------|--------|-|
| computation | **415** | 0 | ████████████ |
| inference | **309** | 0 | ████████░░░░ |
| deep-bayesian | **206** | 0 | █████░░░░░░░ |
| hierarchical | **138** | 0 | ███░░░░░░░░░ |
| model-selection | **136** | 0 | ███░░░░░░░░░ |
| applications | **109** | 0 | ███░░░░░░░░░ |
| nonparametric | **106** | 0 | ███░░░░░░░░░ |
| priors | **10** | 0 | ░░░░░░░░░░░░ |


### By year

| Year | Papers | |
|------|--------|-|
| 2025 | 417 | ████░░░░░░░░ |
| 2026 | 1,012 | ████████████ |


### Momentum (hottest categories)

| Category | Total | Rate | Recent | Score |
|----------|-------|------|--------|-------|
| Applications | 109 | 9.1/mo | 100% | 100 |
| Computation | 415 | 34.6/mo | 100% | 100 |
| Deep Bayesian | 206 | 17.2/mo | 100% | 100 |
| Hierarchical | 138 | 11.5/mo | 100% | 100 |
| Inference | 309 | 25.8/mo | 100% | 100 |


### Trending keywords

| Keyword | Papers | Burst |
|---------|--------|-------|
| posterior | 578 | 1.00 |
| prior | 430 | 1.00 |
| uncertainty quantification | 191 | 1.00 |
| variational inference | 149 | 1.00 |
| model selection | 70 | 1.00 |
| hierarchical model | 42 | 1.00 |
| posterior approximation | 25 | 1.00 |
| normalizing flow | 24 | 1.00 |


### Top venues

| Venue | Papers |
|-------|--------|
| arXiv (Cornell University) | 39 |
| Zenodo (CERN European Organization for Nuclear Research) | 36 |
| Figshare | 8 |
| Open MIND | 8 |
| Research Square | 7 |
| Mathematics | 6 |
| ICML 2026 | 5 |
| ICLR 2026 | 4 |


### Research gaps (thinnest cells)

| Cell | Papers |
|------|--------|
| `inference/evaluation` | 1 |
| `inference/development` | 1 |
| `inference/systems` | 1 |
| `computation/application` | 1 |
| `hierarchical/application` | 1 |



*Generated 2026-08 by `scripts/standard_stats.py`.*


## 📄 License

MIT — see [LICENSE](LICENSE).
