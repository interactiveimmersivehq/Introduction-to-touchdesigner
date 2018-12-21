
## *4.5 Time Slicing*

Time slicing is something that is unique to TouchDesigner, and can be a bit tricky to understand at first. 

A Time slice is the period between the last rendered frame and the current rendered frame. Think of Time slices as dynamic amounts of time. If a project is running at a consistent 60 FPS, then the time slices will be 1 frame in length. If a project is having trouble keeping up with real-time, and drops 10 frames, the corresponding time slice would be 10 frames in length.

Time slicing exists to smoothen out CHOP data in situations where frames are dropped. To think about it simply, Time slicing is when CHOPs start taking the size of Time slices into account when cooking. Think of this as a kind of adaptive cooking, meaning that as the time slices grow in length, the CHOPs will compensate for the amount of frames lost, and cook the amount of frames necessary to produce smoother outputs. This is in contrast to CHOPs that aren't time sliced, that will cook their value at the last cooked frame, then jump to the value at the next cooked frame, no matter how many frames are dropped inbetween. Only CHOPs can take advantage of Time slicing.

Using the example above, when the timeline is running consistently at 30 FPS, every time slice is 1 frame in length. If there are two ramps going from 0 to 1 over the course of one second (30 frames), both outputs would be smooth ramps. If, for some bizarre reason, only every tenth frame was cooked, there would be very different results. In the non-time sliced CHOP, the value would jump every time a frame is cooked, while the data between those cooked frames is lost. The Time sliced CHOP is aware that it is only being cooked every tenth frame, and will cook the frames inbetween to interpolate between the value of the last cooked frame, and the current cooked frame. This keeps the data smooth no matter what is going on. 

The diagram below illustrates the above example, where the dotted-blue line is a non-Time sliced CHOP, the dotted-red line is a Time sliced CHOP, and the vertical dotted-green lines represent a cooked frame: 

{width=100%,float=left}
![Time Slicing](images/4.4/Timeslice.png)

