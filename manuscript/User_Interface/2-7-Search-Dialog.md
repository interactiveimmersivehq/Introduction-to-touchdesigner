## *2.7 Search Dialog*

The 'Search Dialog' is incredibly helpful as projects become more complicated, and riddled with Python scripts and nested Networks. The 'Search Dialog' can find a multitude of things in a multitude of places, and searches can be as broad, or specific, as needed. It is accessible in the 'Edit' menu at the top of  the screen, or by pressing 'F3' on the keyboard.

The 'Basic' search can not only find Operators, but can search through Python code. Frequently, Python is used to change Operator parameter values. Sometimes, in the thick of Python scripts, it is easy to lose track of specific lines of code. A quick search for the code below will return a list of every single line of code that involves changing parameters of the Operators with 'transform' in their name:

~~~~~~~~
op('transform').par
~~~~~~~~

Sifting through the results is much easier than manually looking through Networks full of code. 

The 'Advanced' search can search by any combination of name, Operator type, comments, flags, and more. When returning to past projects, often it takes some time to relocate and reacclimatize to the inner workings of complex logic systems. This is when searching for operators by vague name and type can save a ton of time. For example, in an extremely nested system, somewhere in the depths of it might be a Movie In TOP that has the word 'movie' in its name. These little pieces of information about the Operator type, and partial name, can be used to create a fairly precise search. 

When a search has yielded results, each result can be clicked on to open the Network in a new floating pane. Here, the results can be can quickly previewed, and simple changes can be made within this pane, without affecting the current work area.

{pagebreak}