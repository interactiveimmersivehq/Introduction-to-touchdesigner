## *3.3 Preloading Movies*

When creating real-time applications, continuous dropped frames can greatly detract from presentation and impact. Diagnosing performance issues is something that will be discussed in a later chapter, but many preventative measures can be taken. Preloading and unloading Movie In TOPs is one of these preventative measures. The simple procedure of preloading and unloading movies is often overlooked by new users because the easiest methods involve scripting.

Open example 'Preloading.toe'. This example has a set of three buttons. The 'Preload' button uses the following Python function to preload the number of frames set in the 'Pre-Read frames' parameter in the 'Tune' parameters of the Operator 'moviein1':


`op('moviein1').preload()`


The 'Play' button starts playback of the Movie In TOP. The 'Unload' button stops 'moviein1' playback, and then unloads the movie, freeing up whatever system resources were being used. This is done with the following Python script:


`op('play').click(0)`

`op('moviein1').unload()`


It is best practice to preload movies before playing them, otherwise there is a high risk of dropping frames upon playback.

{pagebreak}