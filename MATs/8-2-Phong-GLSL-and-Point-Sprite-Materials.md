
### *8.2 Phong, GLSL, and Point Sprite Materials*

The three most used MATs are:

* the Phong MAT

* the GLSL MAT

* the Point Sprite MAT


The general uses of these three MATs will quickly be covered in this section. These are three very different Operators, and cover many shading and material needs.

The Phong MAT is the most common material Operator. It is responsible for applying texture to 3D geometry. There are a variety of maps that can be applied, such as Color, Bump, Specular, Diffuse, and more. The Phong MAT can mix and match Ambient, Diffuse, Specular, Emit, and Constant lighting. Open example 'Phong.toe'. In this project there are two very simple examples of the Phong MAT. The first uses the texture's alpha to create a transparent box. The second sets the Emit Light of 1,1,1 to fully illuminate the object regardless of the lighting condition. There will be many examples of the Phong MAT when it is put to use the examples section.

The GLSL MAT is used to create custom materials using the OpenGL Shading Language (GLSL for short). GLSL is a fantastic programming language that can create extremely complex textures that run extremely quickly. It achieves this by giving the programmer quite a bit of control over the graphics pipeline, without exposing them to assembly languages. There can be a slight learning curve when first starting, but there are tons of examples of GLSL shaders on the Internet, as well as quite a number of great examples in the 'Shared Component' area of the TouchDesigner Forum.

The Point Sprite MAT is used to assign sprites to the points of a particle system. The name is self explanatory, in that a 2D image (a sprite) is placed at every single point in 3D space. The sprites are always facing the camera, and are scaled according to their Z depth. The example 'Point\_Sprite.toe' demonstrates this. To create a similar TouchDesigner network without point sprites, not only would there be a pretty disorganized Network, of who knows how many Transform TOPs and Composite TOPs, but they would all be using much more resources. By using a particle system and point sprites, the Network is easy to read, and doesn't require a lot of system resources.