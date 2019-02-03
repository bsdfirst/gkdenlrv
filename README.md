# gkdenlrv

## What is it?

gkdenlrv imports files from your GoPro SD card in such a manner that:

1. They are sensible named.
1. The GoPro LRV file is placed appropriately to be detected by Kdenlive and used directly as a proxy file.


## What is it using more words?

When recording at higher resolutions, modern GoPro cameras create a Low Resolution Video (LRV) file in addition to a full-resolution MP4.  Unless you have a supercomputer, you are probably using proxy files when editing high resolution video within Kdenlive.  The only problem with proxy files is that if you import 200 GiB of 4K video, it is likely to take a week to actually create them all.  (I'm probably hyperbolising - but I imagine not by much, I don't have the patience to test that!)

gkdenlive imports files from your mounted GoPro SD card into a Kdenlive project folder structure.  The GoPro LRV files are placed in the correct location for Kdenlive to detect and use them.  Additionally, the "sense" of the default GoPro filenames is reversed so that a basic alphabetical source places videos into the order they were shot (including videos that span multiple files).

For example, this (in alphabetical order):

```
GH013560.MP4
GX013458.MP4
GX013488.MP4
GX023458.MP4
```

Becomes this (in alphabetical order):

```
G3458_01_X.MP4
G3458_02_X.MP4
G3488_01_X.MP4
G3560_01_H.MP4
```

## How do I use it?

Clone this repository and make sure that the `gkdenlrv` script is in your path and executeable:

```
$ git clone git@github.com:bsdfirst/gkdenlrv.git
$ cd gkdenlrv
$ cp gkdenlrv ~/.local/bin
```


Create an empty directory to hold your Kdenlive project:

```
mkdir MyVideoProject
```


Use gkdenlrv to import files from your previously mounted SD card:

```
cd MyVideoProject
gkdenlrv /path/to/my/mounted/sdcard
```

Now simply follow the instructions at the termination of the script to create your project within Kdenlive and enjoy not waiting for proxy file renders!

Running gkdenlrv with no options will output a usage/help page.


## License
This utility is released under the GNU Public License v3.0.  At it's simplest, you can do whatever you want with this script, but if you modify it, you should release your changes for the benefit of others.  See the LICENSE file for more details.

_Copyright (c) 2019  Patrick M. Brennan_
