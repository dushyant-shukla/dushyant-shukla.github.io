# Cassini Engine


<!--more-->

Cassini is a real-time 3D game engine I began developing in June 2024. It’s still in the early stages, with no public release yet, but each iteration brings it closer to something I can share.

# Why 'Cassini'?

The name is an homage to the 17th century engineer, astronomer, and mathematician, Jean-Dominique Cassini. The name also takes an inspiration from the [Cassini-Huygens](https://science.nasa.gov/mission/cassini/) space-research mission by NASA, the European Space Agency, and the Italian Space Agency.

# Why make a game engine?

Well, the goal is simple: to learn. I want to understand what’s really happening beneath the surface, the systems and techniques that make highly interactive and deeply immersive game worlds come alive. This engine is my way of lifting the curtain and building those fundamentals myself.

# Engine features

The engine is written in C++. I am still working on the core systems (sub-systems) of the engine, however, some interesting features include:
* A rendering API agnostic abstraction layer (currently only supports Vulkan)
* Physically based rendering pipeline using the metallic‑roughness workflow with glTF asset support.
* Bindless rendering to reduce draw‑call overhead and improve GPU resource access efficiency.
* Asynchronous resource loading to prevent stalls and improve runtime performance.

</br>

{{< figure src="cassini_pbr_ii.png" title="Metallic Roughness Workflow" width="75%" >}}

</br>

{{< figure src="cassini-async-loading.gif" title="Asynchronous Resource Loading In Action (slowed down for capturing the effect)" width="75%" >}}
