### *3.3 Importing Shaders from Shadertoy*

This section will demonstrate the basics of porting a shader from Shadertoy.com to TouchDesigner. We recommend using a feature-rich code editor, such as Sublime Text, Atom, or Notepad++, as there a strong Find-and-Replace function is essential.
###### Shadertoy API
When porting a shader from Shadertoy to TouchDesigner, you can either use your judgement and find/make sources that work similary to the built-in inputs in Shadertoy, or you can download the sources that were used on Shadertoy using their API. To download the shader's input sources, you have to set up a Shadertoy account and create an 'App Key'. 
To create an ‘App Key’, once you’re logged into Shadertoy, click on `PROFILE` at the top right, then click on 'your Apps' in the 'Config' section. Choose a name and description, and click the 'Create' button. 
You'll see the `App Key` in the `Manage Your Apps` section. Now, copy this URL `https://www.shadertoy.com/api/v1/shaders/MdlGDM?key=` into your browser, and enter your App Key at the end. After you press enter, the response will be a JSON object with a key called 'inputs'.  In this example, the URL above requires the file called 'tex09.jpg’.If you enter `https://www.shadertoy.com/presets/tex09.jpg` as the URL in your browser, you will see and be able to download the required texture.

#### Example 1: Waterly Video - Test
![Example 1: Waterly Video - Test](../img/12.6_shade/ex1_1.jpeg)
Shader written by: [FabriceNeyret2](https://www.shadertoy.com/user/FabriceNeyret2) <br>
https://www.shadertoy.com/view/MdlGDM <br>
<br>

##### Setup

Start by creating a GLSL TOP and an Info DAT. Put the GLSL TOP's name in the Info Dat's `Operator field`.<br>
On the the GLSL TOP's `Common` page, change the `Output Resolution` to `Custom` and then enter `1280` and `720` in the `Resolution` fields.<br> 
Copy the code from Shadertoy and paste it into the 'glsl1_pixel' DAT, replacing the code that was there by default.<br>
<br>
Now we need to set up the sources. For this example, we're just going to create two 'Movie File In' TOPs and select two pictures that are the same resolution as the 'GLSL' TOP (1280 x 720), ‘Mettler.3.jpg’ and 'Trillium.jpg'.<br>

##### Main Function and its Parameters

In Shadertoy, the main function and paramters are:<br>
`mainImage( out vec4 fragColor, in vec2 fragCoord )`<br>
but we'll change that to:<br>
`main()`<br>
To replace the fragColor argument that we removed, we'll go up to the top of the code and insert:<br> 
`layout(location = 0) out vec4 fragColor;`<br> 
Next, we'll search for all references to `fragCoord` and replace them with `gl_FragCoord`.

```
uniform vec3 Resolution;
uniform float iGlobalTime
``` 

###### Uniform Inputs
Shadertoy contains a list of built-in uniform variables. You can view them on the Shadertoy website at the top of the code window by clicking an arrow labled 'Shader Inputs', or you can click the '?' at the bottom right of the same code window to create a pop up window that contains 'Shadertoy Inputs' as well as other information. We will go through the main samplers and uniforms associated with Shadertoy shaders.

###### *Samplers*
Shadertoy has named their sampler inputs `iChannels`.These samplers can be images, videos, noise patterns, cube mabs, etc. The 'GLSL' TOP has a similar variable called `sTD2DInputs`. The Shadertoy samplers are individual numbered samplers, such as `iChannel0` and `iChannel1`. In TouchDesigner, `sTD2DInputs` is an array, so you can access an elements with a numeric index.<br> 
Now, search through the code and wherever there is the a reference to `iChannel0`, replace that with `sTD2DInputs[0]`. Where there is a reference to `iChannel1`, replace that with `sTD2DInputs[1]`.

###### *iGlobalTime*
To find out what type of uniform this needs to be, look at the list of 'Shader Inputs' on Shadertoy mentioned previously. In the list, `iGlobalTime` is a float, so near the top of our code, below the `fragColor` declaration, we'll write: <br>
`uniform float iGlobalTime;` <br>
Next, we click on the 'GLSL' TOP in TouchDesigner, and go to the `Vectors 1` page in the parameter window. <br>
As the first `Uniform Name` we'll write `iGlobalTime` and for the value we will reference TouchDesigner's 'seconds' member of the `absTime` class by entering: <br>
`absTime.seconds`<br>
It should look like this: <br>
![iGlobalTime : absTime.seconds](../img/12.6_shade/ex1_2.JPG)
<br>
###### *iResolution*
iResolution is the resolution of the Shader on Shadertoy. If our resolution depended on one of our inputs, we could use TouchDesigner's built-in array: 
`uTD2DInfos[i].res`
TouchDesigner only gives us with this information if we aren't providing our own vertex shader, so for consistency, we will manually declare iResolution as a uniform. If we look at Shadertoy's input list, we see that iResolution is a vec3. Similar to iGlobalTime, we'll first declare it in the code by going near the top of our code and writing the line: 
`uniform vec3 iResolution;` 
Next, go to the `Vectors 1` page of the GLSL TOP’s parameters, and next to the second `Uniform Name`, enter `iResolution`. For its values, enter `1270` and `720`. We won't need the 3rd value of the vec3 for this, so we'll just leave the other 2 values as `0`

Your GLSL TOP should now compile successfully and look something like this :<br>
![iGlobalTime : absTime.seconds](../img/12.6_shade/ex1_3.JPG)
<br>
<br>
<br>

#### Example 2: Shard
![iGlobalTime : absTime.seconds](../img/12.6_shade/ex2_1.jpg)
Shader written by: [simesgreen ](https://www.shadertoy.com/user/simesgreen)<br>
https://www.shadertoy.com/view/Xdf3zM <br>

This example will take you a bit further, using cubemaps, creating a noise sampler, using sound, and adding mouse interaction.

##### Setup
We will start off with a new TouchDesigner project and begin the same way we did for the last example.<br>
Create a GLSL TOP and set its `Output Resolution` to `1280` and `720`.<br>
Create an Info DAT and add a reference to the GLSL TOP to it’s `Operator` parameter.<br>
Copy the code from Shadertoy into `glsl1_pixel`.<br>
If we look at the shader on the Shadertoy website, at the bottom we can see that we require 3 inputs: a noise texture, a background image, and some sound/audio.

###### Noise Texture
In Shadertoy there are 4 noise textures: a monochrome and color noise at a resolution of 64 x 64, and a monochrome and color noise with a resolution of 256 x 256. <br>
For this example, create a Noise TOP and set the resolution to 64 x 64 in the `Common` settings. We can look at the noise texture on Shadertoy and estimate the settings. These are the settings you can use for now:<br>









