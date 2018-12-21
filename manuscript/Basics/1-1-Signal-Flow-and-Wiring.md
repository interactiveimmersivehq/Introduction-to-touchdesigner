# 1 Basics

## *1.1 Signal Flow and Wiring*

Wiring Operators is the most basic operation in TouchDesigner. All projects are made up of nothing more than groups of Operators wired together. Each Operator, on its own, does a very specific thing, but when they are combined together into a ’Network’, they can solve extremely complex problems.

All data in TouchDesigner flows from left to right. Any inputs that an Operator has will always be on the left side, and outputs will be on the right side. The inputs and outputs will also be ordered first to last, going from top to bottom. In the example diagram below, follow the two signals starting on the left. As they flow from left to right, they are composited, one over the other.

{width=100%,float=left}
![img 1.1.1](images/1.1/signal-flow-1.png)

Components, interestingly, have the same data signal flow as Operators, flowing from left to right, but they are also capable of parent and child relationships, which flow from top to bottom. The component at the top of the signal chain is the parent, and the components below it are its children, and below that are the children’s children, and so on. In the example below, there is a small UI, that is made of a few sliders. In this example, the Slider COMPs are the children of the Container COMP, which is the parent.

{width=100%,float=left}
![img 1.1.2](images/1.1/signal-flow-2.png)

