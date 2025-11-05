---
title: "Moment Shadow Mapping"
subtitle: ""
date: 2025-11-02T13:30:28-08:00
lastmod: 2025-11-02T13:30:28-08:00
draft: false
authors: ["Dushyant"]
description: ""

tags: [OpenGL, Graphics]
categories: ["archive"]
series: []

hiddenFromHomePage: false
hiddenFromSearch: false

featuredImage: "soft-shadows.gif"
featuredImagePreview: ""

toc:
  enable: true
math:
  enable: false
lightgallery: false
license: ""
---

<!--more-->

Moment Shadow Mapping (MSM) is a rendering technique for rendering soft-shadows in real-time. This project was my attempt at implementing the [Hamburger 4MSM paper](https://cg.cs.uni-bonn.de/backend/v1/files/publications/MomentShadowMapping.pdf) for the *CS-562: Advanced Real-Time Rendering Techniques* coursework I took during my time at *DigiPen Institute of Technology*.

## An overview of the technique

The technique builds on the ubiquitous two-pass shadow map algorithm, where:
* Instead of storing the depth '*z*' in a single channel shadow map, we store (*z, z^2, z^3, z^4*) in a four channel shadow map.
* The four channel shadow map is then blurred by running it through a Gaussian blur filter.
* During the lighting pass:
  * We calculate pixel depth, *zf*, as in regular two-pass shadow mapping.
  * Next, we calculate light depth, as in regural two-pass shadow mapping, by projecting the pixel onto the shadow map and extract the (*z, z^2, z^3, z^4*) values, which are now blurred.
  * Now instead of comparing the two depth values, we run *zf* and (*z, z^2, z^3, z^4*) values through the MSM algorithm to calculate a full range of shadow factor between [0, 1].

</br>

## Results

{{< figure src="msm_shadowmap_moments.gif" title="MSM: Capturing four different moments" width="50%" >}}

</br>

{{< figure src="msm_shadowmap_blurred.gif" title="MSM: Blurring the shadow map" width="50%" >}}

</br>

{{< figure src="msm-perspective-combined.png" title="Soft Shadows: Using Perspective Projection for light's viewing volume (point lights)" width="100%" >}}

</br>

{{< figure src="msm-ortho-combined.png" title="Soft Shadows: Using Orthographic Projection for light's viewing volume (directional lights)" width="100%" >}}

</br>

| Hard Shadows | Anti-Aliasing with MSM |
| ------ | ----------- |
| {{< figure src="hard-shadows.png" title="" width="" >}}   | {{< figure src="msm-anti-aliasing.png" title="" width="" >}} |

<p style="text-align: center;"><b>MSM soft shadows with just enough blur to achieve anti-aliasing</b></p>

</br>

| Gaussian Blur Passes = 2, Kernel Size = 5 | Gaussian Blur Passes = 10, Kernel Size = 11 |
| ------ | ----------- |
| {{< figure src="msm-pass-2-size-kernel-5.png" title="" width="" >}}   | {{< figure src="msm-pass-10-size-kernel-11.png" title="" width="" >}} |

<p style="text-align: center;"><b>MSM soft shadows with varied amount of shadow map blurring</b></p>

</br>

## Future work

Implementing the blur filter for the shadow map in the fragment shader hampered the frame rate. Using compute shaders would be better for performance.

</br>

---




