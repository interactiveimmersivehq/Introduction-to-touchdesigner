
### *12.4 Shaders in 3D*

Let's start by looking at a few very simple 3D scenes that utilize Vertex and Pixel shaders.

Open example 'Basic\_3D.toe'.

This is a simple render setup where the vertex shader does nothing but pass the vertices to the pixel shader, which then colors everything white. Let's take a more in-depth at each shader, starting with the Vertex shader:

```
void main(){
	gl_Position = TDWorldToProj(TDDeform(P));
}
```

Since this is written for someone with no GLSL experience, a few notes about basic C syntax and rules that need to be followed, since GLSL is very similar to C.

The first thing is that semi-colons need to be added at the end of working lines of code.

The second thing is that most of the working code will be inside of the main() loop. For beginners, the only things outside of the main loops will be the delcaring of variables such as input and output streams and attributes.

When starting an empty shader, it's good practice to start by entering the main() loop as follows:

```
void main(){

}
```

In this vertex shader, there is only have one line of code:

```
gl_Position = TDWorldToProj(TDDeform(P));
```

Let's break this down from right to left, as there is a lot going on here.

'P' in this instance is the vertex position. In TouchDesigner, there are a few attributes that are declared by default. For instance, 'P' is the vertex position, 'N' is the normal, 'Cd' is the color, and 'uv' is the texture coordinate layers (it is an array that is accessed by index, i.e. uv[0], uv[1], etc). These values can be accessed as easily as we've accesed 'P'.

In the line of code, 'P' is input into a function named 'TDDeform()'. This function takes the vertex position from object space and returns the position in world space.

Think of object space as if each object in the 3D world had it's own co-ordinate system and 0,0,0 point. After processing these vertices, they have to be transformed and integrated into world space. World space is, as the name implies, the full world. The world, in this case, is the common coordinate system, with one 0,0,0 point, where all objects will exist together.

Once the vertex positions are returned in world space, they are passed to the function 'TDWorldToProj()'. This function takes the world space co-ordinates and returns them in projection space. The projection space takes all the co-ordinates from the world space, and returns them from a camera's point of view.

These values are then assigned to the variable 'gl\_Position', which is a built-in output for the transformed vertices.

As shown in the rendering pipeline diagram, these transformed vertices are processed and passed to the Pixel shader, where they will be assigned color values.

In this example, the Pixel shader sets the color output of all the fragments to white. The code is below:

```
out vec4 fragColor;
void main(){
	fragColor = vec4(1,1,1,1);
}
```

Similar to the Vertex shader, all of the code except for the output declaration are inside of the main() loop, and there are semi-colons at the end of lines of code.

Starting from the top, there is this line of code:

```
out vec4 fragColor;
```

This line sets the output as a variable called 'fragColor'. A 'vec4' is a vector with 4 components, and in this scenario, they correspond to the output red, green, blue, and alpha channels. In GLSL, whenever declaring an input or output, the type must be declared as well, thus the specification that it will be a 'vec4'. Similarly, inputs will be prefaced by 'in' and outputs will be prefaced by 'out'.

The line of code inside of the main() loop is as follows:

```
fragColor = vec4(1,1,1,1);
```

As 'fragColor' has already been declared as the output, this line writes the pixel values directly to the output. The section 'vec4(1,1,1,1)' creates a 4-component vector with the values 1,1,1,1, and then assigns it to 'fragColor'. 'vec4' has to precede the list of values because 'fragColor' has already been declared as a vec4, so to assign a value to it, that value needs to be a 'vec4'.

Because the 4 components of the output correspond to RGBA channels, (1,1,1,1) would set all of the channels to 1, effectively setting the output to white for every pixel.

Now with a basic understand of working with shaders in a 3D scene, let's add a few levels of complexity. For starters, let's resize the box. This is as simple as multiplying each of the vertex positions, or 'P', by a value.

Open example 'Basic\_3D\_scaled.toe'.

Only a few lines of the vertex shader are changed:

```
vec3 scaledP;

void main(){
	scaledP = P * 0.5;
	gl_Position = TDWorldToProj(TDDeform(scaledP));
}
```

The first this that is added is a declaration for a variable that is going to be used, named 'scaledP'. This is going to be a 3-component vector because we'll be working with the vertex position, 'P', which is also a 3-component vector.

Once the variable is defined, it can be used throughout the code. The next line that is added is:

```
scaledP = P * 0.5;
```

This line takes the vertex position, multiplies all the values by 0.5, effectively making the box half the size. Similarly, a value of 2 would make the box be double it's original size.

This new value, 'scaledP', then replaces 'P' below:

```
gl_Position = TDWorldToProj(TDDeform(scaledP));
```

Similarly, to transform the box instead of scaling it, values need to be added or subtracted to the various axis.

Open example 'Basic\_3D\_transform.toe'.

In this example, The code in the vertex shader has been changed as below:

