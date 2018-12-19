
## *4.3 Audio Inputs and Outputs*

Audio can be processed from a variety of sources, and can be processed in a variety of ways. TouchDesigner is capable of processing audio from audio files, movie files, external audio interfaces, internet audio streams, and can even synthesize audio from nothing. 

Most projects involving sound design and audio tracks will include dedicated audio files. TouchDesigner is capable of reading and playing many standard audio formats such as MP3, AIFF, and WAV, through the use of the Audio File In CHOP and the Audio Play CHOP. These files can be looped, cued, re-pitched, and trimmed, allowing for flexible uses of samples and audio files.

The Audio Movie CHOP can be used to playback audio from a movie file. Instead of reading audio by referencing a file, this CHOP references a Movie In TOP. This is useful because it keeps the audio in sync with the video playing back in the Movie In TOP, and comes with a parameter that can be used to offset the audio to better match the video.

There are many different external audio interfaces that can be used with TouchDesigner. It is best to refer to the Derivative TouchDesigner Wiki and Forum for a more comprehensive list of compatible devices. 

These devices provide analog and digital audio inputs and outputs. These can be inputs from musicians and instrumentalists, audio mixing consoles, professional video cameras, other computer systems, and much more. These devices can output audio to many of the above mentioned destinations, as well as to loud speaker systems. The CHOPs used to communicate with external interfaces are the Audio Device In CHOP and the Audio Device Out CHOP. Each respectively handles the inputs and outputs, to and from, a project. There is an Audio SDI CHOP which is used in conjunction with the nVidia Quadro SDI card, to receive audio from external SDI sources. 

There are two different audio drivers that can be accessed from within TouchDesigner. DirectSound has been available since previous versions of TouchDesigner, and has been developed as a part of DirectX. It is a mature driver, having been in development for many years, and provides relatively low latencies even under heavy use. 

ASIO is a new addition to TouchDesigner 088. It has been developed by Steinberg to improve on one of DirectX's main drawbacks, which is that DirectX feeds all audio through the Windows operating system. Bypassing the operating system, the ASIO driver is able to communicate directly with external audio hardware, thus creating lower latencies than what was previously possible with DirectSound.

Once inputs and outputs are setup in TouchDesigner, they can be routed much like any other data. 