
## *7.2 Window COMP*

The Window COMP is used in almost every project to display the contents of an Operator in a new window. Whether using the Window COMP to create a full-screen output, or to create more of a traditional windowed application, there are a number of options that will need modifying. Because of the unique nature of every project, there are no 'best settings' to consistently rely on. Spend some time and go over the parameters on the Wiki, and experiment to find works best in each and every new situation.

Open example 'Window.toe'. This example demonstrates a very helpful practice, as well as some simple Window COMP functionality. It is best practice to use a Container COMP as the source of the Window COMP's output. This is because the texture in a TOP can be dragged around the screen, even in Perform Mode. If this happens, the texture will remain shifted until the project is reloaded, or until the texture is moved back to its original position. The same texture shifting doesn't occur to Container COMPs. The texture inside of a Container COMP cannot be dragged around by default, meaning the texture will always be consistent.

The other functionality in this example is rather simple. The first is a button, whose Null CHOP is being referenced in the 'Open in Separate Window' parameter of the Window COMP. This allows easy access to the opening of the window. The next is a button that dynamically checks how many monitors are connected, by getting a row count from the recently implemented Monitors DAT. Using that value to cycle a Count CHOP, open the window with the first button, then use the second button to cycle through which monitor this window is assigned to.

{pagebreak}