# Keywords for SetAttr META

The following keywords can be used to modify file metadata [programmatically](/Manual/file_operations/editing_metadata/programmatic_setting_of_metadata.md) with the **[SetAttr](../command_reference/internal_commands/setattr.md) META** command. Most fields can only be set to a string (or number), or cleared, however some fields accept more complex instructions, and these are noted below.

<table>
<thead><tr><th>
Field</th><th>
Keyword</th><th>
Notes
</th></tr></thead><tbody><tr><td>

**Standard Properties**</td><td>
</td><td>

</td></tr><tr><td>
Attributes</td><td>
attr</td><td>

Attributes are specified with one or more of the following letters:  
**A** (archive)  
**R** (read-only)  
**H** (hidden)  
**S** (system)  
**C** (compressed)  
**E** (encrypted)

You can also use **+** to turn attributes on and **-** to turn attributes off.

//<Example://>

**SetAttr META attr:+c-r***   - sets compression and clears read-only attributes*
</td></tr><tr><td>
Date created</td><td>
createdate</td><td>

The date and time can be set to an absolute date (in which case the time will be unchanged), an absolute time (in which case the date will be unchanged), or both.  
The accepted formats for an absolute time and date are:  
**YYYY-MM-DD** - set just the date  
**HH:MM:SS** - sets just the time  
**YYYY-MM-DD HH:MM:SS** - sets both time and date (needs quotes)  
The keyword **now** can also be given to use the current date and time.  
You can also perform relative adjustments to the current date and time setting, using the following formats:  
**\<time-adjust\> ** - adjusts only the time  
**\<date-adjust\> \<time-adjust\>**  - adjusts both date and time (needs quotes)

The valid formats of the **\<time-adjust\>** string are:  
**\[+-\]H:M:S**  - add or subtract hours, minutes and seconds  
**\[+-\]H:M**  - add or subtract hours and minutes  
**\[+-\]H**  - add or subtract a number of hours  
The valid formats of the **\<date-adjust\>** string are:  
**\[+-\]Y:M:D**  - add or subtract a year, month and day value  
**\[+-\]M:D**  - add or subtract a month and day value  
**\[+-\]D**  - add or subtract a number of days

You can't adjust the date without also adjusting the time - so specify 0 for *\<time-adjust\>* if you only want to adjust the date.

*Example*:

**SetAttr META createdate:now***   - sets the creation date to the current date/time*  
**SetAttr META createdate:20100922***   - sets creation date to Sep 22, 2010*  
**SetAttr META "createdate:20100922 15:30:30"***   - also sets time to 3:30 pm*  
**SetAttr META createdate:+1:30***   - adds 1h30m to creation time*  
**SetAttr META "createdate:+1 0"***   - adds 1 day (and zero hours)*

You can also copy the values from another date field by specifying the other field's name: **createdate**, **lastmodifieddate**, **datedigitized** or **datetaken**. (For backward compatibility, **modifydate** also works as an alias of lastmodifieddate.)

*Example*:

**SetAttr META createdate:lastmodifieddate***   - sets the creation date to the file's last modified date/time*
</td></tr><tr><td>
Date modified</td><td>
lastmodifieddate</td><td>

Accepts the same values as **createdate** (described above).
</td></tr><tr><td>

**  
Extended Properties**</td><td>
</td><td>

</td></tr><tr><td>
Comment</td><td>
comment  
usercomment</td><td>
User-defined string.
</td></tr><tr><td>
Rating</td><td>
rating</td><td>

Accepts a value from **0** (to clear the rating) through to **5** (5 stars).
</td></tr><tr><td>
Tags</td><td>
tags</td><td>

Accepts multiple semi-colon separated tags. You can either set the tags absolutely, or add tags to or remove tags from the existing set.

*Example*:

**SetAttr META tags:one;two***   - sets the tags to "one" and "two"*  
**SetAttr META tags:+one***   - adds the tag "one" to any existing tags*  
**SetAttr META tags:+one;-two***   - adds "one" and removes "two"*
</td></tr><tr><td>

