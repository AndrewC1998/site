---
title: "Identifiability of Hawkes Processes"
authors:
  - admin
  - "Ed Cohen"
author_notes:
  - "Lead author"
  - "Supervisor & co-author"
date: "2025-11-30T00:00:00Z"

# Schedule page publish date (NOT publication's date).
publishDate: "2025-11-22T00:00:00Z"
lastmod: "2025-11-16T00:00:00Z"
doi: ""

featured: true
math: true

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["7"]

# Publication name and optional abbreviated publication name.
publication: "PhD thesis chapter, Imperial College London (Department of Mathematics)"
publication_short: "PhD thesis chapter"

# Summary. An optional shortened abstract.
summary: >
  A full identifiability theory for exponential Hawkes processes, combining
  closed-form moment recursions (positive and negative), analytic Fisher
  information, and practical Jacobian and Fisher based diagnostics to
  detect ill-conditioning in both univariate and multivariate models.

tags:
  - Hawkes processes
  - Identifiability
  - Fisher information
  - Moments
  - Negative moments
  - Inference
  - Multivariate point processes
categories:
  - PhD Thesis

# Optional external links shown as buttons.
links:
  - name: "Chapter PDF"
    url: "paper.pdf"  # replace with the final URL

# Featured image
# To use, add an image named `featured.jpg/png` to this page's folder.
image:
  caption: "Identifiability map for an exponential Hawkes model: well-identified vs ridge-like non-identifiability."
  focal_point: ""
  preview_only: false

projects: []
---

## Overview

This chapter asks a simple but crucial question: when are Hawkes parameters uniquely recoverable from data?

Working with stationary univariate and multivariate exponential-kernel Hawkes processes, this work developed parallel moment-based and likelihood-based frameworks for local identifiability. The chapter introduces new theory for the conditional intensity’s positive and negative moments, derives closed-form Fisher information for the univariate case, and builds practical diagnostics that flag nearly singular regions of parameter space before or during inference.

This work was carried out as part of my PhD thesis under the supervision of [**Dr. Ed Cohen**](https://profiles.imperial.ac.uk/e.cohen).

![Illustration of a well-identified likelihood surface (left) versus a ridge-like, nearly non-identifiable surface (right).](identifiability_map.png)

## Key contributions

- **Closed-form moment theory (positive & negative).**  
  - Recursive and Bell-polynomial formulas for stationary positive moments \( \mathbb{E}[\lambda^n] \).  
  - New negative-moment theory \( \mathbb{E}[\lambda^{-n}] \) via Laplace / Mellin representations and continued fractions, including computable bounds and asymptotic expansions.

- **Moment-based identifiability via Jacobians.**  
  - Construction of a low-order moment map \( \Psi(\theta) \) for the exponential Hawkes, based on a small collection of stationary moments of the intensity.  
  - Explicit Jacobian \( \mathcal{J}(\theta) \), its determinant, and smallest singular value \( \sigma_{\min}(\mathcal{J}) \) as conditioning diagnostics.  
  - Maps out parameter regions where \((\mu,\alpha,\beta)\) are weakly distinguished (e.g. near the Poisson edge or as \( \alpha \uparrow \beta \)).

- **Fisher-information-based criteria.**  
  - Closed-form Fisher information for the univariate exponential Hawkes, including exact integral representations and fast approximations.  
  - Determinant bounds and per-unit-time Fisher summaries that give quick *certificates* of local identifiability and highlight ill-conditioned directions.

- **Multivariate extension via Bartlett spectra.**  
  - Identifiability map for \(M\)-dimensional Hawkes based on the stationary mean and Bartlett spectrum \(S(\omega)\).  
  - Shows that stacking \( \Lambda \) with \( S(\omega_1), S(\omega_2) \) at two non-zero frequencies yields a generically full-rank identification map under mild conditions.

## Methods and diagnostics

- **Moment ODEs and generators.**  
  Derivations use the Markovian representation of the exponential kernel and the infinitesimal generator to obtain ODEs for \( \mathbb{E}[\lambda^n] \), mixed moments \( \mathbb{E}[N^k \lambda^j] \), and cross-moments. These ODEs close at each order, yielding explicit recursions.

- **Laplace-based negative moments.**  
  The Laplace transform \( \phi(s) = \mathbb{E}[e^{-s\lambda}] \) satisfies a scalar ODE, leading to integral formulas and asymptotic expansions for \( \mathbb{E}[\lambda^{-n}] \), plus sharp bounds
  \[
    (\mathbb{E}[\lambda])^{-n} \le \mathbb{E}[\lambda^{-n}] \le \mu^{-n}.
  \]

- **Jacobian singular values and determinant.**  
  Conditioning is quantified via the smallest singular value and determinant of the moment Jacobian. The figure below shows \(|\det \mathcal{J}(\mu,\alpha,\beta)|^2\) across a grid in \((\mu,\alpha)\) for several fixed \(\beta\), highlighting regions where the moment map becomes nearly singular.

  ![Grid of heatmaps over \((\mu,\alpha)\) for several fixed \(\beta\), showing \(|\det \mathcal{J}|^2\) and exposing Poisson-like and near-critical regimes where the moment map is ill-conditioned.](identifiability_heatmap_absdet.png)

- **Fisher information and bounds.**  
  Exact Fisher entries are expressed in terms of kernel integrals \(K_1,K_2\) and negative moments. When those are expensive, closed-form lower bounds on \( \det \mathcal{I}(\theta) \) and simple approximations in terms of \( \mathbb{E}[\lambda] \), \( \mathrm{Var}(\lambda) \), and \( \mathbb{E}[\lambda^{-1}] \) provide fast screening tools.

## Selected findings

- **Empirical vs theoretical moments.**  
  Monte Carlo experiments over large grids in \( (\mu,\alpha,\beta) \) confirm excellent agreement for positive moments up to order 6 and for several negative moments, validating the analytic recursions and Laplace formulas.

- **Negative-moment ratios and asymptotics.**  
  The ratio
  \[
    R_n = \frac{\mathbb{E}[\lambda^{-(n+1)}]}{\mathbb{E}[\lambda^{-n}]}
  \]
  converges rapidly to \( 1/\mu \), matching the continued-fraction theory and providing a clean asymptotic picture of the negative-moment cascade.

- **Ill-conditioned regimes.**  
  Both Jacobian and Fisher-based diagnostics agree on problematic regions:
  - the **Poisson edge** \( \alpha \downarrow 0 \), where excitation vanishes and Hawkes parameters degenerate to a simple Poisson rate;  
  - the **near-critical ridge** \( \alpha \uparrow \beta \), where \((\alpha,\beta)\) become nearly collinear in the likelihood and long-memory effects dominate.  
  In these regimes, small perturbations in the data can cause large swings in the MLE, even with long observation windows.

- **Multivariate identifiability.**  
  For \(M\)-dimensional exponential Hawkes with non-degenerate decay rates and $\rho(\Gamma) \le 1$, augmenting the mean with two non-zero-frequency spectra yields a generically full-rank identification map, giving a principled route to identifiability in higher dimensions and guiding practical experiment design.

## Reference

```bibtex
@phdthesis{Connell2025Identif,
  author = {Andrew M. Connell and Ed Cohen},
  title  = {Identifiability of Hawkes Processes},
  school = {Imperial College London},
  year   = {2025},
  note   = {PhD thesis chapter: Identifiability}
}
```
