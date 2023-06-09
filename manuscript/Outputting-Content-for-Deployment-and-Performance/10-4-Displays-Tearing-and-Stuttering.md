
## *10.4 Displays, Tearing, and Stuttering*

There has not been much hardware discussion throughout this book, but it is important to keep a few things in mind when working with multiple displays. The most important rule is to always try to have all display hardware be exactly the same. Any difference in the signal flow, can cause what is called 'tearing'. The image below is an example of a frame that has tearing.

Examine the image below. Is it an example of what a frame with tearing will look like. Notice the two horizontal cuts across the frame:

{width=100%}
![](images/10.4/tearing.jpg)

*Image courtesy of Wikipedia*

Tearing occurs when a display refreshes its image out of sync with when the graphics card renders its image. The result is part of the image being from the previous frame, and part of it being from the next frame. On slow moving content, this can sometimes be hard to notice, but once there is any sort of motion in the content, tearing becomes incredibly distracting.

Tearing is a complex issue to solve, but there are a few preventative measures that can be taken to avoid it. The first is to use a professional graphics card, such as something from the nVidia Quadro series. Most companies will not guarantee tear-free playback on anything but their professional cards.

The second is to always ensure that the displays are identical. Identical can't be stressed enough. If there is an installation with 3 outputs that have a refresh rate of 60hz, and one output with a refresh rate of 59hz, there is a chance there will be tearing. If there is an installation with two 1080p projectors, and two SXGA+ projectors, there is a chance there will be tearing. The best practice is to use displays that are not only identical in specifications, but are also the exact same model of displays. Network remote access applications like VNC and LogMeIn have also been the culprits of tearing.

This brings up a very important issue with tearing: there are no hard and fast rules. Sometimes, setups with a handful of different resolutions and refresh rates will work perfectly and won't tear. On the other hand, sometimes even setups with identical displays can tear. Enough emphasis cannot be put on preventative measures to avoiding tearing. When tearing issues arise, the only things that can be done are a step by step breakdown and analysis of the system to see what is causing the tearing.

There is a list of common debugging methods on the Derivative Wiki page for 'Tearing'. 

Generally the steps to begin with are as follows, in no particular order:

* Verify the project isn't dropping any frames. Dropped frames can sometimes trigger tearing

* Verify no other applications are interrupting or mirroring the graphics card drivers, such as VNC and LogMeIn.

* Disconnect every display connected to computer, and one by one connect them until tearing occurs. Then isolate that display on it's own, and figure out if it's being cause by a single display, or by the layout

* Verify all displays are configured to the same resolution, colour bit depth, and refresh rate, in the nVidia or AMD control panel

* Verify that none of the displays have any rotation applied in Windows. this can cause unpredictable behaviour.

* Check the graphics card driver version and update it if necessary

* Check for drivers or firmware updates on external video splitters - such as the Datapath X4 or Matrox TripleHead2Go

* Confirm only 1 Window COMP is being rendered

* Verify Windows Aero is disabled. In Windows 7, Aero can cause dropped frames and stutters, but won't tear. Once disabled, the system might tear, but stutter free playback is guaranteed.

* Configure a Premium Mosaic using the nVidia Control Panel to create a single logical display 


There are many instances in which a system that performs perfectly, and doesn't drop a single frame, will occasionally stutter. This may occur because of how displays and graphics cards negotiate different refresh rates. 

If a project is running at 30 FPS, but a display's refresh rate is 60hz, frame doubling has to be negotiated somewhere. Between the graphics card and the display, most of the time this negotiation is done transparently, but sometimes there can be issues. What can occur is that instead of negotiating a proper frame doubling for every frame, one frame might be displayed once, while the next frame is displayed for three frames. From the project's point of view, no time is lost and no frames were dropped, so it would not be reported in the Performance Monitor or Windows Task Manager. 

If it seems that this kind of issue may be occurring, use the 'FPS is Half Monitor Refresh' feature in the Window COMP. This informs the graphics driver that it should show each frame for 2 refreshes.

{pagebreak}