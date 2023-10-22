# Keywords for SetAttr META

The following keywords can be used to modify file metadata [programmatically](/Manual/file_operations/editing_metadata/programmatic_setting_of_metadata.md) with the **[SetAttr](../command_reference/internal_commands/setattr.md) META** command. Most fields can only be set to a string (or number), or cleared, however some fields accept more complex instructions, and these are noted below.

\<commandtable columns="3" id="cmdtable_1"\> \$\$ Field \$\$ Keyword \$\$ Notes\$\$\$\$ **Standard Properties** \$\$ Attributes \$\$ attr \$\$ Attributes are specified with one or more of the following letters:  
**A** (archive)  
**R** (read-only)  
**H** (hidden)  
**S** (system)  
**C** (compressed)  
**E** (encrypted)

You can also use **+** to turn attributes on and **-** to turn attributes off.

//<Example://>

**SetAttr META attr:+c-r***   - sets compression and clears read-only attributes*  
\$\$ Date created \$\$ createdate \$\$ The date and time can be set to an absolute date (in which case the time will be unchanged), an absolute time (in which case the date will be unchanged), or both.  
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
\$\$ Date modified \$\$ lastmodifieddate \$\$ Accepts the same values as **createdate** (described above).  
\$\$\$\$ **  
Extended Properties** \$\$ Comment \$\$ comment  
usercomment \$\$ User-defined string.  
\$\$ Rating \$\$ rating \$\$ Accepts a value from **0** (to clear the rating) through to **5** (5 stars).  
\$\$ Tags \$\$ tags \$\$ Accepts multiple semi-colon separated tags. You can either set the tags absolutely, or add tags to or remove tags from the existing set.

*Example*:

**SetAttr META tags:one;two***   - sets the tags to "one" and "two"*  
**SetAttr META tags:+one***   - adds the tag "one" to any existing tags*  
**SetAttr META tags:+one;-two***   - adds "one" and removes "two"*  
\$\$\$\$ **  
Picture Properties** \$\$ Aperture \$\$ aperture \$\$ Accepts either a decimal or fractional value.  
\$\$ Camera make \$\$ cameramake \$\$ User-defined string.  
\$\$ Camera model \$\$ cameramodel \$\$ User-defined string.  
\$\$ Contrast \$\$ contrast \$\$ Accepts the following values (either the *value* or the *keyword* can be used):

\<WRAP\>

| Value | Keyword |
|-------|---------|
| 0     | normal  |
| 1     | soft    |
| 2     | hard    |

\</WRAP\>\<wrap clear/\>

//<Example://>

**SetAttr META contrast:2**  
\$\$ Creation software \$\$ software \$\$ User-defined string.  
\$\$ Date digitized \$\$ datedigitized \$\$ Accepts the same values as **createdate** (described above in the **Standard Properties** section).  
\$\$ Date taken \$\$ datetaken \$\$ Accepts the same values as **createdate** (described above in the **Standard Properties** section).  
\$\$ Digital Zoom \$\$ digitalzoom \$\$ Accepts a decimal or fractional value, as well as the keyword **off**.  
\$\$ Exposure bias \$\$ exposurebias \$\$ Accepts either a decimal or fractional value.  
\$\$ Exposure program \$\$ exposureprogram \$\$ Accepts the following values (either the *value* or the *keyword* can be used):  
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
\$\$ Exposure time \$\$ exposuretime \$\$ Specified in seconds or fractions of a second - accepts either a decimal or fractional value.  
\$\$ F-number \$\$ fnumber \$\$ Accepts either a decimal or fractional value.  
\$\$ Flash \$\$ flash \$\$ Accepts the following values (either the *value* or the *keyword* can be used):  
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
\$\$ Focal length \$\$ focallength \$\$ Specified in millimetres - accepts either a decimal or fractional value.  
\$\$ Focal length (35mm) \$\$ 35mmfocallength \$\$ Specified in millimetres - accepts either a decimal or fractional value.  
\$\$ GPS Altitude \$\$ gpsaltitude \$\$ Specified as metres relative to sea level - accepts either a decimal or fractional value. Specify a negative number to reference below sea level.

//<Example://>

**SetAttr META gpsaltitude:-423**  
\$\$ GPS Latitude \$\$ gpslatitude \$\$ Accepts coordinates in any of the following formats:  
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
\$\$ GPS Longitude \$\$ gpslongitude \$\$ Accepts coordinates in any of the following formats:  
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
\$\$ Image description \$\$ imagedesc \$\$ User-defined string.  
\$\$ ISO speed \$\$ isospeed \$\$ Accepts a numeric value.  
\$\$ Metering mode \$\$ meteringmode \$\$ Accepts the following values (either the *value* or the *keyword* can be used):  
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
\$\$ Rotation \$\$ orientation \$\$ Accepts the values **0**, **90**, **180** and **270**.  
Also accepts a delta value to adjust the existing orientation value.

//<Example://>

**SetAttr META orientation:90***   - set orientation to 90*  
**SetAttr META orientation:-90***   - rotate orientation 90 degrees counter-clockwise*  
\$\$ Saturation \$\$ saturation \$\$ Accepts the following values (either the *value* or the *keyword* can be used):

\<WRAP\>

  
^Value^Keyword^

|     |        |
|-----|--------|
| 0   | normal |
| 1   | low    |
| 2   | high   |

