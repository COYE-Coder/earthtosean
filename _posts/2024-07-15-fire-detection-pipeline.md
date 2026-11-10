---
layout: post
title: "Fire Detection: From Research to Operations"
date: 2024-07-15
description:
tags: [remote-sensing, deep-learning, fire, data-fusion]
categories: [Science]
---

While I was at [BAERI](https://baeri.org/) on a NASA Ames contract, I built a data fusion framework for satellite-based fire detection. The model combines geostationary imagery with polar-orbiting imagery. Fusing the two lets the model detect fires in near real-time. I also integrated the pipeline with AWS so it could keep up with full-disk geostationary imagery at an operational cadence.

After I moved on, a close friend of mine took the model and built an [operational pipeline](https://github.com/hunterad93/firenet) around it on Google Cloud Platform. Here is how it works:

- Cloud Functions ingest and reproject the imagery.
- A containerized Cloud Run instance runs inference. It loads the raster stack, passes it through the PyTorch UNET, and writes the classifications back as a georeferenced band.
- High-confidence pixels are grouped into fire polygons using connected components.
- The polygons are uploaded to BigQuery and served to a [live map](https://lnkd.in/gsQBDZYq) through Flask.

The pipeline is modular. New model weights go in as a `.pt` file, and a new region of interest goes in as a NetCDF template. The model needs retraining, but the infrastructure is solid. Seeing my research code turn into something operational has been pretty cool, but I can't take credit for the hard part.
