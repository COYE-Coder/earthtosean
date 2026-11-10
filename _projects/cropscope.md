---
layout: page
title: Annual Cropland Extent
description: 30m annual cropland mapping across North American grasslands (1996–2021) using deep learning, published in Ecological Indicators.
img: assets/img/ace_fig5_active_cropland_change.png
importance: 1
category: research
tags: [remote-sensing, deep-learning, land-use-change]
---

## Annual Cropland Extent

Developed a 30-meter resolution dataset capturing annual "active" and "cumulative" cropland from 1996 to 2021 across the central grasslands of North America. The pipeline uses an Attention U-Net convolutional neural network trained on Landsat imagery.

{% include figure.liquid loading="eager" path="assets/img/ace_fig4_cumulative_active_trends.png" title="Cumulative and active cropland trends" class="img-fluid rounded z-depth-1" caption="Fig. 4 — Bias-adjusted cumulative and active cropland change estimates in Canada, the United States, and Mexico from 1996 to 2021." %}

{% include figure.liquid loading="eager" path="assets/img/ace_fig5_active_cropland_change.png" title="Changes in active cropland area" class="img-fluid rounded z-depth-1" caption="Fig. 5 — Changes in active cropland area across the study region over the entire study period (left) and five-year epochs (right). Red indicates increased active cropland; blue indicates decrease." %}

Key findings:
- While active cropland showed no significant change, the **cumulative cropland footprint expanded by 17%** relative to the 1996–2000 baseline
- New conversion or recultivation occurred at a consistent rate of **~1 million ha per year**
- Mexico showed the largest relative gain, expanding by nearly 48%

**Published in:** Carter, S., Morford, S.L., Tack, J.D., et al. (2025). *Annual cultivated extent and agricultural land use expansion across the central grasslands of North America, 1996–2021.* Ecological Indicators, 178, 113968. [DOI](https://doi.org/10.1016/j.ecolind.2025.113968)

**Interactive map:** [Cropland Extent Map](https://wlfw-um.projects.earthengine.app/view/cropland-extent-map) — explore the dataset in Google Earth Engine.

**GitHub:** [COYE-Coder/Annual-Cropland-Extent](https://github.com/COYE-Coder/Annual-Cropland-Extent)

**Tech stack:** TensorFlow, Attention U-Net, Landsat, Google Earth Engine

**Built at:** Numerical Terradynamic Simulation Group (NTSG), University of Montana
