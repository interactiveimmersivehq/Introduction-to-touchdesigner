# 11 Optimization
## *11.1 Introduction*

Is is incredible to think about the challenges that are overcome when working in real-time. All the hardware and software aside, there is an extraordinary amount of precision to real-time work. When working in a project at 30 FPS, every single thing that is processed, displayed, and created, must be done in a 33ms window. That's not even a tenth of a second! This window is even smaller when working at higher frame rates. A project running at 60 FPS only has 16ms to render every frame from start to finish.

Realizing how tiny the window of opportunity is, it is important to cherish every single fraction of a single millisecond. Wonder why Operators are taking a whole millisecond to cook. Become nervous and try to salvage every half millisecond possible, knowing that every millisecond makes a difference. These all require basic project analysis and optimization skills.

TouchDesigner uses the CPU and GPU heavily, and knowing how to figure out which is under more demand is an important skill. When faced with larger and larger Networks, knowing where the system is stalling, and how to optimize Operators to get around these pitfalls, can be the difference between successfully delivering and not delivering a project.

{pagebreak}