```
vec3 transformedP;

void main(){
	transformedP = P + vec3(1,0,0);
	gl_Position = TDWorldToProj(TDDeform(transformedP));
}
```

This is very similar to the above example. It starts off by declaring a 3-component vector named 'transformedP'. In the first line of the main() loop, instead of multiplying the vertex positions by 0.5, the new 3-component vector is being added to them.

The reason to use a 'vec3' in this example is that if 0.5 was simply added to 'P', it would add 0.5 to the x-axis, 0.5 to the y-axis, and 0.5 to the z-axis. Creating a 'vec3' for these values allows control over each specific axis. In this example, adding 'vec3(1,0,0)' will only add 1 to the x-axis, leaving the y-axis and z-axis untouched. In practice, this moves the box 1 unit to the camera's right.

We could just as easily change from addition to subtraction to move the box in the other direction.

Now, let's reference an LFO CHOP from the vertex shader to animate the movement.

Open example 'Basic\_3D\_LFO.toe'.

For this to be achieved, an LFO CHOP was created. The value of it's channel was then exported to the GLSL MAT's parameter 'value0x' in the 'Vectors 1' tab of the Parameter window. Then the Uniform was given a name, in this case 'lfoCHOP'. This means the value can now be accesed from within the vertex and pixel shaders.

The code in the vertex shader has been changed as follows:

```
vec3 transformedP;
uniform float lfoCHOP;

void main(){
	transformedP = P + vec3(lfoCHOP,0,0);
	gl_Position = TDWorldToProj(TDDeform(transformedP));
}
```

The first addition is in the second line, where a 'uniform' is declared. A 'uniform' is a global GLSL variable that is mainly used for parameters that a user or program will pass into the shader.

In this example, the LFO CHOP channel is a float value, so then 'float' is added after 'uniform'. The name of the uniform is important, because it must correspond to the name entered in the 'Uniform Name' parameter in the GLSL MAT. In the GLSL MAT, we named the uniform 'lfoCHOP', so to access it, the same name must be used.

The only other change is that where previously 1 was being added to the x-axis of the vertex position, there is now the value of 'lfoCHOP'.

```
transformedP = P + vec3(lfoCHOP,0,0);
```

With those small changes, a CHOP is controlling the x-axis position of the shader. Pixel shaders function in much of the same way as Vertex shaders. Let's assign the LFO CHOP in the previous example to control the red channel of the output color.

Open example 'Basic\_3D\_red.toe'.

In this example, the LFO CHOP is controlling the red channel of the pixel shader in much the same way that the LFO CHOP is controlling the x-axis transform.

The code in the Pixel shader is below:

```
out vec4 fragColor;
uniform float lfoCHOP;

void main(){
	fragColor = vec4(lfoCHOP,0,0,1);
}
```

Similarly to the x-axis transform example, the only steps needed were to declare the incoming uniform, and then to assign it to a parameter, in this case the first component of the vector. To take this another step furtuer, let's sample a Ramp TOP as the texture, instead of just outputting a single color.

Open example 'Basic\_3D\_texture.toe'.

The first thing that was done was create the Ramp TOP and assign it to the GLSL MAT. The TOP needs to be referenced in the 'Samplers 1' tab in the Paramter window. In the same way that the LFO CHOP needed a 'Uniform Name', the Ramp TOP needs a 'Sampler Name', which in this case is 'rampTOP'.

Then a Texture SOP is added after the Box SOP to assign the texture co-ordinates.

In the Vertex shader, a few lines of code are added to assign the texture co-ordinates. These lines are added below:


```
vec3 transformedP;
uniform float lfoCHOP;
out vec2 texCoord0;

void main(){
	transformedP = P + vec3(lfoCHOP,0,0);
	gl_Position = TDWorldToProj(TDDeform(transformedP));

	vec3 texCoord = TDInstanceTexCoord(uv[0]);
	texCoord0.st = texCoord.st;
}
```

The first line that is added is:

```
out vec2 texCoord0;
```

This line outputs a 2-component vector named 'texCoord0' which can be used in the pixel shader. In this case, they will be the texture UV co-ordinates.

There is one more additional line:

```
texCoord0.st = uv[0].st;
```

This line takes 'texCoord0' that was declared earlier, and assigns it the built-in TouchDesigner variable 'uv', which as mentioned earlier is declared by default and contains the UV texture co-ordinates (similar to 'P' for vertex position).

The '.st' here is assigning the two values contained in the 2-component vector 'uv' to the 2 components of 'texCoord0'. As mentioned earlier, where '.xyzw' are used for vertex positions, '.stpq' are often used for texture co-ordinates. These are mostly just for convention so that the same letters (such as XYZW and RGBA) don't mean multiple different things. You may also see '.uv' used instead of '.st', depending on the software package.

With these two extra lines of code, the Box SOP is now being textured by the Ramp TOP.