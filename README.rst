.. image:: https://travis-ci.org/scienceopen/tonegen.svg?branch=master
    :target: https://travis-ci.org/scienceopen/tonegen

=======
tonegen
=======

Generates a sine wave on the sound card or standard out for Linux and *BSD systems.

.. contents::

Compile
=======
::
    
    make

or::

    cc tonegen.c -o tonegen -lm

Run
===
::

    ./tonegen

-a dB       Sets attenuation from "all ones" in dB.  Default is "10 db".
-d device   Sets device name.  Default is "/dev/dsp".
           If "device" is "-" then it uses STDOUT
-f Hz       Sets tone in Hertz.  Default is "1000 Hz".
-r rate     Sets device sample rate in Hertz.  Default is "44100 Hz".
-t seconds  Sets time to run.  Default is infinite.

No Sound!
=========
The program default is to output to ``/dev/dsp`` that is the file handle used by OSS. Since 1999, many Linux OS have moved to ALSA, PulseAudio, or the like. If you don't get sound from::

    ./tonegen

try the section applying to your OS.

PulseAudio
----------
run tonegen with ``padsp`` that emulates ``/dev/dsp``::

    padsp ./tonegen

Mac and others not working
--------------------------
Perhaps try ``sox`` ``play``. If this works for you, use the ``tonesox`` script::

    ./tonegen -d - | play -t raw -b 16 -e signed -c 1 -r 44100 -

