---
title: "Bloom"
subtitle: ""
date: 2025-11-02T11:12:24-08:00
lastmod: 2025-11-02T11:12:24-08:00
draft: false
authors: ["Dushyant"]
description: ""

tags: [OpenGL]
categories: ["archive"]
series: []

hiddenFromHomePage: false
hiddenFromSearch: false

featuredImage: "vehicle-ii.gif"
featuredImagePreview: ""

toc:
  enable: false
math:
  enable: false
lightgallery: false
license: ""
---

<!--more-->

Bloom is a post processing technique used to give bright light sources and brightly lit regions of the scene a glow effect. This effect results in the light bleeding around such brightly lit regions, giving an illusion usually associated with intense brighness.

We can see the effect in work in the picture above. Turning on the effect adds a subtle glow to the light sources on the vehicles body.

The project was implemented following a guide from Nvidia on [real-time glow](https://developer.nvidia.com/gpugems/gpugems/part-iv-image-processing/chapter-21-real-time-glow).