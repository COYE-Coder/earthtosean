---
layout: post
title: "Landscape Explorer"
date: 2024-09-10
description:
tags: [remote-sensing, data-engineering, google-earth-engine]
categories: [Science]
---

While I was at [Working Lands for Wildlife](https://www.wlfw.org/), I did the data engineering for [Landscape Explorer](https://www.landscapeexplorer.org/). The tool lets you compare historic aerial imagery (going back to the 1950s) with recent satellite imagery across the western US. [WLFW wrote about it here](https://www.wlfw.org/landscape-explorer-map-shows-how-much-the-west-has-changed-since-the-1950s/).

{% include figure.liquid loading="eager" path="assets/img/landscape_explorer_screenshot.png" class="img-fluid rounded z-depth-1" caption="Landscape Explorer — comparing historic and current aerial imagery of the same location." %}

Most of the processing happened in Google Earth Engine. Getting decades of imagery into a consistent, servable format was a headache. The projections differed, the metadata was inconsistent, and the coverage had gaps. These are standard problems with historic geospatial data, but they took me a while to work through.

I took two lessons away from this project.

First, design for idempotency. At this scale, batch jobs fail constantly. If your scripts can't pick up where they left off, you end up re-processing data you have already handled, and that means days of wasted compute.

Second, link each downloading script to its repo. Months later, you will need to trace which script produced which file.

If you want to see how much the West has changed, go poke around at [landscapeexplorer.org](https://www.landscapeexplorer.org/). The Great Plains conversions are especially striking.
