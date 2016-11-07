> Our Trump advertising campaign is incredible, it's skyrocketing! It's astronomical! Wait stop!! SLOW DOWN!!!

This challenge provided the following image:

![warp_speed](warp_speed.jpg)

The word "TRUMP" is just about legible and the text either side of it looks to
be of interest.

Running ```exiftool``` on the image produces the following:

```
ExifTool Version Number         : 10.20
File Name                       : warp_speed.jpg_original
Directory                       : .
File Size                       : 229 kB
File Modification Date/Time     : 2016:11:04 23:23:35+00:00
File Access Date/Time           : 2016:11:07 00:41:30+00:00
File Inode Change Date/Time     : 2016:11:05 00:46:36+00:00
File Permissions                : rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
Exif Byte Order                 : Big-endian (Motorola, MM)
X Resolution                    : 72
Y Resolution                    : 72
Resolution Unit                 : inches
Y Cb Cr Positioning             : Centered
XP Comment                      : I am a square. Anyone who tells you otherwise
is a LIAR!
DCT Encode Version              : 100
APP14 Flags 0                   : [14]
APP14 Flags 1                   : (none)
Color Transform                 : YCbCr
Image Width                     : 1000
Image Height                    : 250
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:4:4 (1 1)
Image Size                      : 1000x250
Megapixels                      : 0.250
```

That comment is definitely a hint! I decided to resize the image to 500x500 in
order to see what would happen. Instead of reaching for python, I decided to
use vim to manually change the width and height in the jpeg header.

After doing so, I was left with the following:

![warp_speed_resized](warp_speed_resized.jpg)

With a bit of squinting and head turning, I put the following flag in the
website for a cool 150 points.

```
flag{1337_ph0t0_sk1ll5}
```
