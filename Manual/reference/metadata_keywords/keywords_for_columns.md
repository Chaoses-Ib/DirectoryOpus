# Keywords for Columns

The following keywords are used by the **[Set](../command_reference/internal_commands/set.md)** command (with the **COLUMNS**, **COLUMNSADD**, **COLUMNSREMOVE** and **COLUMNSTOGGLE** arguments) to change which columns are displayed in the file display (in details and power modes), and with the **GROUPBY** and **SORTBY** arguments to modify the group and sort fields. For example, **Set COLUMNSADD=desc** adds the Description column to the file display.

They are also used by the [Rename](/Manual/file_operations/renaming_files/README.md) function when [renaming using metadata](/Manual/file_operations/renaming_files/advanced_rename/renaming_with_metadata.md), and in the [File Types](/Manual/file_types/filetype_editor/README.md) editor when defining your own [tile](/Manual/file_types/filetype_editor/tiles_mode.md) and [infotip](/Manual/file_types/filetype_editor/info_tip.md) definitions.

Note that some columns appear in multiple categories. For historic reasons, column keywords sometimes only reflect a narrow usage when the column actually works in a wider range of situations. For example, the *Duration* column (**mp3songlength**) works with various music file types, and some movie types, not just MP3 music files.

Where columns are used to output text (for example, when generating filenames for a rename, or when displaying info tips), the format of dates, times and numeric values can be overridden.

### Date and time fields

Date and time fields let you configure the date format, the time format, or both. For example,

