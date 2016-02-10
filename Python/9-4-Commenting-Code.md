
### *9.4 Commenting Code*

Commenting is a practice that should not be overlooked by new users of Python. As easy as it is to write a few lines of script, it takes only a few more seconds to quickly document what those lines do. This comes in handy in a multitude of situations such as:

* Sharing code and projects with other programmers

* Maintaining code in older projects

* Changing the functionality inside of a re-usable component


It may seem frivolous when scripts are brief, but it is a habit that should be solidified from day 1. Look at the example code below:

```
a = 10
b = op('value')[0]

op('op12').par.rx = b

c = str(op('numbers')[0])
d = 'testing'
e = 'something'

op('lines').par.text = d + e + c
```

This script is hard to read for a number of reasons. The main reason is that its actions weren't obvious when quickly skimmed. One quick way to increase the readability of this script is to comment it. Let's take the above script and add some basic comments to it:

```
#Set initial variable
#get the value from slider input
a = 10
b = op('value')[0]

#assign the slider value to video input rotation
op('op12').par.rx = b

#take numeric input from computer keypad
c = str(op('numbers')[0])
d = 'You'
e = 'pressed'

#create a sentence from variables above
#add it to a Text TOP to display
op('lines').par.text = d + e + c
```

Without taking the time to create meaningful variable and Operator names, the above script is still much easier to read through. Even out of context, the function of the script is apparent.

This kind of simple addition can make collaborating with other developers much easier and more enjoyable.