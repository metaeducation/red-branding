# DOCUMENT ICONS

Document icons on most systems are graphics that are somehow connected with the relevant application which are stuck onto things that look like pieces of paper with a corner folded over.

A red-colored version of the monochrome flat logo (minus the box) is used for Red's .RED files, while the Red/System logo is used for .REDS files.

The root directory contains some Photoshop files at different resolutions.  Although it's early in the process to know exactly how it will turn out, the hope is that these files will have common layers, and only change the lowest layer (the operating system's "blank document" template).  Though the process of exporting is manual, these would ideally be exported and packed into icons by some kind of script.

*(Note: Currently a layer in the Photoshop files exists for [Rebol](http://en.wikipedia.org/wiki/Rebol) as well, because the document icons were designed together as a set. When the methods for creating the document icons across platforms has stabilized, that should be moved into a branding repository for Rebol.)*


## OS/X .ICNS

The baseline for the OS/X document bitmaps is the GenericBlankDocument template, found in `/System/Library/CoreServices/CoreTypes.bundle/Contents/Resources/GenericDocument.icns`:

http://stackoverflow.com/questions/3454201/mac-os-x-document-icon-template

OS/X icons are stored in the ".ICNS" file format.  As of 2014, the expected list of files to produce a ICNS file is:

* icon_16x16.png
* icon_16x16@2x.png
* icon_32x32.png
* icon_32x32@2x.png
* icon_128x128.png
* icon_128x128@2x.png
* icon_256x256.png
* icon_256x256@2x.png
* icon_512x512.png
* icon_512x512@2x.png

In order to be processed by the `iconutil` packing utility *(which ships with OS/X)*, the files must have exactly those names.  They must also be in a directory whose suffix is `.iconset`.

Files ending in `@2x` are used in high resolution contexts.  Thus, `icon_16x16@2x.png` is actually 32x32 pixels in size.  It was traditionally the case that details are added at higher bitmap sizes due to the expectation that a bitmap will be *larger*.  Yet this distinction allows one the ability to make use of more resolution with the understanding that the bitmap will not actually be any bigger.

To turn the directories containg the files into .ICNS files, change to the `osx/` directory and run:

    iconutil -c icns -o red-doc.icns red-doc.iconset

    iconutil -c icns -o red-system-doc.icns red-doc.iconset


## Windows

TBD...


## Linux

TBD...