|                                   |                                                                              |
|-----------------------------------|------------------------------------------------------------------------------|
| **{datetaken\|D#yyyy-MM-dd}**     | inserts the date only in **yyyy-MM-dd** format (e.g. *2023-09-22*)           |
| **{modified\|T#HH-mm-ss}**        | inserts the modified time in **HH-mm-ss** format (e.g. *13:10:55*)           |
| **{datetaken\|A#yyyyMMddHHmmss}** | inserts both the date and time as **yyyyMMddHHmmss** (e.g. *20221130154410*) |

As you can see in the examples, **D#** is used to mark the date format, **T#** is used to mark the time format, and **A#** indicates both date and time codes are present. See the [Codes for date and time](../command_reference/external_control_codes/codes_for_date_and_time.md) page for information on date and time formats.

### Numeric fields

Numeric fields let you control zero-padding. For example,

|                    |                                                               |
|--------------------|---------------------------------------------------------------|
| **{size\|#8}**     | zero-pads the size in bytes to eight places (e.g. *00045412*) |
| **{mp3track\|#2}** | zero-pads the track number to two places (e.g. *08*)          |

The filename can be retrieved without the file extension using **{name\|noext}**.

------------------------------------------------------------------------

## Column keywords

### Date and Time

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>
Create (relative)</td><td>
cdaterel
</td></tr><tr><td>
Date (accessed)</td><td>
accesseddate
</td></tr><tr><td>
Date (created)</td><td>
createddate
</td></tr><tr><td>
Date (modified)</td><td>
modifieddate
</td></tr><tr><td>
Date and Time (accessed)</td><td>
accessed
</td></tr><tr><td>
Date and Time (created)</td><td>
created
</td></tr><tr><td>
Date and Time (modified)</td><td>
modified
</td></tr><tr><td>
Modify (relative)</td><td>
daterel
</td></tr><tr><td>
Time (accessed)</td><td>
accessedtime
</td></tr><tr><td>
Time (created)</td><td>
createdtime
</td></tr><tr><td>
Time (modified)</td><td>
modifiedtime
</td></tr></tbody>
</table>

### Documents

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>
Authors</td><td>
author
</td></tr><tr><td>
Category</td><td>
category
</td></tr><tr><td>
Comment</td><td>
comments
</td></tr><tr><td>
Company</td><td>
companyname
</td></tr><tr><td>
Copyright</td><td>
copyright
</td></tr><tr><td>
Creator</td><td>
creator
</td></tr><tr><td>
Document created date</td><td>
doccreateddate
</td></tr><tr><td>
Last edit time</td><td>
docedittime
</td></tr><tr><td>
Last saved by</td><td>
doclastsavedby
</td></tr><tr><td>
Last saved date</td><td>
doclastsaveddate
</td></tr><tr><td>
Pages</td><td>
pages
</td></tr><tr><td>
Producer</td><td>
producer
</td></tr><tr><td>
Subject</td><td>
subject
</td></tr><tr><td>
Title</td><td>
title
</td></tr></tbody>
</table>

### Name and Path

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>
Extension</td><td>
ext
</td></tr><tr><td>
Extension (dirs)</td><td>
extdir
</td></tr><tr><td>
Filename</td><td>
name
</td></tr><tr><td>
Full path</td><td>
fullpath
</td></tr><tr><td>
Location</td><td>
path
</td></tr><tr><td>
Location (relative)</td><td>
pathrel
</td></tr><tr><td>
Parent folder</td><td>
parent
</td></tr><tr><td>
Parent folder (full)</td><td>
parentlocation
</td></tr><tr><td>
Parent location</td><td>
parentpath
</td></tr><tr><td>
Path length</td><td>
pathlen
</td></tr><tr><td>
Short name</td><td>
shortname
</td></tr></tbody>
</table>

### Picture Dimensions

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>
Aspect ratio</td><td>
aspectratio
</td></tr><tr><td>
Bit depth</td><td>
picdepth
</td></tr><tr><td>
Dimensions</td><td>

picsize  
dimensions
</td></tr><tr><td>
Height</td><td>
picheight
</td></tr><tr><td>
Physical height</td><td>
picphysy
</td></tr><tr><td>
Physical size</td><td>
picphyssize
</td></tr><tr><td>
Physical width</td><td>
picphysx
</td></tr><tr><td>
Resolution (X)</td><td>
picresx
</td></tr><tr><td>
Resolution (Y)</td><td>
picresy
</td></tr><tr><td>
Rotation</td><td>
rotation
</td></tr><tr><td>
Width</td><td>
picwidth
</td></tr></tbody>
</table>

### Picture Metadata

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>
Altitude</td><td>
altitude
</td></tr><tr><td>
Aperture</td><td>
apertureval
</td></tr><tr><td>
Artists</td><td>
mp3artist
</td></tr><tr><td>
Camera make</td><td>
cameramake
</td></tr><tr><td>
Camera model</td><td>
cameramodel
</td></tr><tr><td>
Color model</td><td>
colormodel
</td></tr><tr><td>
Contrast</td><td>
contrast
</td></tr><tr><td>
Coordinates</td><td>
coords
</td></tr><tr><td>
Copyright</td><td>
copyright
</td></tr><tr><td>
Creation software</td><td>
software
</td></tr><tr><td>
Date digitized</td><td>
datedigitized
</td></tr><tr><td>
Date taken</td><td>

datetaken  
shootingtime
</td></tr><tr><td>
Digital Zoom</td><td>
digitalzoom
</td></tr><tr><td>
Exposure bias</td><td>
exposurebias
</td></tr><tr><td>
Exposure program</td><td>
exposureprogram
</td></tr><tr><td>
Exposure time</td><td>
exposuretime
</td></tr><tr><td>
F-number</td><td>
fnumber
</td></tr><tr><td>
Flash</td><td>
flash
</td></tr><tr><td>
Focal length</td><td>
focallength
</td></tr><tr><td>
Focal length (35mm)</td><td>
35mmfocallength
</td></tr><tr><td>
ISO speed</td><td>
isorating
</td></tr><tr><td>
Image description</td><td>
imagedesc
</td></tr><tr><td>
Image quality</td><td>
imagequality
</td></tr><tr><td>
Latitude</td><td>
latitude
</td></tr><tr><td>
Lens make</td><td>
lensmake
</td></tr><tr><td>
Lens model</td><td>
lensmodel
</td></tr><tr><td>
Longitude</td><td>
longitude
</td></tr><tr><td>
Macro mode</td><td>
macromode
</td></tr><tr><td>
Metering mode</td><td>
meteringmode
</td></tr><tr><td>
Saturation</td><td>
saturation
</td></tr><tr><td>
Scene capture type</td><td>
scenecapturetype
</td></tr><tr><td>
Scene mode</td><td>
scenemode
</td></tr><tr><td>
Sharpness</td><td>
sharpness
</td></tr><tr><td>
Shutter speed</td><td>
shutterspeed
</td></tr><tr><td>
Subject</td><td>
subject
</td></tr><tr><td>
Subject distance</td><td>
subjectdistance
</td></tr><tr><td>
Special instructions</td><td>
instructions
</td></tr><tr><td>
Title</td><td>
title
</td></tr><tr><td>
White balance</td><td>
whitebalance
</td></tr></tbody>
</table>

### Programs

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>
Copyright</td><td>
copyright
</td></tr><tr><td>
Company</td><td>
companyname
</td></tr><tr><td>
Module Description</td><td>
moddesc
</td></tr><tr><td>
Module Version</td><td>
modversion
</td></tr><tr><td>
Product Name</td><td>
prodname
</td></tr><tr><td>
Product Version</td><td>
prodversion
</td></tr></tbody>
</table>

### File Size

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>
Size (KB)</td><td>
sizekb
</td></tr><tr><td>
Size (auto)</td><td>
sizeauto
</td></tr><tr><td>
Size (bytes)</td><td>
size
</td></tr><tr><td>
Size (relative)</td><td>
sizerel
</td></tr><tr><td>
Size on disk (KB)</td><td>
disksizekb
</td></tr><tr><td>
Size on disk (auto)</td><td>
disksizeauto
</td></tr><tr><td>
Size on disk (bytes)</td><td>
disksize
</td></tr><tr><td>
Size on disk (relative)</td><td>
disksizerel
</td></tr><tr><td>
Uncompressed Size</td><td>
uncompressedsize
</td></tr></tbody>
</table>

### General

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>
Attributes</td><td>
attr
</td></tr><tr><td>
Availability</td><td>
availability
</td></tr><tr><td>
Description</td><td>
desc
</td></tr><tr><td>
File count</td><td>
filecount
</td></tr><tr><td>
Font name</td><td>
fontname
</td></tr><tr><td>
Group</td><td>
group
</td></tr><tr><td>
Index</td><td>
index
</td></tr><tr><td>
Label</td><td>
label
</td></tr><tr><td>
MD5 checksum</td><td>
md5sum
</td></tr><tr><td>
Owner</td><td>
owner
</td></tr><tr><td>
Rating</td><td>
rating
</td></tr><tr><td>
SHA-1 checksum</td><td>
shasum
</td></tr><tr><td>
Status Icons</td><td>
status
</td></tr><tr><td>
Sub-folder count</td><td>
dircount
</td></tr><tr><td>
Tags</td><td>
keywords
</td></tr><tr><td>
Target</td><td>
target
</td></tr><tr><td>
Thumbnail</td><td>
thumbnail
</td></tr><tr><td>
Total File count</td><td>
filecounttotal
</td></tr><tr><td>
Total Sub-folder count</td><td>
dircounttotal
</td></tr><tr><td>
Type</td><td>
type
</td></tr><tr><td>
User description</td><td>
userdesc
</td></tr></tbody>
</table>

### Movies

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>
Aspect ratio</td><td>
aspectratio
</td></tr><tr><td>
Audio codec</td><td>

audiocodec  
mp3type
</td></tr><tr><td>
Bit depth</td><td>
picdepth
</td></tr><tr><td>
Bit rate</td><td>
mp3bitrate
</td></tr><tr><td>
Broadcast date</td><td>
broadcastdate
</td></tr><tr><td>
Channel number</td><td>
channel
</td></tr><tr><td>
Credits</td><td>
credits
</td></tr><tr><td>
Data rate</td><td>
datarate
</td></tr><tr><td>
Dimensions</td><td>

picsize  
dimensions
</td></tr><tr><td>
Duration</td><td>

duration  
mp3songlength
</td></tr><tr><td>
Episode name</td><td>
episodename
</td></tr><tr><td>
FOURCC code</td><td>
fourcc
</td></tr><tr><td>
Frame rate</td><td>
framerate
</td></tr><tr><td>
Height</td><td>
picheight
</td></tr><tr><td>
High definition?</td><td>
ishd
</td></tr><tr><td>
Mode</td><td>
mp3mode
</td></tr><tr><td>
Physical size</td><td>
picphyssize
</td></tr><tr><td>
Publisher</td><td>
publisher
</td></tr><tr><td>
Recording time</td><td>
recordingtime
</td></tr><tr><td>
Repeat?</td><td>
isrepeat
</td></tr><tr><td>
Sample rate</td><td>
mp3samplerate
</td></tr><tr><td>
Station name</td><td>
station
</td></tr><tr><td>
Video codec</td><td>
videocodec
</td></tr><tr><td>
Width</td><td>
picwidth
</td></tr></tbody>
</table>

### Music

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>
Album</td><td>
mp3album
</td></tr><tr><td>
Album artist</td><td>
mp3albumartist
</td></tr><tr><td>
Artists</td><td>
mp3artist
</td></tr><tr><td>
Audio codec</td><td>

audiocodec  
mp3type
</td></tr><tr><td>
BPM</td><td>
mp3bpm
</td></tr><tr><td>
Bit depth</td><td>
picdepth
</td></tr><tr><td>
Bit rate</td><td>
mp3bitrate
</td></tr><tr><td>
Compilation</td><td>
compilation
</td></tr><tr><td>
Composers</td><td>
composers
</td></tr><tr><td>
Conductors</td><td>
conductors
</td></tr><tr><td>
Copyright</td><td>
copyright
</td></tr><tr><td>
Disc number</td><td>

mp3disc  
mp3disk
</td></tr><tr><td>
Duration</td><td>
mp3songlength
</td></tr><tr><td>
Encoded by</td><td>
mp3encoder
</td></tr><tr><td>
Encoding Software</td><td>
mp3encodingsoftware
</td></tr><tr><td>
Genre</td><td>
mp3genre
</td></tr><tr><td>
Initial key</td><td>
initialkey
</td></tr><tr><td>
Mode</td><td>
mp3mode
</td></tr><tr><td>
Music comment</td><td>
mp3comment
</td></tr><tr><td>
Music info</td><td>
mp3info
</td></tr><tr><td>
Music title</td><td>
mp3title
</td></tr><tr><td>
Protected</td><td>
mp3drm
</td></tr><tr><td>
Release date</td><td>
releasedate
</td></tr><tr><td>
Sample rate</td><td>
mp3samplerate
</td></tr><tr><td>
Track number</td><td>
mp3track
</td></tr><tr><td>
Year</td><td>
mp3year
</td></tr></tbody>
</table>

You can also access some columns that aren't part of the standard set of columns shown above. These can come from various places - third-party shell namespace extensions can provide custom columns, as can Opus plugins. Additionally, Zip and FTP define several columns that are only valid in those types of folders. In Opus, these columns all appear under the **Other** category. To refer to one of these columns from a command you need to know the name of the column, and then use the appropriate prefix to indicate that you want to use a special column.

![](/Manual/images/media/special_columns.png) 

Columns provided by shell extensions (as in the screenshot above) are prefixed with **sh:** in Opus - the keyword for the column is the name shown in the list without spaces.

For example, to add the **SVN Status** column you might use the command **Set COLUMNSADD sh:svnstatus**.

Columns provided by plugins (e.g. the 7-Zip plugin) must be prefixed by the name of the plugin DLL (e.g. **opus7zip:packed**).

The following column keywords are provided by Opus but only valid in certain folders:

- *FTP* keywords are only valid in an **ftp://** path
- *Zip* keywords are only valid when viewing a Zip archive
- *7-Zip* keywords are only valid when viewing an archive handled by the 7-Zip plugin
- *Computer* keywords are only valid when viewing the [native Computer folder](/Manual/basic_concepts/virtual_file_system/system_virtual_folders.md)

<table>
<thead><tr><th>
Column</th><th>
Keyword
</th></tr></thead><tbody><tr><td>

\$ **FTP keywords**</td><td>
Transfer time
</td></tr><tr><td>
<ftp:xfertime></td><td>
Group
</td></tr><tr><td>
<ftp:group></td><td>

\$ **Computer keywords**
</td></tr><tr><td>
Free space on drive</td><td>
sh:freespace
</td></tr><tr><td>
File system</td><td>
sh:filesys
</td></tr><tr><td>
Used space (graph)</td><td>
sh:usedpercent
</td></tr><tr><td>
Free space (graph)</td><td>
sh:freepercent
</td></tr><tr><td>
Network location</td><td>
sh:netlocation
</td></tr><tr><td>
Used space on drive</td><td>
sh:usedspace
</td></tr><tr><td>

\$ **Zip keywords**</td><td>
Compressed size
</td></tr><tr><td>
zip:compsize</td><td>
Compression ratio
</td></tr><tr><td>
zip:compratio</td><td>
Compression method
</td></tr><tr><td>
zip:compmethod</td><td>
CRC checksum
</td></tr><tr><td>
zip:compcrc</td><td>

\$ **7-Zip keywords**
</td></tr><tr><td>
Packed size</td><td>
opus7zip:packed
</td></tr><tr><td>
Ratio</td><td>
opus7zip:ratio
</td></tr><tr><td>
CRC</td><td>
opus7zip:crc
</td></tr><tr><td>
Block</td><td>
opus7zip:block
</td></tr><tr><td>
Index</td><td>
opus7zip:index
</td></tr><tr><td>
Is solid?</td><td>
opus7zip:solid
</td></tr><tr><td>
Method</td><td>
opus7zip:method
</td></tr><tr><td>
Mode</td><td>
opus7zip:mode
</td></tr><tr><td>
Link</td><td>
opus7zip:link
</td></tr><tr><td>
User</td><td>
opus7zip:user
</td></tr><tr><td>
Group</td><td>
opus7zip:group
</td></tr></tbody>
</table>

