# Keywords for Columns

The following keywords are used by the **[Set](../command_reference/internal_commands/set.md)** command (with the **COLUMNS**, **COLUMNSADD**, **COLUMNSREMOVE** and **COLUMNSTOGGLE** arguments) to change which columns are displayed in the file display (in details and power modes), and with the **GROUPBY** and **SORTBY** arguments to modify the group and sort fields. For example, **Set COLUMNSADD=desc** adds the Description column to the file display.

They are also used by the [Rename](/Manual/file_operations/renaming_files/RAEDME.md) function when [renaming using metadata](/Manual/file_operations/renaming_files/advanced_rename/renaming_with_metadata.md), and in the [File Types](/Manual/file_types/filetype_editor/RAEDME.md) editor when defining your own [tile](/Manual/file_types/filetype_editor/tiles_mode.md) and [infotip](/Manual/file_types/filetype_editor/info_tip.md) definitions.

Note that some columns appear in multiple categories. For historic reasons, column keywords sometimes only reflect a narrow usage when the column actually works in a wider range of situations. For example, the *Duration* column (**mp3songlength**) works with various music file types, and some movie types, not just MP3 music files.

Where columns are used to output text (for example, when generating filenames for a rename, or when displaying info tips), the format of dates, times and numeric values can be overridden.

##### Date and time fields

Date and time fields let you configure the date format, the time format, or both. For example,

