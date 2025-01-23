---
title: "Google Summer of Code"
authors:
- admin
date: "2020-07-07T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2024-01-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["0"]

# Publication name and optional abbreviated publication name.
publication: "R Packages"
publication_short: "Packages"

# Summary. An optional shortened abstract.
summary: >
  Google Summer of Code (GSoC) is an international program in which Google awards stipends to contributors who successfully complete a free and open-source software coding project during the summer.

tags:
- Mathematics
- Programming
- CRAN
- R
featured: false

# - name: Custom Link
#   url: http://example.org
# url_pdf: files/example-preprint.pdf  # Alternatively, you can use this line for the direct PDF link.
# url_code: '#'
# url_dataset: '#'
# url_poster: '#'
# url_project: ''
# url_slides: ''
# url_source: '#'
# url_video: '#'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: ''
  focal_point: ""
  preview_only: false
---

During the summer of 2018 and 2019, I took part in Google Summer of Code (GSoC). A brief summary of each project is given below. All the code, as it was during the projects is avaiable, [GSoC](https://github.com/AndrewC1998/GSoC), though the repositories noted later have been updated since the end of the project.

## 2018

Over the summer of 2018, I worked with [Professor David Matteson](https://stat.cornell.edu/people/faculty/david-s-matteson) at Cornell University and [Professor Rebecca Killick](http://www.lancs.ac.uk/~killick/) at Lancaster University to implement a new R package: `changepoint.online`. Although this work officially ended in August, I continued developing this project and left an active Github for other researchers to extend upon. Further work, such as the development of online non-parametric changepoint detection, is now in progress by other researchers at Lancaster University.

Throughout the summer, I used R, C++, and C to create the R package while working from Lancaster University. This opportunity allowed me to work in an office where new statistical research was being developed, providing exposure to areas of statistics not covered by my degree’s curriculum.

The project lead to the development of an R package that moved beyond the existing R packages available that were for offline changepoint detection, to one that is for online changepoint detection. The package implements traditional “resetting” methodology, meaning once a change occurs, previous data is forgotten. This work brought the accuracy benefits of offline methodology to the online setting, allowing users to implement state-of-the-art offline methods in a computationally efficient manner for online use.

The repository can be found at: [changepoint.online](https://github.com/rkillick/changepoint.online)

## 2019

In 2019, I returned again to complete a second project with R and GSoC. This time work was developed that detected changes in statistical properties of a time series. Much research had focused on changes in mean and variance in time series, often assuming that the error process is independent. However, more users of existing packages, like `changepoint`, faced problems using real-world data due to the dependence structures present. This project addressed this issue by adding new functionality to the popular CRAN package `changepoint`.

The project implemented several changes in second-order structure algorithms, including the commonly used AR(p) structure, and changes in variance and autocovariance (rather than spectra) through the Locally Stationary Wavelet (LSW) model, a model that I have used in other aspects of my research since.

The LSW process can capture many dependence structures. Of particular interest in changepoint applications is the fact that a piecewise second-order time series will have its structure encoded as piecewise constant sequences in the local wavelet periodogram — a feature noted by Cho and Fryzlewicz. Using the LSW framework for changepoint methods, we do not need to prescribe the structure of the dependence beyond the requirements of the LSW definition. A barrier to the current implementation in `wbsts` is that most practitioners are familiar with variance and autocorrelation but not necessarily spectral decompositions—let alone time-varying spectra. For this reason, we seek to implement a method to detect changes in variance and covariance through the non-parametric LSW model instead of a change in spectra.

This project impacted several dependencies on other projects. Please read the news within each repository for exact changes. The updated repositories can be found:

- [changepoint](https://github.com/AndrewC1998/changepoint)
- [changepoint.np](https://github.com/AndrewC1998/changepoint.np)
- [EnvCpt](https://github.com/AndrewC1998/EnvCpt)
