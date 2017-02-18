
### *3.5 Codecs*

Movie playback is a taxing process. It is wise to spend time experimenting with different codecs to see which one suits a project in terms of visual quality and performance.

Before diving into specific codecs, it is important to know the difference between a codec and a container. Codec has taken over as the general term for the file format of audio-video files, which is confusing for beginners, because many containers can hold multiple codecs. 

Codec stands for compressor-decompressor. The codec has two main tasks. The first is to compress video data for storage and transportation, and the second is to decompress the video data for playback. Because of these different tasks, each codec is made for a different purpose. Some prioritize compression for light weight, portable files, while others prioritize quality, for long-term preservation of content. Different projects will have different requirements. Sometimes, the goal is to play back a single piece of content at the highest quality possible, whereas other times, quality must be sacrificed to be able to playback multiple video files simultaneously. Finding the right codec for each project may require a few tests and some forethought, but it is time well spent. 

A container does exactly what its name implies. It holds the compressed video, audio, and all the metadata a movie player needs to properly decompress and playback the content. There are quite a few different containers, but they have much less of an impact on the overall programming workflow, compared to codecs. 

Things can get complicated when different combinations of containers and codecs are used. Imagine a file named 'test\_movie.mov'. In one example, this file could be an Animation codec compressed video file inside of a '.mov' QuickTime container. What's interesting, and what also confuses many beginners, is that in another example, this file could be an H.264 compressed video file inside of a QuickTime container. To add to confusion, the same H.264 file could also be inside of a '.mp4', or MPEG-4 Part 14, container. 

Confusion aside, some popular codec choices are currently the HAP family, H.264, Animation codec, and Cineform. Each codec has its own set of advantages and disadvantages. Below is a very quick point form list of some pros and cons to each:


**HAP family**


*Pros*

* Can playback extremely high resolutions and high frame rates

* Very little CPU cost

* HAP Q is visually lossless

* Very little GPU cost



*Cons*

* Large file sizes

* Difficult to batch encode files on Windows

* Must use SSDs or a RAID0 of SSDs for file playback

* Main bottleneck is hard drive read speeds



**H.264**

*Pros*

* Creates extremely light-weight/low file size videos

* Best bang for buck when comparing quality to file size

* Low disk usage


*Cons*

* Requires a large number of CPU cores to playback extremely high resolutions or high frame rate.

* Can experience colour quantization if proper care is not taken in encoding

* Bit rate is highly dependant on content

* 4096 pixel size resolution in both length and width

* Difficult to create alpha channels


**Animation Codec**

*Pros*

* 100% quality is a lossless file

* Prioritizes quality 

* Has native support for Alpha channel
 

*Cons*

* Large file sizes

* Demanding on both hard drives and CPU

* Bit rate fluctuates with amount of detail in video content



**Cineform**

*Pros*

* Constant bit rate

* High image quality

* Native Alpha channel support


*Cons*
    
* file sizes

* Must purchase encoding software from Cineform