**  
Picture Properties**</td><td>
</td><td>

</td></tr><tr><td>
Aperture</td><td>
aperture</td><td>
Accepts either a decimal or fractional value.
</td></tr><tr><td>
Camera make</td><td>
cameramake</td><td>
User-defined string.
</td></tr><tr><td>
Camera model</td><td>
cameramodel</td><td>
User-defined string.
</td></tr><tr><td>
Contrast</td><td>
contrast</td><td>

Accepts the following values (either the *value* or the *keyword* can be used):

\<WRAP\>

| Value | Keyword |
|-------|---------|
| 0     | normal  |
| 1     | soft    |
| 2     | hard    |

\</WRAP\>\<wrap clear/\>

//<Example://>

**SetAttr META contrast:2**
</td></tr><tr><td>
Creation software</td><td>
software</td><td>
User-defined string.
</td></tr><tr><td>
Date digitized</td><td>
datedigitized</td><td>

Accepts the same values as **createdate** (described above in the **Standard Properties** section).
</td></tr><tr><td>
Date taken</td><td>
datetaken</td><td>

Accepts the same values as **createdate** (described above in the **Standard Properties** section).
</td></tr><tr><td>
Digital Zoom</td><td>
digitalzoom</td><td>

Accepts a decimal or fractional value, as well as the keyword **off**.
</td></tr><tr><td>
Exposure bias</td><td>
exposurebias</td><td>
Accepts either a decimal or fractional value.
</td></tr><tr><td>
Exposure program</td><td>
exposureprogram</td><td>

Accepts the following values (either the *value* or the *keyword* can be used):  
\<WRAP\>

  
^Value^Keyword^

|     |                  |
|-----|------------------|
| 0   | notdefined       |
| 1   | manual           |
| 2   | auto             |
| 3   | aperturepriority |
| 4   | shutterpriority  |
| 5   | creativeprogram  |
| 6   | actionprogram    |
| 7   | portraitmode     |
| 8   | landscapemode    |

\</WRAP\>\<wrap clear/\>

*Example*:

**SetAttr META exposureprogram:aperturepriority**
</td></tr><tr><td>
Exposure time</td><td>
exposuretime</td><td>

Specified in seconds or fractions of a second - accepts either a decimal or fractional value.
</td></tr><tr><td>
F-number</td><td>
fnumber</td><td>
Accepts either a decimal or fractional value.
</td></tr><tr><td>
Flash</td><td>
flash</td><td>

Accepts the following values (either the *value* or the *keyword* can be used):  
\<WRAP\>

  
^Value^Keyword^

|      |                                                        |
|------|--------------------------------------------------------|
| 0x00 | noflash                                                |
| 0x01 | fired                                                  |
| 0x05 | fired,strobereturnlightnotdetected                     |
| 0x07 | fired,strobereturnlightdetected                        |
| 0x08 | yes,didnotfire                                         |
| 0x09 | yes,compulsory                                         |
| 0x0d | yes,compulsory,returnlightnotdetected                  |
| 0x0f | yes,compulsory,returnlightdetected                     |
| 0x10 | no,compulsory                                          |
| 0x14 | no,didnotfire,returnnotdetected                        |
| 0x18 | no,auto                                                |
| 0x19 | yes,auto                                               |
| 0x1d | yes,auto,returnlightnotdetected                        |
| 0x1f | yes,auto,returnlightdetected                           |
| 0x20 | noflashfunction                                        |
| 0x41 | yes,red-eyereduction                                   |
| 0x45 | yes,red-eyereduction,returnlightnotdetected            |
| 0x47 | yes,red-eyereduction,returnlightdetected               |
| 0x49 | yes,compulsory,red-eyereduction                        |
| 0x4d | yes,compulsory,red-eyereduction,returnlightnotdetected |
| 0x4f | yes,compulsory,red-eyereduction,returnlightdetected    |
| 0x50 | no,red-eyereduction                                    |
| 0x58 | no,auto,red-eyereduction                               |
| 0x59 | yes,auto,red-eyereduction                              |
| 0x5d | yes,auto,red-eyereduction,returnlightnotdetected       |
| 0x5f | yes,auto,red-eyereduction,returnlightdetected          |

