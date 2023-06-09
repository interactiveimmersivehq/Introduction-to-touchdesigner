
### *9.3 Common Practices*

There are some common practices that should be upheld when working with Python. Something that is interesting about the Python language is that it is built around the idea of readability and simplicity. Python has an easter egg built inside of it, which can be accessed by entering the following code into a Python interpreter or the Textport:

```
import this
```

Python returns a poem named 'The Zen of Python' by Tim Peters. Below is that text:

    The Zen of Python, by Tim Peters

    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one-- and preferably only one --obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than *right* now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!


This poem is the motto for many Python developers. Many of its lines try to convey Python's ideals and common developer sense.

Think about the line:

    'Explicit is better than implicit'

This can be applied to something that is often done in a hurry: naming. There are many different areas in Python and TouchDesigner where objects reference each other by name. A developer ends up naming variables, functions, Operators, Networks, and more. Without carefully naming Operators, it would be impossible to know each Operator's function. Similarly, without care in naming variables, as demonstrated earlier in the chapter, reading scripts can become quite a tedious task. There are two conventions that are regularly used when naming Operators and variables in TouchDesigner.

The first involves using underscores in the place of real-world spaces. Here are some examples:

* final\_comp

* stop\_button

* time\_now


The underscores make names easier to read and quickly understand. There are individuals who aren't partial to using underscores, and because of such the second convention involves using capital letters to differentiate between words. Here are some examples:

* finalComp

* stopButton

* timeNow


Both are able to convey the original idea of explicit naming, and should be used to facilitate collaboration.

{pagebreak}