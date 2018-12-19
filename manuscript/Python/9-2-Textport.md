## *9.2 Textport*

The Textport has a few important roles in regards to scripting inside of TouchDesigner. There are two ways to open the Textport. The first is by using key command 'Alt + T'. The second is by selecting 'Textport' from 'Dialogs' in the menu bar at the top of the TouchDesigner window.

The first is that it can be used similarly to the IDLE shell that comes with Python installations. For example, open the Textport, type the following, and hit 'Enter' on the keyboard:

~~~~~~~~
print(2+2+2+2)
~~~~~~~~

Running this in Python would print the result of the equation, which is 8. After hitting 'Enter' in the Textport, the result of the equation is displayed. This is because the Textport works as a Python interpreter. Type Python code into the Textport, it will be processed, and the results will be returned.

It can similarly do the same for tscript, the scripting language that was used in TouchDesigner 077. Notice that when the Textport is opened, the first thing printed is:

~~~~~~~~
python >>
~~~~~~~~

This is because in TouchDesigner 088, the Textport interpreter is set to interpret Python by default. To work with tscript in the Textport, the mode of the Textport needs to be changed from Python to tscript. This is done by clicking on the Python logo in the top left corner of the Textport. Once clicked, it will change to the letter 'T' and the next line of the Textport will be:

~~~~~~~~
tscript ->
~~~~~~~~

This means the Textport is now in tscript mode. To confirm this, type the following tscript code into the Textport:

~~~~~~~~
echo Hello!
~~~~~~~~

Similar to the Python Print function, the above tscript code will print 'Hello!'' to the Textport.

Another great use of the Textport is as a Python debugger. Open example 'Textport\_1.toe'.

This is a very simple example that highlights how beneficial the Textport becomes when using Python scripts. Open the Textport, and then click on the 'Good Python' button in the middle of the Network. This will run a script that prints to the Textport:

~~~~~~~~
this will not error
~~~~~~~~

Now click on the 'Bad Python' button. The Textport will display something very different.

~~~~~~~~
File "/project1/chopexec1", line 11
	Print(this will error)
			     ^
SyntaxError: Invalid syntax
~~~~~~~~

This is a Python error, occurring because some of the code being interpreted is invalid. Learning to read these errors can greatly speed up debugging large Python scripts. Let's examine the different portions of this error.

The first line indicates exactly where the error is in the Network, and which line of the script the Python interpreter believes is invalid:

~~~~~~~~
File "/project1/chopexec1", line 11
~~~~~~~~

In this example, the Operator with the error is 'chopexec1' inside of the component 'project1'. The Python stops interpreting the script at line 11.

Below that, the Textport prints the line with the error:

~~~~~~~~
Print(this will error)
~~~~~~~~

More often that not, spelling mistakes and slip-ups can easily be caught by these two lines. In this case, it is clear that the string being printed is not enclosed in quotation marks. Knowing where the error is, and more specifically what the line the error is occurring on, means this would result in the problem being quickly solved. For the sake of this example look at the last line of the error:

~~~~~~~~
SyntaxError: Invalid syntax
~~~~~~~~

The last line of the error is the type of error Python is encountering. More detailed information on the different types of errors can be found by looking through the official Python 3.3 documentation, under the 'Errors and Exceptions' section. The 'SyntaxErrror' is a very common error, and is caused by the Python interpreter encountering code that isn't valid Python syntax. As mentioned, the above line of code is the missing the quotation marks around the string being printed.

Printing to the Textport is an excellent way to take some of the mystery out of scripting. When scripting in larger and larger projects, there are often scripts in every Network, and quite often, many of them are performing backend tasks, such as preloading and unloading movies, that have results that are difficult to view. More often than not, scripts are running in parallel in different Networks, and it becomes incredibly difficult to tell if the timing of scripts are correct, or if actions are happening in the wrong order.

By having simple Print functions spread throughout scripts, it is not only easy to see when scripts are running, but myriad pieces of information can be printed as well. Some of these pieces of information can be as simple as the path to the script that is being run, or as detailed as what values and variables are being worked with and changed.

Open example 'Textport\_2.toe'. In this example, there are two sequences of scripts that run one after another, with a certain amount of pause between them. Click the 'Visual Sequence' button. This sequence has buttons that are clicked into the On position as each script is run. This is solely to make it easier to see the progress of this sequence. How would this progress be monitored from another Network?

Open the Textport and click the 'Textport Sequence' button. Contrary to the first sequence, this sequence prints a message to the Textport as each script is run. There may not be buttons visually changing states in the Network, but a number of new abilities are gained. The first is the ability to monitor these scripts from anywhere in the project. The second is that it is possible to compare the timing of these sequences to any other scripts that are running elsewhere in the project. The third, and possibly the most valuable, is the ability to pause the project and have a written history of the most recent sequence of events.

This history becomes absolutely invaluable when debugging complex logic systems. In a project with 30 Networks and 300 independent scripts, when a series of actions fail without raising any Python errors, without an ordered log of events, it would be impossible to trace bugs. As a script becomes longer and more complex, it is easy to create more of these pseudo-checkpoints throughout the script, such as 'running X section of Y script'.