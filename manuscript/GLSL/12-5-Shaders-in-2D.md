## *12.5 Shaders in 2D*

Even if one doesn't want to spend a ton of time learning about GLSL for 3D use, the Pixel shader can be extremely useful as a tool for generative visuals and compositing 2D textures. Simple GLSL shaders can be especially useful when compositing textures, as it can save quite a lot of graphics memory when doing repititious work.

Let's take a look at an example of adding two TOPs together, similar to a Add TOP.

Open example 'Basic\_2D\_add.toe'.

Using the GLSL TOP, multiple TOP inputs can be composited, sampled, and effected in a GLSL pixel shader. In this example, a Movie In TOP and a Constant TOP are input into the GLSL TOP. The GLSL code in the pixel shader, adds them together:

```
out vec4 fragColor;

void main(){
	vec4 in1 = texture(sTD2DInputs[0], vUV.st);
	vec4 in2 = texture(sTD2DInputs[1], vUV.st);
	fragColor = in1 + in2;
}
```

Working with Pixel shaders in the TOP family is very similar to working with them using a GLSL MAT. There is still a main() loop, the declarations happen first before the main() loop, and there are semi-colons at the end of working lines of code.

The first difference to notice is how inputs are handled. In this example there are two inputs, and there are two lines that deal with those inputs:

```
vec4 in1 = texture(sTD2DInputs[0], vUV.st);
vec4 in2 = texture(sTD2DInputs[1], vUV.st);
```

To get access to a TOP input, a 4-component variable must be declared for the RGBA channels. The texture() function is used to sample a texture. It takes two arguments, the first is the texture that it is going to sample, which in these cases are TOP inputs. The second argument is the texture co-ordinate to sample.

In this case, since TOP inputs are being sampled, the built-in sampler array named 'sTD2DInputs' is used. This array is accessed by index. In this case, there are two TOP inputs, so 'sTD2DInputs[0]' is used to access the first input, and 'sTD2DInputs[1]' is used to access the second.

To access the proper texture co-ordinate, 'vUV.st' is used. 'vUV' is a built-in variable that contains the texture co-ordinates of the pixel. As mentioned, '.st' is used to access the first two components of the vector.

Once the appropriate pixel is addressed from each input, this example procedes to add the pixels together, and output them to 'fragColor', which is the defined output:

```
fragColor = in1 + in2;
```

As simple as that, a main functionality of the Add TOP has been replicated. This may seem like a round-about way of adding two textures, but the benefits of something as simple as this begin to become apparent when using more complicated workflows or the GLSL Multi TOP, which is fundamentaly the same as the GLSL TOP, except that it has an infinite number of TOP inputs (limited only by the graphics card).

Open example 'Basic\_2D\_multi.toe'.

This example expands on the previous example by adding together more sources. This is done by connecting all the sources into a GLSL Multi TOP, and then accesing them in the same way that the two inputs were accessed previously.

In the shader of this example, each input takes the next index of 'sTD2DInputs' and assigns it to another 'vec4', after which they are all added together.

Again, this might be useful, but a Composite TOP can add multiple inputs s well, so let's take it one step further.

Open example 'Basic\_2D\_composite.toe'.

This example takes the previous example a step further. With all the inputs defined, instead of just adding all the inputs together, the GLSL code does a mix of addition, subtraction, and multiplication. Remembering the order of operations when working like this is key!

This is incredibly useful when working with a large number of textures, even if just 1920x1080, because doing a similar process with TOPs would take multiple Composite TOPs, or a number of Multiply, Add, and Subtract TOPs. Being able to manipulate all these textures, even in such simple methods, all at once can save quite a bit of GPU memory.

Transforming the textures is very similar to transforming vertices in a vertex shader. Let's take a look at an example.

Open example 'Basic\_2D\_transform.toe'.

This example takes the previous example, and offsets a few of the textures. This is done by adding, subtracting, multiplying, and dividing the texture co-ordinate. Let's examine the example code below:

```
out vec4 fragColor;

void main(){
	vec4 in1 = texture(sTD2DInputs[0], vUV.st * 0.5);
	vec4 in2 = texture(sTD2DInputs[1], vUV.st);
	vec4 in3 = texture(sTD2DInputs[2], vUV.st - vec2(0.5,0.25));
	vec4 in4 = texture(sTD2DInputs[3], vUV.st);
	vec4 in5 = texture(sTD2DInputs[4], vUV.st + vec2(0.5,0.));

	fragColor = in1 + in2 * in3 - in4 * in5;
}
```

In the above example, three of the textures are being transformed. The first is being scaled up by a factor of two. To do this, 'vUV.st' is multiplied by 0.5. This may seem backwards, but remember that 'vUV' is the texture co-ordinates, so when both x-axis and y-axis co-ordinates are moved to the right, the image moves to the left. Imagine having a finger pointing into the center of a piece of paper. If the finger position is moved to the right, the image will be more to the left of the finger than before. This is an overtly simple example, but should help get the idea across.

The third input, 'in3', has been translated on both x-axis and y-axis by subtracting 0.5 from the x-axis, and 0.25 from the y-axis.

The final input, 'in5', has been translated on the x-axis by adding 0.5 to the x-axis.

Both of these two tranformations also follow the same thought process mentioned for the first transformation. For example, when adding 0.5 to the x-axis texture co-ordinates, they are being added to the texture co-ordinates and not the position of the image. Thus when the texture co-ordinates move 0.5 on the x-axis, the image appears to move to the left.

The final example will be to take the previous exampleoutputs each individual layer to a separate color buffer instead of compositing them.

Open example 'Basic\_2D\_buffers.toe'.

The shader is as follows:

```
out vec4 fragColor[5];

void main(){
	vec4 in1 = texture(sTD2DInputs[0], vUV.st * 0.5);
	vec4 in2 = texture(sTD2DInputs[1], vUV.st);
	vec4 in3 = texture(sTD2DInputs[2], vUV.st - vec2(0.5,0.25));
	vec4 in4 = texture(sTD2DInputs[3], vUV.st);
	vec4 in5 = texture(sTD2DInputs[4], vUV.st + vec2(0.5,0.));

	fragColor[0] = in1;
	fragColor[1] = in2;
	fragColor[2] = in3;
	fragColor[3] = in4;
	fragColor[4] = in5;

}
```

The first line of the shader has been modified so that the output 'fragColor' is now an array. Each component of the array can be assigned a different texture, as has been done at the end of the shader. At which point, with the '\# of Color Buffers' parameter for the GLSL Multi TOP set to 5, Render Select TOPs can be used to individually select each of the separate color buffers from inside of the GLSL Multi TOP using the. To do this, the 'Render or GLSL TOP' parameter references the GLSL Multi TOP, and the 'Color Buffer Index' parameter is set to the target color buffer.

Assigning textures to the color buffers is similar to assigning textures to a single output, with the addition of the color buffer index:

```
fragColor[0] = in1;
```

The number in the square brackets refers to the buffer being written to. In the above example, the first buffer is being written to.