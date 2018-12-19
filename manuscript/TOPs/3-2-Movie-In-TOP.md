## *3.2 Movie In TOP*

The Movie In TOP is one of the most used TOPs. It's function is to load assets into TouchDesigner. It is capable of loading many different types of assets, ranging from still images to a variety of movie codecs. Below is a small list of common file formats used with the Movie In TOP:


* .mov

* .mp4

* .avi

* .tiff

* .jpeg

* .png



There are many more supported file formats, which are listed on the Derivative TouchDesigner 088 wiki under the 'File Types' page.

There are a few of great features built into the Movie In TOP that can significantly reduce the headaches involved with quickly ingesting and outputting assets with different frame-rates. The main feature is that the Movie In TOP's goal is to playback assets while staying true to its time duration. For example, if the project is set to 60FPS and an asset is made at 30FPS and is 10 seconds long, it will play over the course of 10 seconds, regardless of FPS differences between the project and the asset. The opposite is true as well. If a 10 second asset created at 60 FPS is played in a 30FPS timeline, it will play over the course of 10 seconds. In both of these cases frames are either doubled or discarded to stay true to each asset's real-world time length. This makes interpolation of frames a good idea in some situations.
