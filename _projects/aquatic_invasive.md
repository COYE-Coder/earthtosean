---
layout: page
title: Aquatic Invasive Species
description: ML-based spatial risk assessment for aquatic invasive species in Northwest Montana.
img: assets/img/thumb_aquatic_invasive.jpeg
importance: 4
category: research
tags: [remote-sensing, ecology, machine-learning]
---

## Aquatic Invasive Species Monitoring

{% include figure.liquid loading="eager" path="assets/img/ais_fig1_study_area.jpeg" class="img-fluid rounded z-depth-1" caption="Study area: upper Flathead River system, northwestern Montana, with land surface temperature shown across hydrologic units." %}

My master's thesis at the University of Montana. I built a workflow that generates rapid spatial risk assessments for aquatic invasive species using occurrence data, satellite-derived environmental variables, and an ensemble of five machine learning algorithms.

We tested it on Rainbow Trout (*Oncorhynchus mykiss*) invasion in the upper Flathead River system — a well-studied, climate-driven species invasion in northwestern Montana. The ensemble approach achieved 87% accuracy on 30-fold cross-validated datasets. Temperature came out as the dominant predictor, which matched the existing ecological literature on RBT habitat suitability.

We wanted to build something that could transfer across species and ecosystems — a framework that resource managers could adapt without starting from scratch every time.

**Published in:** Carter, S., van Rees, C.B., Hand, B.K., et al. (2021). *Testing a Generalizable Machine Learning Workflow for Aquatic Invasive Species on Rainbow Trout (Oncorhynchus mykiss) in Northwest Montana.* Frontiers in Big Data, 4. [DOI](https://doi.org/10.3389/fdata.2021.734990)

**Tech stack:** Python, Rasterio, Geopandas, MODIS, Landsat, SMAP, Random Forest, XGBoost

**Built at:** NTSG, University of Montana