\</WRAP\>\<wrap clear/\>

Alternatively, the following codes can be used in conjunction to represent the various states:

- **Y**: Flash fired.
- **N**: Flash did not fire.
- **S\[yn-\]**: Strobe return; **y**: detected, **n**: not detected, **-**: not present
- **C\[yna\]**: Compulsory; **y**: yes, **n**: no, **a**: auto
- **P\[yn\]**: Flash present; **y**: yes, **n**: no
- **R\[yn\]**: Red-eye reduction; **y**: yes, **n**:no

//<Example://>

**SetAttr META flash:0x50  
SetAttr META flash:yes,auto,red-eyereduction  
SetAttr META flash:YCaRy**
</td></tr><tr><td>
Focal length</td><td>
focallength</td><td>

Specified in millimetres - accepts either a decimal or fractional value.
</td></tr><tr><td>
Focal length (35mm)</td><td>
35mmfocallength</td><td>

Specified in millimetres - accepts either a decimal or fractional value.
</td></tr><tr><td>
GPS Altitude</td><td>
gpsaltitude</td><td>

Specified as metres relative to sea level - accepts either a decimal or fractional value. Specify a negative number to reference below sea level.

//<Example://>

**SetAttr META gpsaltitude:-423**
</td></tr><tr><td>
GPS Latitude</td><td>
gpslatitude</td><td>

Accepts coordinates in any of the following formats:  
\<WRAP\>

  
\|45:26:46N\|

|               |
|---------------|
| 45:26:46.302N |
| 45N26 21      |
| 45.446195N    |
| 45.446195     |
| N45° 26.7717' |
| 45°26'21"N    |

\</WRAP\>\<wrap clear/\>

//<Example://>

**SetAttr META gpslatitude:45:26:46.302N**
</td></tr><tr><td>
GPS Longitude</td><td>
gpslongitude</td><td>

Accepts coordinates in any of the following formats:  
\<WRAP\>

  
\|65:56:55W\|

|                |
|----------------|
| 65:56:55.903W  |
| 65W58 36       |
| 65.948862W     |
| -65.948862     |
| W65° 56.93172' |
| 65°58'36"W     |

\</WRAP\>\<wrap clear/\>

//<Example://>

**SetAttr META gpslongitude:65W58.36**
</td></tr><tr><td>
Image description</td><td>
imagedesc</td><td>
User-defined string.
</td></tr><tr><td>
ISO speed</td><td>
isospeed</td><td>
Accepts a numeric value.
</td></tr><tr><td>
Metering mode</td><td>
meteringmode</td><td>

Accepts the following values (either the *value* or the *keyword* can be used):  
\<WRAP\>

  
^Value^Keyword^

|     |                       |
|-----|-----------------------|
| 0   | unknown               |
| 1   | average               |
| 2   | centerweightedaverage |
| 3   | spot                  |
| 4   | multi-spot            |
| 5   | multi-segment         |
| 6   | partial               |
| 255 | other                 |

\</WRAP\>\<wrap clear/\>
</td></tr><tr><td>
Rotation</td><td>
orientation</td><td>

Accepts the values **0**, **90**, **180** and **270**.  
Also accepts a delta value to adjust the existing orientation value.

//<Example://>

**SetAttr META orientation:90***   - set orientation to 90*  
**SetAttr META orientation:-90***   - rotate orientation 90 degrees counter-clockwise*
</td></tr><tr><td>
Saturation</td><td>
saturation</td><td>

Accepts the following values (either the *value* or the *keyword* can be used):

\<WRAP\>

  
^Value^Keyword^

|     |        |
|-----|--------|
| 0   | normal |
| 1   | low    |
| 2   | high   |

