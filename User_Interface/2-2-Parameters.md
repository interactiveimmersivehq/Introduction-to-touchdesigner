
### *2.2 Parameters*

Parameters can be entered in a number of ways. Depending on the situation, some parameters may require a static value, and some may need to be driven by other values and inputs. Each parameter has three modes. Each mode is quite different and each defines how the parameter behaves. The three modes are:

1. Constant mode

2. Expression mode

3. Export mode

Constant mode is the default for most parameters, and is represented by a grey colour scheme in the value field. Expression mode is used for Python, tscript, or mathematical operations and scripts. Expression mode is represented by a dark grey and light blue colour scheme. Export mode is used to directly reference CHOP channels.  It is represented by a light green colour scheme.

Each of an Operators parameters can be independently changed between the three modes. To change the mode of a parameter, hover the mouse over the parameter's name. A '+' sign will appear near the parameter's name, similarly to the diagram below.

{width=100%,float=left}
![](../img/2.2/parameters-1.png)


Once hovering over the parameter's name, click it and it will expand, displaying more information and options, similarly to the diagram below:

{width=100%,float=left}
![](../img/2.2/parameters-2.png)

There are three main elements that are available once a parameter is expanded. The first on the left, is the parameter's scripting name. This scripting name is needed whenever that parameter is referenced in any of TouchDesigner's scripting languages. In the above diagram, the scripting name for the Noise CHOP's Roughness is 'rough'. Continuing the above example, the Python script to set the Roughness of the above Noise CHOP to '1' would be:

```op('noise1').par.rough = 1```

The second element is the three coloured squares. These squares represent the different modes for the parameter, as discussed above. Operator parameters set to Constant mode are represented by a filled grey square. This parameter can be changed to Expression mode by clicking on the outline of the light blue square. Once clicked, the light blue square will be filled, and the value field to the right will also be coloured to reflect the parameter's mode.

{width=100%,float=left}
![](../img/2.2/parameters-3.png)

To change the parameter's mode to Export mode, a CHOP channel needs to be dragged and dropped on the parameter, at which point it will take up Export mode's colour scheme, and the green box will be filled in.

{width=100%,float=left}
![](../img/2.2/parameters-4.png)

The third element of the expanded parameter is the value field. The value field displays a different piece of information depending on the parameter mode. In Constant mode, the value field displays the current value, and can be edited by clicking and typing in the field. In Expression mode, the value field displays the script of Python or tscript that is being evaluated. The expression can be edited by clicking and typing in the value field. In Export mode, the value field displays two pieces of information separated by a colon. The text before the colon displays the path of the CHOP that is exporting to this parameter. The text after the colon is the name of the channel being exported from the CHOP. Because these values are being imposed by another Operator, the value field cannot be edited while the parameter is in Export mode.
