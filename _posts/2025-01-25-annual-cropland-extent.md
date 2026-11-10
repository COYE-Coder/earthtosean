---
layout: post
title: "Annual Cropland Extent (ACE)"
date: 2025-01-25
description:
tags: [remote-sensing, deep-learning, google-earth-engine, land-use-change]
categories: [Science]
---

My main project at [Working Lands for Wildlife](https://www.wlfw.org/) was the Annual Cropland Extent (ACE) dataset. ACE maps cropland across the central grasslands of North America at 30-meter resolution for every year from 1996 to 2021. The [paper](https://doi.org/10.1016/j.ecolind.2025.113968) is published in Ecological Indicators, and the [interactive map](https://wlfw-um.projects.earthengine.app/view/cropland-extent-map) is live on Earth Engine.

The core model is an Attention U-Net trained on Landsat composites. For each pixel, it classifies whether the land was actively cultivated in a given year. We ran it across roughly 10 million square kilometers for 26 years, which works out to about 260 million classified square kilometers. After bias correction, the model achieved about 90% accuracy. That is comparable to other cropland products, although I'm still not sure what "accuracy" really means when you evaluate an image model at this scale.

{% include figure.liquid loading="eager" path="assets/img/ace_fig5_active_cropland_change.png" class="img-fluid rounded z-depth-1" caption="Changes in active cropland area across the study region, 1996–2021. Red indicates increase; blue indicates decrease." %}

The code is on [GitHub](https://github.com/COYE-Coder/Annual-Cropland-Extent) if you want to dig into the pipeline. It's set up for demonstration purposes, but it should give you a good sense of the approach.
