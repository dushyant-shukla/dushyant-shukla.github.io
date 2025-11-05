# Deferred Shading


<!--more-->

Forward shading, while being easy to understand and implement, is quite heavy on performance. Consider scenarios below that depict limitations of forward shading:
* For a scene with a high depth complexity, forward shading tends to waste a lot of fragment shader runs as fragment outputs are overwritten.
* For a scene with multiple lights, lighting calculations are performed for every geometry in the scene for every light.

Deferred shading overcomes these issues with a different rendering technique.

I implemented this project for the <i>**CS-562: Advanced Real-Time Rendering Techniques**</i> coursework I took during my time at *[DigiPen Institute of Technology](https://www.digipen.edu/)*.

The renderer for the project was written using **C++**, **OpenGL**, and **GLSL**.

## An overview of the technique
Deferred shading consists of two passes:
1. **Geometry Pass:** In this pass, we render the scene once and store all kinds of geometric information from the scene into a collection of textures collectively known as the G-Buffer. These textures can store information such as vertex positions, color information, normal vectors, and more.

{{< figure src="scene-g-buffer.png" title="Contents of G Buffer at the end of Geometry Pass" width="80%" >}}

2. **Lighting Pass:** The geometric information stored in the G-Buffer is then retrieved later for use in lighting calculations in this second pass. In lighting pass, we render the scene with a FULL SCREEN QUAD, and perform lighting calculations for each fragment using the information stored in G-Buffer.
At this point, it should be noted that by the time information is written into the G-Buffer, the depth test has already been performed. Therefore, any fragment that ends up in the G-Buffer is the actual fragment information that will be finally displayed for the screen pixel. Thus, for each screen pixel that is processed in the lighting pass, lighting calculations are performed only once.

</br>

## Results

Deferred shading can provide significant optimizations for a scene with many lights. This allows us to render scenes with hundreds or even thousands of lights with an acceptable framerate, something which would not be possible with forward rendering.

{{< figure src="scene-point-light-positions.png" title="Scene depicted with positions of 3578 point lights" width="80%" >}}

</br>

{{< figure src="scene-point-lights.png" title="Scene light ed with 3578 point lights while main t aining a framerate of ~25 FPS" width="80%" >}}

</br>

---
