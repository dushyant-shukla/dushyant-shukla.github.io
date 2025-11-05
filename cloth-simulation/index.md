# Physically Based Cloth Simulation


<!--more-->

</br>

The project demosntrates simulation of a physically based cloth. Effects of basic external forces such as gravity, and wind forces are exhibited. Intereraction of the cloth with another body is also demonstrated.

The project uses a custom 3D renderer I wrote using C++ programming language and Vulkan graphics API.

# Simulating the Cloth

Geometry for the cloth is build using a grid of particles:
- The arrangement of the particles is triangulated to convert them into a mesh format suitable for rendering through a graphics pipeline.
- Normals vectors and UV coordinates for the geometry are also calculated during the triangulation process every frame.

# Particle Physics

Every particle in the grid has certain properties such as position, mass, acceleration which define their behavior under the external forces.
- The change in position of particles is integrated using the Verlet integration.
- Cloth particles are held in their place using a set of constraints they satisfy with their most immediate neighbors. This also gives a spring like effect to the cloth particles under the influence of external forces.
- Cloth particles are also subjected to interaction with external bodies, a spherical ball in this case. As the cloth particles are integrated and updated every frame, we check if they are inside the ball. If the particles are found to be inside the ball, they are projected to the surface of the ball. These are rudimentary checks, therefore, it is possible for the sphere to 'slip through' if it is small enough compared to the distance between the grid particles.

</br>

The cloth in the demonstration below is build with 55 X 45 particles arranged in a 14 X 10 grid:

</br>

{{< youtube 0WVHB7P3xjo >}}

</br>

---
