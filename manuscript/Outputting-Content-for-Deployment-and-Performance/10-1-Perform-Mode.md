# 10 Outputting Content for Deployment and Performance

### *10.1 Perform Mode*

Perform mode should be used whenever possible when deploying projects. The basic premise behind Perform mode is that when a project is ready to be delivered, it will be in a state that won't require on-demand programming, and thus won't require the Network editor. It is surprising how much system resources can go towards just rendering the Network editor, especially if there are many Operators with visible viewers, displaying CHOP channels, TOP previews, DAT tables, etc.

Therefore, Perform mode exists so that that computer can focus on rendering the content, and doesn't have to render the extra Network editor. Everything that is involved with creating the final product is still rendered and active in Perform window, including elements such as external data inputs and outputs. The only thing that stops being rendered is the Network editor.

As mentioned in the Component chapter, it is recommended that Container COMPs are used as the source for Window COMPs. The same recommendation applies to Perform mode.

Open example 'Perform\_mode.toe'. In this example, the Container COMP, 'container1', is used as the source for Perform mode. Press the 'F1' key to enter Perform mode, and the contents of the container will be displayed in a new window. Press the 'ESC' key to exit Perform mode and return to the Network editor. There is a UI button that can be used to enter Perform mode via the mouse.

![10.1.1](../img/10.1/perform.png)