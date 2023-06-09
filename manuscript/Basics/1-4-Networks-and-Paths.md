## *1.4 Networks and Paths*

All TouchDesigner projects are made of Networks. A Network is a group of Operators. Networks are encapsulated inside of components, such as a Container COMP, Base COMP, Geometry COMP, etc. Networks can be infinitely nested. The top level is called the ’root’ level. TouchDesigner system and UI elements can be found at the ’root’ level.

Encapsulating and organizing Networks from the start of the project is a great practice to get in the habit of. The current path is always visible in the ’Path Bar’ at the top of the ’Network Editor’.

{width=100%}
![](images/1.4/path-1.png)

All TouchDesigner Operators have a path. These paths are similar to Unix file paths. There are two kinds of paths to an Operator: the ’absolute path’ and the ’relative path’. The ’absolute path’ is the path to the Operator from the ’root’ of the project, or ’/’. The ’relative path’ is the path to an Operator from another Operator. These paths start from the Network of the referencing Operator, instead of starting from the ’root’.

Open example ’Paths.toe’. This example demonstrates paths. TouchDesigner will start in the ’root’ of the project where there is a Container COMP named ’network1’. Inside of ’network1’, there are two Operators. ’rel1’ is a Text DAT with two paths in its contents. The first is an ’absolute path’. This path starts from the ’root’, or top of the project, and travels towards the Operator. The second path is the ’relative path’ from the current Operator to ’rel2’, which is a Text DAT inside of the Container COMP named ’network2’. In the ’relative path’, the path travels from the current location to the destination. To get from ’rel1’ to ’rel2’, the path only needs to travel into ’network2’, thus the ’relative path’ is ’network2/rel2’.

Notice that the viewer of ’network2’ is displaying an Operator from inside of it. This technique will be discussed more in later examples, but what is important now is the path used. In the ’Operator Viewer’ parameter of ’network2’, there is the path to ’./display’, where ’display’ is the name of the Operator, and ’./’ denotes one level inside of the referencing Operator, which is ’network2’ in this case.

Inside of ’network2’, there is a Text DAT named ’display’, whose contents are being displayed in the Network above. The other two Text DATs have more path examples written in them. ’abs1’ is another example of an ’absolute path’. ’rel2’ has an example of a ’relative path’ between itself and ’abs1’. It also has an example of a ’relative path’ between itself and ’rel1’ in the Network above, where ’rel1’ is the Operator’s name, and ’../’ denotes one Network level above the current Network. ’../’ can be used in sequence to move up as high as the root, but there are more efficient ways of making paths.

{pagebreak}