|                                   |                                                                              |
|-----------------------------------|------------------------------------------------------------------------------|
| **{datetaken\|D#yyyy-MM-dd}**     | inserts the date only in **yyyy-MM-dd** format (e.g. *2023-09-22*)           |
| **{modified\|T#HH-mm-ss}**        | inserts the modified time in **HH-mm-ss** format (e.g. *13:10:55*)           |
| **{datetaken\|A#yyyyMMddHHmmss}** | inserts both the date and time as **yyyyMMddHHmmss** (e.g. *20221130154410*) |

As you can see in the examples, **D#** is used to mark the date format, **T#** is used to mark the time format, and **A#** indicates both date and time codes are present. See the [Codes for date and time](../command_reference/external_control_codes/codes_for_date_and_time.md) page for information on date and time formats.

##### Numeric fields

Numeric fields let you control zero-padding. For example,

|                    |                                                               |
|--------------------|---------------------------------------------------------------|
| **{size\|#8}**     | zero-pads the size in bytes to eight places (e.g. *00045412*) |
| **{mp3track\|#2}** | zero-pads the track number to two places (e.g. *08*)          |

The filename can be retrieved without the file extension using **{name\|noext}**.

------------------------------------------------------------------------

#### Column keywords

##### Date and Time

| Column | Keyword |
| --- | --- |
| Create (relative) | cdaterel |
| Date (accessed) | accesseddate |
| Date (created) | createddate |
| Date (modified) | modifieddate |
| Date and Time (accessed) | accessed |
| Date and Time (created) | created |
| Date and Time (modified) | modified |
| Modify (relative) | daterel |
| Time (accessed) | accessedtime |
| Time (created) | createdtime |
| Time (modified) | modifiedtime |

##### Documents

| Column | Keyword |
| --- | --- |
| Authors | author |
| Category | category |
| Comment | comments |
| Company | companyname |
| Copyright | copyright |
| Creator | creator |
| Document created date | doccreateddate |
| Last edit time | docedittime |
| Last saved by | doclastsavedby |
| Last saved date | doclastsaveddate |
| Pages | pages |
| Producer | producer |
| Subject | subject |
| Title | title |

##### Name and Path

| Column | Keyword |
| --- | --- |
| Extension | ext |
| Extension (dirs) | extdir |
| Filename | name |
| Full path | fullpath |
| Location | path |
| Location (relative) | pathrel |
| Parent folder | parent |
| Parent folder (full) | parentlocation |
| Parent location | parentpath |
| Path length | pathlen |
| Short name | shortname |

##### Picture Dimensions

| Column | Keyword |
| --- | --- |
| Aspect ratio | aspectratio |
| Bit depth | picdepth |
| Dimensions | picsize  <br />dimensions |
| Height | picheight |
| Physical height | picphysy |
| Physical size | picphyssize |
| Physical width | picphysx |
| Resolution (X) | picresx |
| Resolution (Y) | picresy |
| Rotation | rotation |
| Width | picwidth |

##### Picture Metadata

| Column | Keyword |
| --- | --- |
| Altitude | altitude |
| Aperture | apertureval |
| Artists | mp3artist |
| Camera make | cameramake |
| Camera model | cameramodel |
| Color model | colormodel |
| Contrast | contrast |
| Coordinates | coords |
| Copyright | copyright |
| Creation software | software |
| Date digitized | datedigitized |
| Date taken | datetaken  <br />shootingtime |
| Digital Zoom | digitalzoom |
| Exposure bias | exposurebias |
| Exposure program | exposureprogram |
| Exposure time | exposuretime |
| F-number | fnumber |
| Flash | flash |
| Focal length | focallength |
| Focal length (35mm) | 35mmfocallength |
| ISO speed | isorating |
| Image description | imagedesc |
| Image quality | imagequality |
| Latitude | latitude |
| Lens make | lensmake |
| Lens model | lensmodel |
| Longitude | longitude |
| Macro mode | macromode |
| Metering mode | meteringmode |
| Saturation | saturation |
| Scene capture type | scenecapturetype |
| Scene mode | scenemode |
| Sharpness | sharpness |
| Shutter speed | shutterspeed |
| Subject | subject |
| Subject distance | subjectdistance |
| Special instructions | instructions |
| Title | title |
| White balance | whitebalance |

##### Programs

\<commandtable columns="2"\> \$\$ Column \$\$ Keyword \$\$ Copyright \$\$ copyright \$\$ Company \$\$ companyname \$\$ Module Description \$\$ moddesc \$\$ Module Version \$\$ modversion \$\$ Product Name \$\$ prodname \$\$ Product Version \$\$ prodversion \</commandtable\>

##### File Size

| Column | Keyword |
| --- | --- |
| Size (KB) | sizekb |
| Size (auto) | sizeauto |
| Size (bytes) | size |
| Size (relative) | sizerel |
| Size on disk (KB) | disksizekb |
| Size on disk (auto) | disksizeauto |
| Size on disk (bytes) | disksize |
| Size on disk (relative) | disksizerel |
| Uncompressed Size | uncompressedsize |

##### General

| Column | Keyword |
| --- | --- |
| Attributes | attr |
| Availability | availability |
| Description | desc |
| File count | filecount |
| Font name | fontname |
| Group | group |
| Index | index |
| Label | label |
| MD5 checksum | md5sum |
| Owner | owner |
| Rating | rating |
| SHA-1 checksum | shasum |
| Status Icons | status |
| Sub-folder count | dircount |
| Tags | keywords |
| Target | target |
| Thumbnail | thumbnail |
| Total File count | filecounttotal |
| Total Sub-folder count | dircounttotal |
| Type | type |
| User description | userdesc |

##### Movies

| Column | Keyword |
| --- | --- |
| Aspect ratio | aspectratio |
| Audio codec | audiocodec  <br />mp3type |
| Bit depth | picdepth |
| Bit rate | mp3bitrate |
| Broadcast date | broadcastdate |
| Channel number | channel |
| Credits | credits |
| Data rate | datarate |
| Dimensions | picsize  <br />dimensions |
| Duration | duration  <br />mp3songlength |
| Episode name | episodename |
| FOURCC code | fourcc |
| Frame rate | framerate |
| Height | picheight |
| High definition? | ishd |
| Mode | mp3mode |
| Physical size | picphyssize |
| Publisher | publisher |
| Recording time | recordingtime |
| Repeat? | isrepeat |
| Sample rate | mp3samplerate |
| Station name | station |
| Video codec | videocodec |
| Width | picwidth |

##### Music

| Column | Keyword |
| --- | --- |
| Album | mp3album |
| Album artist | mp3albumartist |
| Artists | mp3artist |
| Audio codec | audiocodec  <br />mp3type |
| BPM | mp3bpm |
| Bit depth | picdepth |
| Bit rate | mp3bitrate |
| Compilation | compilation |
| Composers | composers |
| Conductors | conductors |
| Copyright | copyright |
| Disc number | mp3disc  <br />mp3disk |
| Duration | mp3songlength |
| Encoded by | mp3encoder |
| Encoding Software | mp3encodingsoftware |
| Genre | mp3genre |
| Initial key | initialkey |
| Mode | mp3mode |
| Music comment | mp3comment |
| Music info | mp3info |
| Music title | mp3title |
| Protected | mp3drm |
| Release date | releasedate |
| Sample rate | mp3samplerate |
| Track number | mp3track |
| Year | mp3year |

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

| Column | Keyword |
| --- | --- |
| \$ **FTP keywords** | Transfer time |
| <ftp:xfertime> | Group |
| <ftp:group> | \$ **Computer keywords** |
| Free space on drive | sh:freespace |
| File system | sh:filesys |
| Used space (graph) | sh:usedpercent |
| Free space (graph) | sh:freepercent |
| Network location | sh:netlocation |
| Used space on drive | sh:usedspace |
| \$ **Zip keywords** | Compressed size |
| zip:compsize | Compression ratio |
| zip:compratio | Compression method |
| zip:compmethod | CRC checksum |
| zip:compcrc | \$ **7-Zip keywords** |
| Packed size | opus7zip:packed |
| Ratio | opus7zip:ratio |
| CRC | opus7zip:crc |
| Block | opus7zip:block |
| Index | opus7zip:index |
| Is solid? | opus7zip:solid |
| Method | opus7zip:method |
| Mode | opus7zip:mode |
| Link | opus7zip:link |
| User | opus7zip:user |
| Group | opus7zip:group |

