# gst_sample_appln

sample gstreamer application which demonstrate the ogg container audio file playback

audio-player Application written based on gstreamer libraries and tools.

this application code cover the gstreamer initialization, pipeline creation which include the elements creation(audio-player,file-source, ogg-demuxer, vorbis-decoder,converter,audio-output), setting properties for source element(file source location which reads the file from disk), adding message handler (bus concept) to pipeline, pipeline formation (making bin container element by adding all the elements into the pipeline), linking the elements, dynamic pad creation (source pad created for demuxer element which is handled the parsing the ogg stream into audio elementary stream), set the "pad-added" event handler on the demuxer element ( linking the demuxer and decoder element), running pipeline (setting state of element like PLAYING,NULL), deleting the pipeline (unreferecing the object).

-----------------------------------------------------------------------------------------------
Linux Ubuntu Machine used for application execution.
******************************************************

root@ubuntu:/home/emertxe/dharma/gst_sample_appln# lsb_release -a

No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 18.04.4 LTS
Release:	18.04
Codename:	bionic

root@ubuntu:/home/emertxe/dharma/gst_sample_appln# uname -r

4.15.0-99-generic

---------------------------------------------------------------------------------------------

Install gstreamer related package on ubuntu OS:
*****************************************************

https://gstreamer.freedesktop.org/documentation/installing/on-linux.html?gi-language=c

apt-get install pkg-config
sudo apt-get install libgstreamer1.0-dev

-----------------------------------------------------------------------------------------------

Application compilation command:
*********************************


root@ubuntu:/home/emertxe/dharma/gst_sample_appln# gcc -Wall audioplaybackappln.c -o audioplaybackappln $(pkg-config --cflags --libs gstreamer-1.0)

-----------------------------------------------------------------------------------------------

Application execution run command:
***********************************

root@ubuntu:/home/emertxe/dharma/gst_sample_appln# ./audioplaybackappln file_example.ogg 


Now playing: file_example.ogg
Running...
Dynamic pad created, linking demuxer/decoder
End of stream
Returned, stopping playback
Deleting pipeline

-----------------------------------------------------------------------------------------------


Primary Reading:
********************

GObject instantiation

GObject properties(set/get)

GObject casting

GObject referencing/dereferencing

glib memory management

glib signals and callbacks

glib main loop

