
## *9.5 Compartmentalizing*

The more complicated projects become, scripts will slowly become longer and longer. At a certain point, it will take more time to search through code, than it will take to actually change and add to it. Because of this, it is important to compartmentalize all of a projects scripts.

This means a few different things, and incorporates a few different techniques, but it yields quite a number of benefits. All of these benefits will directly improve one's workflow, but more importantly, they will take a lot of the pain out of collaborative settings. Some of the benefits include:

* Easier long-term maintenance of scripts

* Less time spent explaining scripts to colleagues

* Easier reusability of programmed functionality

* Faster short-term edibility and code management


Open example 'Scripting\_1.toe'. In this example, there are 10 Movie In TOPs and there are a series of actions that need to be performed on each of them. First, each one should be unloaded. Secondly, each one will be assigned a new file path. Finally, each movie needs to be preloaded, and prepared for playback. Because this is a Python example, all of these actions will be performed with Python script. Take a look at the Text DAT named 'movies'.

A quick note about this script: For the sake of this example, this script doesn't iterate over all of the Operators using loops. This is to simulate what a longer and more complex script would feel like, even though only a few simple actions are being performed.

Right-click on the Text DAT named 'movies', select 'Run', and all the actions mentioned above will occur in sequence. This script has been lightly commented, but looking through it quickly can be a bit disorienting. To edit a single value somewhere in the code, it would have to be found in the long list of actions. Colleagues would have to spend more time trying to figure out what this script does. To re-use a piece of this script in the future, pieces of it would have to be manually found and extracted. How can these processes become more efficient?

Open example 'Scripting\_2.toe'. This example takes the code from the previous example, but separates each of our 'actions' into its own, isolated, Text DAT. Immediately, even without diving into each of the scripts, it is easy to tell what each one will do. There is one for unloading movies, one for changing paths, and one for preloading movies. At the end of each, there is a line of code that runs each progressive script in the sequence. This is line of code uses the Run class:

`op('preload').run()`

It would be easy to quickly edit a single value, as actions and parameters are much easier to track down now. Passing this component to a colleague would be no trouble at all, as they could quickly see what each script does at first glance. If someone needed a script to start to preload of a set of Movie In TOPs, it could be quickly taken from this project.

This compartmentalized workflow helps cut hard to manage scripts, some more than 500 lines in length, into smaller scripts that are easy to sort through quickly and share. In the case of the above example, there is third way to handle working with these multiple Operators.

Open example 'Scripting\_3.toe'. This example takes advantage of Python functions. A Python function is a small cluster of code that can be called to perform as series of action. Inside of the Text DAT named 'actions', a function has been defined that contains the set of actions that need to be performed on each Movie In TOP. From the Text DAT named 'set\_movie\_tops', instead of retyping the same set of actions over and over, the new function is called by passing it the name of each Movie In TOP.

Although the series of actions have been slightly arbitrary, the idea is simple: compartmentalize Python scripts for ease of maintenance, easier co-operative workflows, re-usability, and ease of management.

{pagebreak}