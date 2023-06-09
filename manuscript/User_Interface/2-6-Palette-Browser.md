## *2.6 Palette Browser*

The Palette Browser can be thought of as a component library. The Palette Browser holds '.tox' files (or TouchDesigner Component files). These files contain a single Component Operator, that can hold a Network of other Operators. This means that a series of frequently used Operators, UI components, Python scripts, and more, can be created inside of a single Component Operator, saved as a '.tox' file, and quickly accessed at any time in the future.

Open the Palette Browser, and look through the large number of pre-existing '.tox' files that are available. Blank projects start with the Palette Browser open by default, and docked to the left side of the window. To open the Palette Browser as a floating window, use the keyboard command 'Alt + L'. Let's try one of the pre-built components. 

Under the 'Derivative' section, navigate to 'Tools', and then finally drag and drop the 'Blend' component into a new project. Looking at the 'Blend' component's UI, it is clear that there is quite a bit going on inside. Before diving deeper, take a moment to connect two inputs and try the 'Blend' component. Activate the viewer, click on the button underneath the image to select a blend mode, and then drag the semi-transparent handle across the image to blend between the inputs. This is a useful tool, and all it took was a simple drag and drop from the Palette Browser!

One of the goals of this book is to create some tools that can be added to the Palette Browser, so that they may be used regularly. There are two ways to add a component to the Palette Browser. The first is a drag and drop method. To do so, select 'My Components' from the top portion of the browser. Then drag any component from the Network and drop it into the lower portion of the Palette Browser. It will then be added to 'My Components' repository. The second method of adding a component is to drag a saved '.tox' file from Windows Explorer, and drop it in the same region mentioned above. The diagram below illustrates exactly where components should be dropped.  

{width=100%}
![](images/2.6/palette-1.png)

{pagebreak}
