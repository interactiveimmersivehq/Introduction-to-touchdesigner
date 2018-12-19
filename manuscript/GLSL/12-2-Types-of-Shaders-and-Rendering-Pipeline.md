## *12.2 Types of Shaders and Rendering Pipeline*

The two main types of shaders that can be programmed in TouchDesigner are the Vertex shader and the Pixel (or Fragment) shader. In a standard rendering pipeline, they are processed in that order, as can be seen in the diagram below:

![GLSL Pipeline](images/12.2/pipeline.png)

There is also a geometry shader that can be applied between the Vertex and Pixel shaders for layered rendering and transform feedbacks, but it is not used commonly.

In the above pipeline, the application passes the vertex and primitive data to the GPU. This includes information such as vertex position, texture coordinate, color, normal, etc. This information can be programatically processed and worked with by using a Vertex shader.

When the Vertex shader has finished processing the vertex and primitive data, the geometry is rasterized. During this process, the geometry goes through various stages such as clipping, culling, transformations to window space, etc. These stages prepare fragments that will be processed by the Pixel shader.

The Pixel shader takes these fragments, processes them, and outputs the color and depth data for each pixel.

For a more in-depth look at the render pipeline, there is a more thorough explanation on the OpenGL website:

[http://www.opengl.org/wiki/Rendering_Pipeline_Overview](http://www.opengl.org/wiki/Rendering_Pipeline_Overview)