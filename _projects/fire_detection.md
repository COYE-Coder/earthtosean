---
layout: page
title: Fire Detection
description: GEO-LEO satellite imagery fusion and deep learning for near real-time wildfire detection, built at BAERI under a NASA Ames contract.
img: assets/img/thumb_fire_detection.png
importance: 3
category: research
tags: [remote-sensing, deep-learning, fire, data-fusion]
---

## Fire Detection via GEO-LEO Imagery Fusion

At BAERI, under a NASA Ames Research Center contract, I designed and built a data fusion framework combining geostationary (GOES) and polar-orbiting (MODIS/VIIRS) satellite imagery for fire detection in near real-time. I also integrated the model with AWS for operational processing of high-fidelity geostationary imagery.

The core challenge was combining two complementary data sources: GOES provides images every few minutes but at coarse spatial resolution, while MODIS and VIIRS offer finer detail but only a few overpasses per day. The fusion model I developed bridges that tradeoff.

A friend of mine later took the model and [operationalized it into a full GCP pipeline](https://github.com/hunterad93/firenet) — Cloud Functions for imagery ingestion, Cloud Run for inference, BigQuery for storing fire polygon outputs, and a Flask server for a [live map](https://lnkd.in/gsQBDZYq). The pipeline is modular: swapping in retrained weights or a new region of interest doesn't require changing infrastructure.

**Tech stack:** PyTorch, GOES, MODIS/VIIRS, AWS, data fusion

**Built at:** BAERI / NASA Ames Research Center