\</WRAP\>\<wrap clear/\>
</td></tr><tr><td>
Scene capture type</td><td>
scenecapturetype</td><td>

Accepts the following values (either the *value* or the *keyword* can be used):

\<WRAP\>

  
^Value^Keyword^

|     |            |
|-----|------------|
| 0   | standard   |
| 1   | landscape  |
| 2   | portrait   |
| 3   | nightscene |

\</WRAP\>\<wrap clear/\>
</td></tr><tr><td>
Sharpness</td><td>
sharpness</td><td>

Accepts the following values (either the *value* or the *keyword* can be used):

\<WRAP\>

  
^Value^Keyword^

|     |        |
|-----|--------|
| 0   | normal |
| 1   | soft   |
| 2   | hard   |

\</WRAP\>\<wrap clear/\>
</td></tr><tr><td>
Shutter speed</td><td>
shutterspeed</td><td>

Specified in seconds or fractions of a second - accepts either a decimal or fractional value.
</td></tr><tr><td>
Special instructions</td><td>
instructions</td><td>
User-defined string.
</td></tr><tr><td>
Subject distance</td><td>
subjectdistance</td><td>

Specified in either metres or millimetres - accepts either a decimal or fractional value.

//<Example://>

**SetAttr META subjectdistance:10.3mm** *   - 10.3 millimetres*  
**SetAttr META subjectdistance:50m** *   - 50 metres*
</td></tr><tr><td>
White balance</td><td>
whitebalance</td><td>

Accepts the following values (either the *value* or the *keyword* can be used):

\<WRAP\>

  
^Value^Keyword^

|     |        |
|-----|--------|
| 0   | auto   |
| 1   | manual |

\</WRAP\>\<wrap clear/\>
</td></tr><tr><td>

**  
Music Properties**</td><td>
</td><td>

</td></tr><tr><td>
Album</td><td>
album</td><td>
User-defined string.
</td></tr><tr><td>
Album artist</td><td>
albumartist</td><td>
User-defined string.
</td></tr><tr><td>
Compilation</td><td>
compilation</td><td>

iTunes Compilation tag. Can be **True** (**1**) or **False** (**0**).
</td></tr><tr><td>
Cover art</td><td>
coverart</td><td>

This can set, add and remove cover art.

To set cover art (removes any existing art), the value must be specified as:  
*type***:***\<filename\>*  
To add cover art (adds to existing art):  
***+**type***:***\<filename\>*  
To remove cover art (removes any art of a certain type):  
**-***type*

The cover art type can be specified as follows (either the *value* or the *keyword* can be used):  
\<WRAP\>

  
^Value^Keyword^

|     |               |
|-----|---------------|
| 3   | front         |
| 4   | back          |
| 0   | other         |
| 1   | icon          |
| 2   | otherfileicon |
| 5   | leaflet       |
| 6   | media         |
| 7   | leadartist    |
| 8   | artist        |
| 9   | conductor     |
| 10  | band          |
| 11  | composer      |
| 12  | lyricist      |
| 13  | location      |
| 14  | recording     |
| 15  | performance   |
| 16  | vidcap        |
| 17  | colorfulfish  |
| 18  | illustration  |
| 19  | bandlogo      |
| 20  | publisherlogo |

\</WRAP\>\<wrap clear/\>

//<Example://>

**SetAttr META "coverart:3:/mypictures/Pink Floyd.jpg"  
SetAttr META "coverart:front:clip"** *- sets cover image from the clipboard*  
**SetAttr META coverart:-back** *   - removes all back cover images***  
SetAttr META coverart *** - removes all images*
</td></tr><tr><td>
Disc number</td><td>
discnumber</td><td>

Accepts either a single digit (the number of the disc), or two digits separated by a forward slash (the number of the disc and the total number of discs in the set).

//<Example://>

