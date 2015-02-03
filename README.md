Introduction To Touchdesigner 088
=============================

<h4>
Foreword

Between the artist and the tool are countless techniques and bits of know-how that contribute to the artist becoming more fluid and well-equipped for the challenges of production.
 
When I caught wind of Elburz' TouchDesigner book project, I thought, yes I'd like to know what he knows!
 
Elburz' deep storage of TouchDesigner wisdom was absorbed from multiple sources - helping and conversing with a myriad of users on the forums, red-lining on-the-job on time-critical projects, working with Derivative using beta builds of TouchDesigner, and his purely exploratory endeavors mixed with his side-life as a hip-hop trombonist and VJ.
 
The book is a good keyboard-side or bed-side companion that explores the concepts, techniques and methodology behind TouchDesigner - something I have not had the opportunity to personally present before and am very happy Elburz has presented here. So build your chops with these treats - It can be read end-to-end or by randomly flipping through pages, as I found myself doing - discovering gems of information and insights throughout.
 
Many thanks to Elburz for this initiative to enrich the TouchDesigner community. I'm sure it will trigger a great chain reaction.

Greg Hermanovic, Founder, Derivative


<h4>
Foreword by Author

The purpose of this book is two-fold:

1) to teach the fundamentals of TouchDesigner 088, and 
2) to create a community-driven resource for beginners


The first purpose is straightforward. We will look at various UI elements, discuss Operators and Operator families, explore logical workflows, Network optimizations, performance interfaces, display management, and etc. TouchDesigner's core elements will be explained and demonstrated, and many common problems will be pre-emptively dealt with.

After the written portion, we will learn how to approach solving a problem with example projects and video tutorials at the end of the book. These lessons will be practical in that we will assemble a few projects and useful modules from the ground up.

The second purpose of this book is slightly more asking of the community. We really believe in the community, so instead of selling this book, we wanted everyone to be able to access it for free (text, video, and example files). We wanted to take this idea a step further, and not only allow free access to the book's contents, but also allow free access to the book's building blocks.

What this means is that anyone can feel free to add, comment, change, mark up, delete, or increment upon the resources in this book. All of the book has been completely written using LaTeX, and the code to compile the book, project files, examples, diagrams, and videos, and whatever else ends up within it, will all be hosted on GitHub, and will be free (under a Creative Commons license) for anyone to download, share, and build upon.

For quality control purposes, everyone will be able to branch the repository, but we will review all changes before integratating updates back into a main branch. Everyone who contributes will be thanked and added to the 'Credits' portion of the book. This way, a new user only has to look for a single PDF, or download link, to receive the communities most up-to-date knowledge.

We really hope that the community engages with this and helps create the ultimate how-to resource for beginners!

As of the initial writing, knowing what this book is will be as important as knowing what this book is not. This book is not an Operator reference manual. We will not cover every parameter or use of every Operator. This book is not meant to replace the Derivative Wiki as the main reference, we will only use and learn about what we need. This book is not meant to replace the forum's wealth of helpful users and components.

In the end, this resource is a tribute to many TouchDesigner programmers and Derivative staff who, whether on the forum, or in real-life, have helped all of us get where we are. We hope that this tradition will continue as long as TouchDesigner does. 



Elburz Sorkhabi & nVoid Art-Tech Limited




Access
=============================

There are multiple ways to access an Introduction to TouchDesigner 088. The first is to download the package from our website, which includes a PDF of the book, all the example .toe files, and the project files that go along with the hours of HD video tutorials. The link for this is below:

https://d31vryd1jmut49.cloudfront.net/Introduction_to_TouchDesigner.zip

The hours of HD video tutorials are available in a single Vimeo channel. All the files can be downloaded from Vimeo for offline viewing. The link for this is below:

https://vimeo.com/channels/845218

You can also download the LaTeX source code from this GitHub and build it yourself. You are free to change, edit, add, delete, and modify the text by branching the source files. When you are finished, submit your changes and they will be reviewed by our administration, and merged into the main branch, at which point you will be added to the list of contributors in the Contributors chapter of the book, along with your contributions.

For more general information about this resource, visit http://book.nvoid.com


Setting up your build environment
=============================

<h4>
Mac

To compile the book on Mac OS X, it is recommended that you install MacTex from this link: https://tug.org/mactex/

MacTex will come packaged with a LaTex editor that can be used to compile the book. The team behind the book have used Sublime Text 3.0 with the additional package named LaTexTools to compile the book directly from Sublime Text, a very beautiful text editor.


<h4>
Windows

To compile the book on Windows, it is recommended that you install TeX Live from this link: http://www.tug.org/texlive/acquire-netinstall.html

Be sure to follow the installation instructions carefully.

The team behind the book have used Sublime Text 3.0 with the additional package named LaTexTools to compile the book directly from Sublime Text, a very beautiful text editor.


Compiling the book
=============================
When you have setup your build environment, open the file "Introduction_to_TouchDesigner.tex" in the main "LaTex Source" folder, and compile it. This file is pull all the separate chapter files and builds the book. Whenever you make changes to the specific chapter files in "/LaTex Source/tex", do not try to compile the specific chapter you've edited. Instead, you need to compile "Introduction_to_TouchDesigner.tex".


Attribution and License
=============================

This resource is licensed under Creative Commons - Attribution-NonCommercial-ShareAlike-4.0 International.

Link: http://creativecommons.org/licenses/by-nc-sa/4.0/

We have used the Tufte-Style Book (Minimal Template) provided by http://www.LaTeXTemplates.com

Thank you!
