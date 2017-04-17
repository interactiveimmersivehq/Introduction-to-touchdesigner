# Instructions

非常高兴在中国我们拥有一群TD开发者，在陈若琨（Totti Chen）的带领下他们建立了TouchDesigner的华人社区（www.touchdesigner.co），并且把这本书翻译成了中文！很难想象这对于他们是多大的工作量，但是作为TD家族的一部分，他们将成果无私与大家分享，有需要的华人朋友请前往下载：http://www.touchdesigner.co/9

##Intoduction to Touchdesigner

###第一章 (Chapter One)

本章将教授最基础的知识，对于刚刚起步并且有着无限好奇心的你，是一个很好的参考材

料，让我们开始吧！

###第二章 (Chapter Two)

本章介绍了一些快捷键和基础界面菜单，请尝试跟随着说明去尝试那些功能，会让你有收

获的。

###第三章 (Chapter Three)

本章介绍了TOP元件的一些知识，着重介绍了视频播放和编码器的选用，这对于大多数的

视频控制播放作业将会很有帮助。

###第四章 (Chapter Four)

本章介绍了CHOP元件的一些知识，可能看起来有些晦涩难懂，但是如果你开始做大项目

的话你会发现这些非常有用！

###第五章 (Chapter Five)

本章介绍了DAT元件的一些知识，可能比较偏向于工程方面，有编程基础的朋友可能更容

易理解，但是不要紧，真是项目操作起来并不会那么复杂。

###第六章 (Chapter Six)

本章介绍了SOP元件的一些知识，这部分主要讲述如何渲染三维场景，参照案例学习会有

不小的收获。

###第七章 (Chapter Seven)

本章介绍了COMP元件的一些知识，这部分主要讲述一些比较综合性的元件，例如容器和

UI的案例。

###第八章 (Chapter Eight)

本章介绍了MAT元件的一些知识，这部分主要讲述了不同材质的作用和使用方法。

###第九章 (Chapter Nine)

本章介绍了一些关于Python的基本知识，如果你了解它，将会让你的TD程序变得更为强

大和灵活

###第十章 (Chapter Ten)

本章介绍了输出模式，包括如何进行融合和一些常见的输出错误分析。

###第十一章 (Chapter Eleven)

本章介绍了如何进行系统优化，对于制作大项目的成员来说这章将会让你醍醐灌顶！


## Foreword

Between the artist and the tool are countless techniques and bits of know-how that contribute to the artist becoming more fluid and well-equipped for the challenges of production. When I caught wind of Elburz’ TouchDesigner book project, I thought, yes I’d like to know what he knows! Elburz’ deep storage of TouchDesigner wisdom was absorbed from multiple sources - helping and conversing with a myriad of users on the forums, red-lining on-the-job on time-critical projects, working with Derivative using beta builds of TouchDesigner, and his purely exploratory endeavors mixed with his side-life as a hip-hop trombonist and VJ.

The book is a good keyboard-side or bed-side companion that explores the concepts, techniques and methodology behind TouchDesigner - something I have not had the opportunity to personally present before and am very happy Elburz has presented here. So build your chops with these treats - It can be read end-to-end or by randomly flipping through pages, as I found myself doing - discovering gems of information and insights throughout.

Many thanks to Elburz for this initiative to enrich the TouchDesigner community. I’m sure it will trigger a great chain reaction.

<br>
*Greg Hermanovic<br>
Founder<br>
Derivative*
<br>



## Foreword by Author

The purpose of this book is two-fold:

* to teach the fundamentals of TouchDesigner 088

* to create a community-driven resource for beginners

The first purpose is straightforward. We will look at various UI elements, discuss Operators and Operator families, explore logical workflows, Network optimizations, performance interfaces, display management, and etc. TouchDesigner's core elements will be explained and demonstrated, and many common problems will be pre-emptively dealt with.

After the written portion, we will learn how to approach solving a problem with example projects and video tutorials at the end of the book. These lessons will be practical in that we will assemble a few projects and useful modules from the ground up.

The second purpose of this book is slightly more asking of the community. We really believe in the community, so instead of selling this book, we wanted everyone to be able to access it for free (text, video, and example files). We wanted to take this idea a step further, and not only allow free access to the book's contents, but also allow free access to the book's building blocks.

What this means is that anyone can feel free to add, comment, change, mark up, delete, or increment upon the resources in this book. All of the book has been completely written using LaTeX, and the code to compile the book, project files, examples, diagrams, and videos, and whatever else ends up within it, will all be hosted on GitHub, and will be free (under a Creative Commons license) for anyone to download, share, and build upon.

For quality control purposes, everyone will be able to branch the repository, but we will review all changes before integratating updates back into a main branch. Everyone who contributes will be thanked and added to the 'Credits' portion of the book. This way, a new user only has to look for a single PDF, or download link, to receive the communities most up-to-date knowledge.

We really hope that the community engages with this and helps create the ultimate how-to resource for beginners!

As of the initial writing, knowing what this book is will be as important as knowing what this book is not. This book is not an Operator reference manual. We will not cover every parameter or use of every Operator. This book is not meant to replace the Derivative Wiki as the main reference, we will only use and learn about what we need. This book is not meant to replace the forum's wealth of helpful users and components.

In the end, this resource is a tribute to many TouchDesigner programmers and Derivative staff who, whether on the forum, or in real-life, have helped all of us get where we are. We hope that this tradition will continue as long as TouchDesigner does. 


*Elburz Sorkhabi & nVoid Art-Tech Limited*
<br>

## What is TouchDesigner?

This is a question many users spend time trying to answer when starting out. It can be surprising how long it takes to create and perform simple tasks. It can be surprising that a good amount of time is spent building functionality that is already native to other software packages. So what is TouchDesigner? The answer is simple: TouchDesigner is a visual, node-based programming language.

Starting from possibly the most important aspect of the description, TouchDesigner is a programming language. TouchDesigner isn't an application that is ready on start to perform actions that may seem simple in other applications. TouchDesigner is an environment with extreme depth, and many potential pitfalls. With some practice and time, many things can be created quickly as theyre required. With the book's goal to create re-useable modules, the speed at which a blank canvas can become a finished project will be greatly increased. This doesn't negate the fact that TouchDesigner is still a programming language. Many tasks will still require due diligence in regards to time and effort. Many will require quite a bit of head-scratching, and all of them will require some basic problem-solving skills. 

The second aspect of the description is that TouchDesigner is node-based. This mean that instead of opening a text document and typing line after line of code, TouchDesigner's graphical interface is used to make applications out of nodes. Each node, or Operator in TouchDesigner, performs a specific, small, and granular action. To perform complex tasks, a handful of nodes will work together. To send information between these nodes, their inputs and outputs are wired together. There are many node-based programming languages in existence, such as Cycling 74's Max/MSP, but what sets TouchDesigner apart is it's visual nature.

Everything in TouchDesigner has a visual counterpart. All the Operators have viewers. Everything, whether it be text, control data, audio, videos, and more, is visualized through each and every operation that is performed. This is unlike any traditional programming, and even node-based, language, but it is what makes TouchDesigner a fantastic environment to work with. Learning how to do many complex tasks is greatly simplified by the ability to visualize the steps involved, every step of the way. 

<br>
## Attribution and Licensing

This resource is licensed under Creative Commons - Attribution-NonCommercial-ShareAlike-4.0 International.

Link: http://creativecommons.org/licenses/by-nc-sa/4.0/

Thank you!