\</WRAP\>\<wrap clear/\>  
\$\$ Scene capture type \$\$ scenecapturetype \$\$ Accepts the following values (either the *value* or the *keyword* can be used):

\<WRAP\>

  
^Value^Keyword^

|     |            |
|-----|------------|
| 0   | standard   |
| 1   | landscape  |
| 2   | portrait   |
| 3   | nightscene |

\</WRAP\>\<wrap clear/\> \$\$ Sharpness \$\$ sharpness \$\$ Accepts the following values (either the *value* or the *keyword* can be used):

\<WRAP\>

  
^Value^Keyword^

|     |        |
|-----|--------|
| 0   | normal |
| 1   | soft   |
| 2   | hard   |

\</WRAP\>\<wrap clear/\>  
\$\$ Shutter speed \$\$ shutterspeed \$\$ Specified in seconds or fractions of a second - accepts either a decimal or fractional value.  
\$\$ Special instructions \$\$ instructions \$\$ User-defined string.  
\$\$ Subject distance \$\$ subjectdistance \$\$ Specified in either metres or millimetres - accepts either a decimal or fractional value.

//<Example://>

**SetAttr META subjectdistance:10.3mm** *   - 10.3 millimetres*  
**SetAttr META subjectdistance:50m** *   - 50 metres*  
\$\$ White balance \$\$ whitebalance \$\$ Accepts the following values (either the *value* or the *keyword* can be used):

\<WRAP\>

  
^Value^Keyword^

|     |        |
|-----|--------|
| 0   | auto   |
| 1   | manual |

\</WRAP\>\<wrap clear/\>  
\$\$\$\$ **  
Music Properties** \$\$ Album \$\$ album \$\$ User-defined string.  
\$\$ Album artist \$\$ albumartist \$\$ User-defined string.  
\$\$ Compilation \$\$ compilation \$\$ iTunes Compilation tag. Can be **True** (**1**) or **False** (**0**). \$\$ Cover art \$\$ coverart \$\$ This can set, add and remove cover art.

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
\$\$ Disc number \$\$ discnumber \$\$ Accepts either a single digit (the number of the disc), or two digits separated by a forward slash (the number of the disc and the total number of discs in the set).

//<Example://>

**SetAttr META discnumber:3/8**  
\$\$ Initial key \$\$ initialkey \$\$ User-defined string.  
\$\$ Original artists \$\$ origartist \$\$ User-defined string.  
\$\$ Release date \$\$ releasedate \$\$ Accepts **YYYYMMDD** or **YYYY-MM-DD** format for the date.

//<Example://>

**SetAttr META releasedate:1973-03-01**  
\$\$ Track number \$\$ track \$\$ Accepts either a single digit (the number of the track), or two digits separated by a forward slash (the number of the track and the total number of tracks on the disk). Append a + to the value to activate auto-increment mode.

//<Example://>

**SetAttr META track:5/14**  
\$\$\$\$ **  
Video Properties** \$\$ Directors \$\$ directors \$\$ User-defined string. Multiple directors can be separated with semi-colons.  
\$\$ Producers \$\$ producers \$\$ User-defined string. Multiple producers can be separated with semi-colons.  
\$\$ Writers \$\$ writers \$\$ User-defined string. Multiple writers can be separated with semi-colons.  
\$\$\$\$ **  
Music and Video Properties** \$\$ Author URL \$\$ authorurl \$\$ User-defined string.  
\$\$ Artists \$\$ artist \$\$ User-defined string. Multiple artists can be separated with semi-colons.  
\$\$ BPM \$\$ bpm \$\$ Accepts a numeric value.  
\$\$ Composers \$\$ composers \$\$ User-defined string. Multiple composers can be separated with semi-colons.  
\$\$ Conductors \$\$ conductor \$\$ User-defined string. Multiple conductors can be separated with semi-colons.  
\$\$ Content group \$\$ contentgroup \$\$ User-defined string.  
\$\$ Encoded by \$\$ encoder \$\$ User-defined string.  
\$\$ Encoding software \$\$ encodingsoftware \$\$ User-defined string.  
\$\$ Genre \$\$ genre \$\$ User-defined string.  
\$\$ Mood \$\$ mood \$\$ User-defined string.  
\$\$ Publisher \$\$ publisher \$\$ User-defined string.  
\$\$ Subtitle \$\$ subtitle \$\$ User-defined string.  
\$\$ Year \$\$ year \$\$ Accepts a four digit year (**YYYY**).  
\$\$\$\$ **  
Document Properties** \$\$ Authors \$\$ author \$\$ User-defined string. Multiple authors can be separated with semi-colons.  
\$\$ Category \$\$ category \$\$ User-defined string.  
\$\$ Company \$\$ company \$\$ User-defined string.  
\$\$ Content Status \$\$ contentstatus \$\$ User-defined string.  
\$\$ Content Type \$\$ contenttype \$\$ User-defined string.  
\$\$ Copyright \$\$ copyright \$\$ User-defined string.  
\$\$ Creator \$\$ creator \$\$ User-defined string.  
\$\$ Language \$\$ language \$\$ User-defined string.  
\$\$ Last saved by \$\$ lastsavedby \$\$ User-defined string.  
\$\$ Manager \$\$ manager \$\$ User-defined string.  
\$\$ Producer \$\$ producer \$\$ User-defined string.  
\$\$ Subject \$\$ subject \$\$ User-defined string.  
\$\$ Title \$\$ title \$\$ User-defined string.

\</commandtable\>
