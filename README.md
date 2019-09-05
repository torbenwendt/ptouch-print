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
- PT-P700 ( could work but needs a little development first - [see here](https://github.com/clarkewd/ptouch-print/issues/2) )
- PT-D450

**Further info can be found at:**
https://mockmoon-cybernetics.ch/computer/p-touch2430pc/

### Compile instructions:

    ./autogen.sh
    ./configure --prefix=/usr
    make


### Development for PT-P700 series:


- If you plug in the PT-P700 and the green light above the PLite button is on, the printer won't be recognized by `ptouch`. You must hold down the PLite button for ~ 2 seconds and the light will turn off and the system will find the device again.
- This step allowed it to be detected as `vid 0x04F9 pid 0x2061` insetad of `vid 0x04F9 pid 0x2064`
- There is a repository at [https://github.com/abelits/ptouch-770](https://github.com/abelits/ptouch-770) that works 'out of the box' with the PT-700, however it is not well documented and only supports printing `pbm` images (although those can be created with something like `pbmtextps -fontsize=30 -font=Arial "Hello World" > hello.pbm` )
- For the P700 to work with `ptouch`, one change may require the `graphics transfer mode` being set in the `ptouch_rasterstart` using the `\x1b\x69\x61\x01` instead of `\x1b\x69\x52\x01`, according to the documentation for that model.
- [Software Developer's Manual for the PT-P700](https://support.brother.com/g/b/manuallist.aspx?c=us&lang=en&prod=p700eus&flang=English&type3=437&type2=81) ( file name as of today is cv_pth500p700e500_eng_raster_110.pdf )
- You may wish to check out [a log of one user's experience](https://sites.google.com/site/tingox/brother_pt-p700) trying to print using both `ptouch-print` and `ptouch-770-write`


### A Note from Dominic

Dear visitor, currently I have absolutely no time for improvements on this
project (my free time currently is about one or two hours PER MONTH).
Therefore, I can not look at suggestions about improvements.

