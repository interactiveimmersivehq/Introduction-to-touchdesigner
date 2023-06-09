## Foreword

Between the artist and the tool are countless techniques and bits of know-how that contribute to the artist becoming more fluid and well-equipped for the challenges of production. When I caught wind of Elburz’ TouchDesigner book project, I thought, yes I’d like to know what he knows! Elburz’ deep storage of TouchDesigner wisdom was absorbed from multiple sources - helping and conversing with a myriad of users on the forums, red-lining on-the-job on time-critical projects, working with Derivative using beta builds of TouchDesigner, and his purely exploratory endeavors mixed with his side-life as a hip-hop trombonist and VJ.

The book is a good keyboard-side or bed-side companion that explores the concepts, techniques and methodology behind TouchDesigner - something I have not had the opportunity to personally present before and am very happy Elburz has presented here. So build your chops with these treats - It can be read end-to-end or by randomly flipping through pages, as I found myself doing - discovering gems of information and insights throughout.

Many thanks to Elburz for this initiative to enrich the TouchDesigner community. I’m sure it will trigger a great chain reaction.

<br>
Greg Hermanovic<br>
Founder<br>
Derivative
<br>



## Foreword by Author

The purpose of this book is two-fold:

* to teach the fundamentals of TouchDesigner 088

* to create a community-driven resource for beginners

The first purpose is straightforward. We will look at various UI elements, discuss Operators and Operator families, explore logical workflows, Network optimizations, performance interfaces, display management, and etc. TouchDesigner's core elements will be explained and demonstrated, and many common problems will be pre-emptively dealt with.

After the written portion, we will learn how to approach solving a problem with example projects and video tutorials at the end of the book. These lessons will be practical in that we will assemble a few projects and useful modules from the ground up.

The second purpose of this book is slightly more asking of the community. We really believe in the community, so instead of selling this book, we wanted everyone to be able to access it for free (text, video, and example files). We wanted to take this idea a step further, and not only allow free access to the book's contents, but also allow free access to the book's building blocks.

What this means is that anyone can feel free to add, comment, change, mark up, delete, or increment upon the resources in this book. All of the book has been completely written using LaTeX, and the code to compile the book, project files, examples, diagrams, and videos, and whatever else ends up within it, will all be hosted on GitHub, and will be free (under a Creative Commons license) for anyone to download, share, and build upon.

For quality control purposes, everyone will be able to branch the repository, but we will review all changes before integrating updates back into a main branch. Everyone who contributes will be thanked and added to the 'Credits' portion of the book. This way, a new user only has to look for a single PDF, or download link, to receive the communities most up-to-date knowledge.

We really hope that the community engages with this and helps create the ultimate how-to resource for beginners!

As of the initial writing, knowing what this book is will be as important as knowing what this book is not. This book is not an Operator reference manual. We will not cover every parameter or use of every Operator. This book is not meant to replace the Derivative Wiki as the main reference, we will only use and learn about what we need. This book is not meant to replace the forum's wealth of helpful users and components.

In the end, this resource is a tribute to many TouchDesigner programmers and Derivative staff who, whether on the forum, or in real-life, have helped all of us get where we are. We hope that this tradition will continue as long as TouchDesigner does. 


*Elburz Sorkhabi & nVoid Art-Tech Limited*
<br>

## What is TouchDesigner?

This is a question many users spend time trying to answer when starting out. It can be surprising how long it takes to create and perform simple tasks. It can be surprising that a good amount of time is spent building functionality that is already native to other software packages. So what is TouchDesigner? The answer is simple: TouchDesigner is a visual, node-based programming language.

Starting from possibly the most important aspect of the description, TouchDesigner is a programming language. TouchDesigner isn't an application that is ready on start to perform actions that may seem simple in other applications. TouchDesigner is an environment with extreme depth, and many potential pitfalls. With some practice and time, many things can be created quickly as they're required. With the book's goal to create re-useable modules, the speed at which a blank canvas can become a finished project will be greatly increased. This doesn't negate the fact that TouchDesigner is still a programming language. Many tasks will still require due diligence in regards to time and effort. Many will require quite a bit of head-scratching, and all of them will require some basic problem-solving skills. 

The second aspect of the description is that TouchDesigner is node-based. This mean that instead of opening a text document and typing line after line of code, TouchDesigner's graphical interface is used to make applications out of nodes. Each node, or Operator in TouchDesigner, performs a specific, small, and granular action. To perform complex tasks, a handful of nodes will work together. To send information between these nodes, their inputs and outputs are wired together. There are many node-based programming languages in existence, such as Cycling 74's Max/MSP, but what sets TouchDesigner apart is it's visual nature.

Everything in TouchDesigner has a visual counterpart. All the Operators have viewers. Everything, whether it be text, control data, audio, videos, and more, is visualized through each and every operation that is performed. This is unlike any traditional programming, and even node-based, language, but it is what makes TouchDesigner a fantastic environment to work with. Learning how to do many complex tasks is greatly simplified by the ability to visualize the steps involved, every step of the way. 

<br>

## Accessing the book

There are multiple ways to access an Introduction to TouchDesigner 088. Since converting the book to using Gitbooks, you may now  download the PDF, epub, or mobi version of the book from the link below:

https://www.gitbook.com/book/nvoid/introduction-to-touchdesigner/details

The example files are found in the ```TouchDesigner Example Files``` folder of the GitHub repo, which can be cloned or downloaded here:

https://github.com/nVoid/Introduction-to-touchdesigner

The hours of HD video tutorials are available in a single Vimeo channel. All the files can be downloaded from Vimeo for offline viewing. The link for this is below:

https://vimeo.com/channels/845218

You can also download the Markdown source code from this GitHub repo and build use the parts separately. You are free to change, edit, add, delete, and modify the text by branching the source files. When you are finished, submit your changes and they will be reviewed by our administration, and merged into the main branch, at which point you will be added to the list of contributors in the Contributors chapter of the book, along with your contributions.

For more general information about this resource, visit http://book.nvoid.com

<br>

## Attribution and Licensing

This resource is licensed under Creative Commons - Attribution-NonCommercial-ShareAlike-4.0 International.

Link: http://creativecommons.org/licenses/by-nc-sa/4.0/

Thank you!
