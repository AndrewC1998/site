---
title: "Google Summer of Code 2019 — Second-order changes in time series (R changepoint)"
authors:
- admin
date: "2020-07-07T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2024-01-01T00:00:00Z"

publication_types: ["0"]

publication: "R Packages"
publication_short: "Packages"

summary: >
  In 2019 I enhanced the R ecosystem (notably `changepoint`) to detect changes in second-order structure—variance and autocovariance—under dependence, using AR(p) models and the Locally Stationary Wavelet (LSW) framework.

tags:
- Mathematics
- Programming
- CRAN
- R
featured: false

links:
  - name: GSoC 2019 Project Page
    url: https://summerofcode.withgoogle.com/archive/2019/projects/4647488932282368
  - name: Repository — changepoint
    url: https://github.com/AndrewC1998/changepoint
  - name: Repository — changepoint.np
    url: https://github.com/AndrewC1998/changepoint.np
  - name: Repository — EnvCpt
    url: https://github.com/AndrewC1998/EnvCpt

image:
  caption: ""
  focal_point: ""
  preview_only: false
---

In 2019 I returned to GSoC to develop methods for detecting changes in statistical properties of a time series beyond mean/variance under independence. Many users of existing packages encountered real-world dependence structures, so this project added functionality to handle dependence within the popular CRAN package `changepoint`.

Contributions included algorithms for changes in second-order structure with AR(p) dependence, and detection of changes in variance and autocovariance via the Locally Stationary Wavelet (LSW) model. The LSW framework captures a wide range of dependence structures; crucially, piecewise second-order structure becomes piecewise constant in the local wavelet periodogram (as noted by Cho & Fryzlewicz), enabling non-parametric change detection without prescribing a specific dependence form.

To improve usability for practitioners familiar with variance/autocorrelation (but not time-varying spectra), the work targets variance/covariance changes through LSW rather than requiring spectral decompositions. See the linked repositories for detailed NEWS and updates.