**SetAttr META discnumber:3/8**
</td></tr><tr><td>
Initial key</td><td>
initialkey</td><td>
User-defined string.
</td></tr><tr><td>
Original artists</td><td>
origartist</td><td>
User-defined string.
</td></tr><tr><td>
Release date</td><td>
releasedate</td><td>

Accepts **YYYYMMDD** or **YYYY-MM-DD** format for the date.

//<Example://>

**SetAttr META releasedate:1973-03-01**
</td></tr><tr><td>
Track number</td><td>
track</td><td>

Accepts either a single digit (the number of the track), or two digits separated by a forward slash (the number of the track and the total number of tracks on the disk). Append a + to the value to activate auto-increment mode.

//<Example://>

**SetAttr META track:5/14**
</td></tr><tr><td>

**  
Video Properties**</td><td>
</td><td>

</td></tr><tr><td>
Directors</td><td>
directors</td><td>
User-defined string. Multiple directors can be separated with semi-colons.
</td></tr><tr><td>
Producers</td><td>
producers</td><td>
User-defined string. Multiple producers can be separated with semi-colons.
</td></tr><tr><td>
Writers</td><td>
writers</td><td>
User-defined string. Multiple writers can be separated with semi-colons.
</td></tr><tr><td>

**  
Music and Video Properties**</td><td>
</td><td>

</td></tr><tr><td>
Author URL</td><td>
authorurl</td><td>
User-defined string.
</td></tr><tr><td>
Artists</td><td>
artist</td><td>
User-defined string. Multiple artists can be separated with semi-colons.
</td></tr><tr><td>
BPM</td><td>
bpm</td><td>
Accepts a numeric value.
</td></tr><tr><td>
Composers</td><td>
composers</td><td>
User-defined string. Multiple composers can be separated with semi-colons.
</td></tr><tr><td>
Conductors</td><td>
conductor</td><td>
User-defined string. Multiple conductors can be separated with semi-colons.
</td></tr><tr><td>
Content group</td><td>
contentgroup</td><td>
User-defined string.
</td></tr><tr><td>
Encoded by</td><td>
encoder</td><td>
User-defined string.
</td></tr><tr><td>
Encoding software</td><td>
encodingsoftware</td><td>
User-defined string.
</td></tr><tr><td>
Genre</td><td>
genre</td><td>
User-defined string.
</td></tr><tr><td>
Mood</td><td>
mood</td><td>
User-defined string.
</td></tr><tr><td>
Publisher</td><td>
publisher</td><td>
User-defined string.
</td></tr><tr><td>
Subtitle</td><td>
subtitle</td><td>
User-defined string.
</td></tr><tr><td>
Year</td><td>
year</td><td>

Accepts a four digit year (**YYYY**).
</td></tr><tr><td>

**  
Document Properties**</td><td>
</td><td>

</td></tr><tr><td>
Authors</td><td>
author</td><td>
User-defined string. Multiple authors can be separated with semi-colons.
</td></tr><tr><td>
Category</td><td>
category</td><td>
User-defined string.
</td></tr><tr><td>
Company</td><td>
company</td><td>
User-defined string.
</td></tr><tr><td>
Content Status</td><td>
contentstatus</td><td>
User-defined string.
</td></tr><tr><td>
Content Type</td><td>
contenttype</td><td>
User-defined string.
</td></tr><tr><td>
Copyright</td><td>
copyright</td><td>
User-defined string.
</td></tr><tr><td>
Creator</td><td>
creator</td><td>
User-defined string.
</td></tr><tr><td>
Language</td><td>
language</td><td>
User-defined string.
</td></tr><tr><td>
Last saved by</td><td>
lastsavedby</td><td>
User-defined string.
</td></tr><tr><td>
Manager</td><td>
manager</td><td>
User-defined string.
</td></tr><tr><td>
Producer</td><td>
producer</td><td>
User-defined string.
</td></tr><tr><td>
Subject</td><td>
subject</td><td>
User-defined string.
</td></tr><tr><td>
Title</td><td>
title</td><td>
User-defined string.
</td></tr></tbody>
</table>

