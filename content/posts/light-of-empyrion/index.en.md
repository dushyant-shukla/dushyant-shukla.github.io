---
title: "Light of Empyrion"
subtitle: ""
date: 2025-11-02T12:09:13-08:00
lastmod: 2025-11-02T12:09:13-08:00
draft: false
authors: ["Dushyant"]
description: ""

tags: []
categories: ["archive"]
series: []

hiddenFromHomePage: false
hiddenFromSearch: false

featuredImage: "light-of-empyrion.gif"
featuredImagePreview: ""

toc:
  enable: false
math:
  enable: false
lightgallery: false
license: ""
---

<!--more-->

Light of Empyrion is a 2D tower-defense game developed for GAM-541 coursework as part of the Master's of Computer Science program at *DigiPen Institute of Technology* between Jan. 2020 - Apr. 2020. The game was written using a custom game-engine written from scratch using **C++** and **OpenGL**.

# Synopsis

*We are inspired by the Path Of Exile blight league to make an ARPG game with both engaging player skills and tower defenses elements. You play as an oath keeper of Empyrion that holds the front line from attacks launched by Abyss monsters. Time is ticking and monsters are flooding. You are to kill monsters and earn coins as fast as possible to get the finest skills and upgrades, and build tower wisely to gain an upper hand on the battlefield. Go! Our oath keeper! For Empyrion!*

</br>
<!-- {{ video src="/videos/light-of-empyrion.mp4" type="video/mp4" preload="auto" }} -->

Catch a glimpse of the gameplay below:

</br>

{{< youtube u656akVYJ9Y >}}

</br>
</br>

I worked on the game project as part of a four member team:

{{< figure src="credits_786.png" title="Light of Empyrion (Credits)" >}}

</br>

As an engine and gameplay programmer, the following were my main contributions:

- Engineered a type-safe, cache-aware Entity Component System (ECS) leveraging C++ templates and data-oriented design to manage large-scale game state efficiently.
- Built a C++ template-based publish–subscribe event system to support decoupled, scalable inter-system communication.
- Implemented a modular inventory and ability system using virtual inheritance, enabling flexible composition of player skills.

</br>

The source code is available at *https://github.com/dushyant-shukla/light-of-empyrion*.