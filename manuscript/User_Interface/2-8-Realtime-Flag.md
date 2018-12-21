## *2.8 Realtime Flag*

{width=100%,float=left}
![](images/2.8/realtime-1.png)

The Realtime flag changes TouchDesigner's behaviour significantly. When it is active (it is active by default), TouchDesigner will always prioritize real-world time. In a simple example, if a movie file is 30 seconds long, no matter what happens, TouchDesigner will try to play it over the course of 30 seconds. If this means that frames need to be dropped, TouchDesigner will try to honour time. This is the mode used for most real-time installation and performance work. 

When the Realtime flag is off, TouchDesigner will prioritize frame rendering over real-world time. In the example mentioned above, if Realtime is off, TouchDesigner would take as long as it needed to process and render each frame, falling out of real-world time to display every frame. This mode is useful when exporting complex animations or 3D renderings. Imagine this mode to be similar to a real-time version of rendering out of Adobe After Effects. 
