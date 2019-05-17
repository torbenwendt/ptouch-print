**Notice:** This repo is a clone of the one on [Dominic Radermacher's website](https://mockmoon-cybernetics.ch/computer/p-touch2430pc/), and he is he author.


# ptouch

ptouch is a command line tool to print labels on Brother P-Touch
printers on Linux.

There is no need to install the printer via CUPS, the printer is accessed
directly via libusb.

The tool was written for and tested with the `PT-2430PC`, but it should also
work with the `PT-1230PC` (untested so far). Maybe others work too (please report USB VID and PID so I can include support for further models, too).

**Models in `libptouch.c` include:**

- PT-2420PC
- PT-1230PC
- PT-2430PC
- PT-2730
- PT-2730
- PT-P700 ( could work but needs a little development first )
- PT-D450

**Further info can be found at:**
https://mockmoon-cybernetics.ch/computer/p-touch2430pc/

### Compile instructions:

    ./autogen.sh
    ./configure --prefix=/usr
    make

### A Note from Dominic

Dear visitor, currently I have absolutely no time for improvements on this
project (my free time currently is about one or two hours PER MONTH).
Therefore, I can not look at suggestions about improvements.

