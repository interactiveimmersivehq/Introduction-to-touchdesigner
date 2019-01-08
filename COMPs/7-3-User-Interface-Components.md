
### *7.3 User Interface Components*

Component Operators are incredibly important as they create user interfaces in TouchDesigner. Specifically, the Panel Components are what provide this functionality. Many user interfaces will be created in later examples, so only a few basic examples will be examined in this section.

Three of the most useful Panel COMPs are:

* the Slider COMP

* the Button COMP

* Container COMP


The first two function with the same capabilities as sliders and buttons in other applications, but can be modified to suit different requirements. Buttons can be programmed as toggles, radios, or momentary buttons. Sliders can function as single axis sliders, or as full XY pads.

Container COMPs, on the other hand, don't have a function other than acting as a container for other UI elements.

Open example 'UI.toe'. In this example, there is a simple UI. From the bottom of the Network upwards, there are the 2 Button COMPs and the 5 Slider COMPs. These are the components that are actually creating the UI's functionality. The parent of these elements, is used to group and arrange the buttons and sliders separately. Notice that if the viewers for 'container1' or 'container2' are activated, the UI elements are usable, but neither 'container1' or 'container2' have any outputs or Operators in their Networks. Similarly, the results are the same when 'container1' and 'container2' are combined inside of 'container3'. This is because Container COMPs have the ability to display their children in their viewers. Container COMPs facilitate the creation of complex interfaces using a combination of smaller pieces.

{pagebreak}