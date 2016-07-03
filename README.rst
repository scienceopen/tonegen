=======
tonegen
=======

Generates a sine wave on the sound card or standard out for Linux and *BSD systems.

Compile
=======
::

    cc -lm tonegen.c -o tonegen

Run
===
Many modern linux systems don't have ``/dev/dsp`` but rather use PulseAudio. No problem, run tonegen with ``padsp`` that emulates ``/dev/dsp``::

    padsp ./tonegen

-a dB       Sets attenuation from "all ones" in dB.  Default is "10 db".
-d device   Sets device name.  Default is "/dev/dsp".
           If "device" is "-" then it uses STDOUT
-f Hz       Sets tone in Hertz.  Default is "1000 Hz".
-r rate     Sets device sample rate in Hertz.  Default is "44100 Hz".
-t seconds  Sets time to run.  Default is infinite.

