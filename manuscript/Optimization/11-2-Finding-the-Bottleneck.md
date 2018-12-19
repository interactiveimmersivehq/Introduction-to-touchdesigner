
### *11.2 Finding the Bottleneck*

The computer as a whole can be thought of as a pipeline. The CPU, GPU, RAM, and hard drives, all work together to create the final product. They sometimes work independently, but often times they are reliant on each other, because they individually perform very specific tasks. In a pipeline, the system can only be as fast as the weakest link. Because of this dependant nature, one stage of the pipeline can stall a whole project, even if the rest of the pipeline is completely clear. This stall, or weak link in the chain, is referred to as a bottleneck.

An example of a pipeline with a bottleneck is a project that tries to render some basic 3D geometry and texture their faces with video files. This hypothetical project consists of 4 Box SOPs. Every face of the Box SOPs are textured with a 1920x1080 HAP Q movie file. The computer being used for this has 32GB of RAM, dual 8-core processors, a top of the line nVidia Quadro graphics card, and a single 5400-RPM hard drive.

When launched, this project just won't run on this system. Regardless of how much RAM, how many processors, and how expensive a graphics card, the project can't read that many HAP Q files from a single 5400-RPM hard drive. The computer will continually stall because the hard drive can not spin fast enough to read every single movie file simultaneously. HAP Q files are demanding on the hard drive, and no matter how powerful the rest of the computer is, the project will not run. The GPU can't begin to read movies from a hard drive, just as the hard drive cannot begin to process pixels. The hard drive, in this case, has become the bottleneck in this project's pipeline.

Generally there are three areas where bottlenecking occurs: the GPU, the CPU, and the hard drives.

The GPU is a pipeline in and of itself, and pixel shading is the stage that is likely to become a bottleneck. Whenever operating on pixels, using almost any TOP, the system demands more and more of the GPU's pixel shader. The higher the resolution, the higher the demand on the GPU. There is a 1:1 ratio between a TOPs resolution and it's GPU workload. If a TOP's resolution is reduced by a factor of two, its GPU workload is proportionally reduced. A quick way to check if there is a pixel shading bottleneck is to lower the resolution of all generator TOPs, such as Render TOPs and Constant TOPs. If there is an immediate increase in speed and performance, then it is clear that there is a pixel shading bottleneck. 

When the graphics card is overworked, seemingly random TOPs will start to have higher than normal cook times. This becomes apparent when looking in the Performance Monitor at the cook times of various TouchDesigner UI elements. If all of a sudden, the various UI elements are taking more than a millisecond to cook, the Network needs to be optimized to relieve the GPU of some of its workload. 

The CPU is second area where bottlenecks are experienced. Most Operators require the CPU to function, thus the CPU can quickly be overworked. CPU bottlenecks tend to be easier to track down, because the Operators that take a long time to cook are visible in the Performance Monitor. It is possible to measure how much CPU head room there is with the Hog CHOP. This CHOP does as it name implies, and hogs CPU processing power. The 'Delay' parameter is the amount of seconds that the Hog CHOP will add to the cook time of each frame. If a Hog CHOP is created and the project begins dropping frames, that means the CPU is the our bottleneck. 

All movie files use the CPU to decode data from their compressed state. Certain codecs use the CPU more than others, and reading many movie files simultaneously can use more CPU resources than one would imagine.

An overloaded CPU reacts similarly to an overloaded GPU, in that inconsistent results will appear in the Performance Monitor. Operators will have varying cook times. This is because their operations are started, but before they finish, the CPU is called to perform another process. The amount of time that the Operator spends waiting for the CPU to return to its process is what increases it's cook time. Unlike a GPU overload, a CPU overload will generally effect more than just TOPs.

Hard drives are the third area where bottlenecks occur. Specific operations can be demanding on hard drives, and it is easy to overlook high quality solid state drives (SSD) when preparing systems for deployment. Operations such as reading and writing movies can quickly exhaust a drive, depending on the codec used. This bottleneck will often appear in the Performance Monitor as a line item under a Movie In TOP that such as:

    Waiting for frame for 90 - E:/test.mov from harddrive

Where the number is the frame of the movie, and the path is the path to the movie file.