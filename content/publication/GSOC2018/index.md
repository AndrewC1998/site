---
title: "Google Summer of Code 2018 — changepoint.online"
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
  Google Summer of Code (GSoC) is an international program in which Google awards stipends to contributors who successfully complete a free and open-source software coding project during the summer. In 2018 I implemented `changepoint.online`, bringing offline changepoint accuracy to the online setting.

tags:
- Mathematics
- Programming
- CRAN
- R
featured: false

# Optional external links shown as buttons.
links:
  - name: GSoC 2018 Project Page
    url: https://summerofcode.withgoogle.com/archive/2018/projects/4854573080510464
  - name: Repository — changepoint.online
    url: https://github.com/rkillick/changepoint.online

# Featured image
# To use, add an image named `featured.jpg/png` to this page's folder.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

During the summer of 2018, I worked with [Professor David Matteson](https://stat.cornell.edu/people/faculty/david-s-matteson) at Cornell University and [Professor Rebecca Killick](http://www.lancs.ac.uk/~killick/) at Lancaster University to implement a new R package: `changepoint.online`. Although the GSoC period ended in August, I continued developing the project and left an active GitHub repository for other researchers to extend. Further work, such as online non-parametric changepoint detectionm is now in progress at Lancaster University.

I used R, C++, and C to create the package while working from Lancaster University, gaining exposure to new statistical research beyond my degree curriculum.

The project moved beyond existing *offline* changepoint R packages by providing an *online* framework. It implements traditional “resetting” methodology (after a change, prior data is forgotten) and brings the accuracy benefits of offline methods to the online setting in a computationally efficient way.
