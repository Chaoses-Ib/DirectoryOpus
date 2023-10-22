# Filter Clause Types

Each clause has a type which specifies exactly which attribute of a candidate file that clause will match. The clause type is chosen from a drop-down list. A sub-clause is created by selecting *Subclause* from the same drop-down list, but sub-clauses are described on the [Defining a Filter](defining_a_filter.md) page rather than here.

![](/Manual/images/media/filter_-_types.png) 

  
There are a number of clause types that apply to all types of file and folder:

- **Attributes**: Lets you match based on the file's attributes.

![](/Manual/images/media/filter_-_attributes.png)

The **On** attributes are those that must be on for the clause to match; the **Off** attributes must be off for the clause to match. In the example above, the clause would match only if the file's **R** attribute were set, and **E** and **C** attributes were not set. The attributes you can choose from are **R**ead-only, **A**rchive, **H**idden, **S**ystem, **E**ncrypted, **C**ompressed, non-content **I**ndexed, **O**ffline, **P**inned.

  
\* **Availability:** Lets you match based on a file's offline status (for cloud storage).

- **Contains**: Searches files for the supplied text string.

![](/Manual/images/media/filter_-_contains.png)

If a **Contains** clause is used then the contents of files will be searched to see if they contain the specified string. Because searching files can be a time-consuming operation, **Contains** clauses are "deferred" and processed as the very last step before a file matches a filter. The options that affect the search are:                                             

      * **Use wildcards**: Lets you specify a search pattern using [[:reference:wildcard_reference:pattern_matching_syntax|standard pattern matching]]. 
      * **Use regular expression**: Lets you specify the search pattern using [[..:..:renaming_files:advanced_rename:rename_modes:regular_expressions|regular expressions]]. 
      * **Assume UTF-8 with no BOM**: Tells Opus to assume that text-files without a Byte Order Mark (BOM) are encoded in UTF8 rather than your computer's default 8-bit character set. 
      * **Whole words**: If this is turned on, only whole words that match the search string will match. For example, searching for "quint" would not match "quintuplet". 
      * **Case sensitive**: Makes the search case-sensitive (upper and lower-case letters will not be treated as the same).

  
\* **Date**: Compares the file's timestamp, but only looks at date and not the time.

![](/Manual/images/media/filter_-_date.png)

The parameters that affect a **Date** comparison are:                                             

      * Which timestamp: Select from //Modified// (last modified date), //Created// (creation date) and //Accessed// (last access date). 
      * Comparison type: Select from //After//, //Before//, //Between// and //Within//. 
      * Comparison date: Enter the actual date to compare against. For //After// and //Before// this is a single date. For //Between// this is two dates (making a range the date must fall within), and for //Within// this is a relative date from the current day in days, months, weeks or years.

  
\* **Date/Time**: Compares the file's timestamp, comparing both date and time.

![](/Manual/images/media/filter_-_datetime.png)

This is similar to a **Date** except that both the time and date portions of the timestamp are compared - you specify both a date and time to compare against. *Within* is not an available comparison type for **Date/Time** clauses.

  
\* **Description**: Compares the file's description (if it has one assigned to it). The search options are the same as for a **Contains** clause.

  
\* **Label**: Matches a file on the basis of its assigned [label](../../labels.md) (if it has one).

![](/Manual/images/media/filter_-_label.png)

The drop-down control displays a list of the [configured labels](/Manual/basic_concepts/folder_options/folder_options_dialog/labels.md) for you to choose from, or you can type in a wildcard pattern.

  
\* **Name**: Compares the file's name against the specified string.

![](/Manual/images/media/filter_-_name.png)

The options for a **Name** clause are:                                             

      * **Use wildcards**: Lets you specify a search pattern using [[:reference:wildcard_reference:pattern_matching_syntax|standard pattern matching]]. 
      * **Use regular expression**: Lets you specify the search pattern using [[..:..:renaming_files:advanced_rename:rename_modes:regular_expressions|regular expressions]]. 
      * **Case sensitive**: Makes the search case-sensitive (upper and lower-case letters will not be treated as the same).

  
\* **Owner**: Match against the file's owner. [Standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) are enabled for this search; if you don't specify any wildcards then the search will automatically perform a partial match (so "Fred" will match "Frederick" automatically).

  
\* **Path length**: Lets you search for files or folders based on the total path length (that is, the number of characters in the full file path, including its name). This is useful for identifying files whose paths exceed the normal Windows 260 character path length limit.

  
\* **Rating**: Match the rating assigned to the file or folder (if any). You can rate your files using the **[Metadata Pane](/Manual/basic_concepts/the_lister/metadata_pane.md)**.

  
\* **Script column**: Test the file or folder against a [column generated by a script add-in](/Manual/scripting/example_scripts/adding_a_new_column.md).

Details depend on the type of column the script adds, but will generally be similar to one of the other clause types.

Filtering using script columns allows you to expand the capabilities of Opus's filtering in arbitrary ways, based on anything you can express as a script. Some script add-ins provide columns intended more for filtering than display, although there is no technical difference between the two. A common use for this is to filter folders based on the files they contain, by writing a script column which looks inside each folder and populates a column with "Yes" and "No" values (or similar) to signal whether it should match or not.

  
\* **Shell column**: Match the value of any column added by third-party shell extension handlers.

![](/Manual/images/media/shellcol.png)

The drop-down gives you a list of available columns, and you can use [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md)to match against the value of the selected column. For numeric columns, limited numeric comparison is available using the operators **!=** (not equals), **==** (equals), **\<** (less than), **\>** (greater than), **\<=** (less than or equal), **\>=** (greater than or equal), **&&** (and) and **\|\|** (or).  
  
  

- **Size**: Compare the file's size.  
    
  ![](/Manual/images/media/filter_-_size.png)  
    
  The parameters that affect a **Size** comparison are:                                             
  - Comparison type: Select from *equal to*, *greater or equal to*, *greater than*, *less than or equal to* and *less than*.
  - Comparison size: Enter the actual size value to compare against.
  - Comparison units: Specify the units that the comparison size is specified in. Select from *bytes*, *KB* (kilobytes), *MB* (megabytes) and *GB* (gigabytes). The search engine automatically rounds file sizes when comparing against units other than bytes; for example, a 1158-byte file would match a clause that specified **equal to 1 KB**.

  
A **Size** clause can also be used to compare the size of folders. Because calculating a folder's size can be time consuming, you must specifically enable this behaviour by also including a **Type** clause that specifies *Folders*. For example, the following two clauses would match all empty folders:  
  
![](/Manual/images/media/filter_-_empty_dirs.png)  
  
  

- **Target:** If a file is a junction, shortcut or link, the **Target** clause lets you match on what it points to (the path of the target of the shortcut).  
    
  **![](/Manual/images/media/filter_-_target.png)\\** The above example would match shortcuts that pointed to any .exe (application files) below the *C:\Program Files* folder. You can choose from the following options:
  - **Use wildcards**: Lets you specify a search pattern using [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md).
  - **Use regular expression**: Lets you specify the search pattern using [regular expressions](../../renaming_files/advanced_rename/rename_modes/regular_expressions.md).
  - **Case sensitive**: Makes the search case-sensitive (upper and lower-case letters will not be treated as the same).
  - **File**: Only match shortcuts that point to files.
  - **Folder**: Only match shortcuts that point to folders.  
      
      
- **Tags**: Compares against any tags assigned to the file. [Standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) are enabled for this search; if you don't specify any wildcards then the search will automatically perform a partial match (so "account" will match "accounting" automatically). The string you enter is compared against all tags assigned to the file separately, so if you want to match two specific tags, you need to use two separate **Tags** clauses.  
    
    
- **Time**: Similar to a **Date** clause, this compares the file's timestamp, but only looks at the time portion and not the date.  
    
  ![](/Manual/images/media/filter_-_time.png)  
    
  The parameters that affect a **Time** comparison are:                                    
  - Which timestamp: Select from *Modified* (last modified date), *Created* (creation date) and *Accessed* (last access date).
  - Comparison type: Select from *After*, *Before*, *Between* and *Within*.
  - Comparison time: Enter the actual time to compare against. For *After* and *Before* this is a single time. For *Between* this is two times (making a range the time must fall within), and for *Within* this is a relative time from the current time within hours, minutes or seconds. The time for a *Within* comparison is relative to *now* - that is, if the current time when the filter is used is 15:35 and the clause specified **within 1 hour**, anything dated the current date between 14:35 and 15:35 would match, but a file from yesterday at 15:10 would not.  
      
      
- **Type**: This lets you match a file by file type.  
    
  ![](/Manual/images/media/filter_-_type_x1x.png)  
    
  The drop-down list lets you pick from a list of all registered file types. So instead of using a **Name Match \*.bmp** clause, you can specify **Type Match Bitmap Image**. The **Type** clause also supports the following special types:      
  - **Files only**: Matches all files, but not folders
  - **Folders only**: Matches all folders, but not files.
  - **Junctions/Links/Shortcuts**: Matches shortcuts, folder junctions and hard or soft links. You can use this in conjunction with the **Target** clause to search for, for example, shortcuts pointing to a specific folder or file.

The following clauses only apply to certain types of file:

- **Document**: Lets you filter on various document fields, applicable to files like Office or PDF documents.  
    
  ![](/Manual/images/media/filter_-_document.png)  
    
  Use the drop-down (in the above screenshot, **Document Created** is selected) to select from the various document fields to compare against:    
  - **Any field**: Searches for the specified string in any of the text-based document fields.
  - **Author**: The document's author.
  - **Category**: The document's category (if it has been assigned one).
  - **Comment**: Any comment stored in the document.
  - **Company**: The company field from the document.
  - **Copyright**: The copyright field.
  - **Document Created**: The date the document was created on. You can specify a date and select a *before*, *after* or *on* comparison.
  - **Last Edit Time**: The date the document was last edited.
  - **Last Saved By**: The person who last saved the document.
  - **Last Saved Date**: The date the document was last saved.
  - **Pages**: The number of pages in the document. You can specify the number of pages and select a *greater than*, *less than* or *equals* comparison.
  - **Subject**: The document's subject.
  - **Title**: The document's title.

  
The document fields that take a string parameter to compare against (which are most of them) support [standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) for the search.  
  
  

- **Image**: Lets you filter on various image-related fields. All recognized image formats are supported.  
    
  ![](/Manual/images/media/filter_-_image.png)  
    
  Use the drop-down (in the above screenshot, **Date taken** is selected) to select from the various fields you can compare on:    
  - **Camera make**: The make (manufacturer) of the camera that took the image.
  - **Camera model**: The model of the camera that took the image.
  - **Color space**: The color space of the image (*grayscale*, *RGB*, *CMYK*, *YCCK* or *YUV*).
  - **Contrast**: The contrast setting when the image was recorded (*hard*, *normal* or *soft*).
  - **Copyright**: The copyright information from the image (if any).
  - **Creation software**: The software that was used to create the image.
  - **Date digitized**: The date the image was digitized. This is sometimes the same as **Date taken** but might be different if the image was originally taken as a non-digital image.
  - **Date taken**: The date the image was recorded (a.k.a. shooting time). You can specify a date and select *on*, *after* or *before* as a comparison.
  - **Digital zoom**: The digital zoom ratio used to record the image (if any). You can specify a multiplier and select *equal to*, *greater than* or *less than* as a comparison.
  - **Dimensions**: The image dimensions. This lets you pick from a drop-down of several common image sizes. If you want more control you can use the **Width** and **Height** fields.
  - **Exposure bias**: The camera's exposure bias setting when the image was recorded, specified in *stops*.
  - **Exposure program**: The exposure program used to record the image (aperture priority, shutter priority, action, landscape, etc.)
  - **Exposure time**: The exposure time used to record the image, specified in seconds or fractions of a second. You can enter the time as a whole number, a fraction (e.g. **1/5**) or a decimal (e.g. **1.8**).
  - **F-number**: The f-number (aperture setting) used to record the image, specified in *stops*.
  - **Flash**: Whether the flash fired or not when the image was taken, and if so what mode was used.
  - **Focal length**: The focal length of the lens when the image was recorded, specified in mm. This is the absolute focal length of the lens.
  - **Focal length (35mm)**: The focal length of the lens as a 35mm equivalent value (e.g. a digital camera with a lens focal length of 6mm may be equivalent to a 28mm focal length lens on a 35mm film camera).
  - **Height**: The height of the image, in pixels. You can select *equal to*, *greater than* or *less than* as a comparison.
  - **ISO speed**: The (equivalent) film speed when the image was taken, expressed using the ISO scale.
  - **Metering mode**: The exposure metering mode used when the image was taken (average, spot, multi-spot, etc).
  - **Resolution (X)**: The horizontal (X) resolution of the image, expressed in dots per inch (dpi).
  - **Resolution (Y)**: The vertical (Y) resolution of the image in dpi.
  - **Rotation**: The rotation information stored in the image, usually from the camera's orientation sensor. This reflects the orientation of the camera when the image was recorded. Select from 0, 90, 180 and 270 degrees.
  - **Saturation**: The saturation of the image (*normal*, *high* or *low*).
  - **Scene capture type**: The type of scene capture program used by the camera (standard, night, portrait, etc).
  - **Sharpness**: The sharpness of the image (*normal*, *hard* or *soft*).
  - **Shutter speed**: The speed of the shutter when the image was taken, expressed in seconds or fractions of a second. You can enter the time as a whole number, a fraction (e.g. **1/5**) or a decimal (e.g. **1.8**). 
  - **Subject distance**: The distance from the focal point to the subject, expressed in metres or fractions of a metre. You can enter the distance as a whole number, a fraction or a decimal. For example, **0.2** would correspond to 20 centimeters.
  - **White balance**: The cameras white balance setting.
  - **Width**: The width of the image, in pixels. You can select *equal to*, *greater than* or *less than* as a comparison.

  
The image fields that take a string parameter to compare against (for example, **Camera make** or **model**) support [standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) for the search.  
  
  

- **Music**: Lets you filter on various music-related fields. All recognized music formats are supported.  
    
  ![](/Manual/images/media/filter_-_music.png)  
    
  Use the drop-down to select from the various fields you can compare on:                   
  - **Album**: The title of the album.
  - **Any field**: Compares the specified text against all text-based music fields.
  - **Artists**: The artist or artists of the album (or track).
  - **Bit rate**: The bit rate the music is digitized at, specified in bits-per-second (bps).
  - **BPM**: The beats-per-minute setting of the track (if any).
  - **Codec**: The codec used to encode the music file.
  - **Comment**: Any comment assigned to the music file.
  - **Disc number**: The number of the disc (for multi-disc sets).
  - **Encoded by**: This field is either used for the name of the person who encoded the track, or the name of the software application they used to do it.
  - **Genre**: The genre of the music.
  - **Protected**: Whether the music is DRM-protected or not (*yes* or *no*).
  - **Release date**: The date the music (normally the actual recording) was released.
  - **Sample rate**: The sample rate the music is digitized at, specified in hertz (Hz).
  - **Song length**: The duration of the music, specified as *hours:minutes:seconds*.
  - **Title**: The title of the track.
  - **Track number**: The track number within an album (if any).

  
The music fields that take a string parameter to compare against (for example, **Album** or **Genre**) support [standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) for the search.

There are three clause types that relate to the location of a file or folder rather than the file or folder itself:  

- **Subfolder**: This is a special type of sub-clause that controls which folders a recursive operation will descend into. When Opus encounters a sub-folder that it would normally enter as part of an operation (for example, when copying a folder containing multiply-nested sub-folders), it tests each sub-folder against the **Subfolder** clause. If it fails, the operation skips that sub-folder and all its contents completely.  
    
  ![](/Manual/images/media/filter_-_subclause.png)  
  In the above example, a **Copy File** operation using that filter would skip over any directories called **.svn** (and all of their contents) no matter where in the folder tree they were encountered. **Subfolder** clauses have no effect on files matched by the filter; they only control which sub-folders are entered.  
    
  *Note: Subfolder clauses do not work with the [Synchronize](../copying_updated_files/synchronize.md) tool.\\*  
    
- **Full path**: This lets you match a file or folder on its full pathname (which includes its own filename). For example,  
    
  ![](/Manual/images/media/filter_-_full_path.png)  
  would match any file ending in **.jpg** that was located in any sub-folder of the *C:\Data\Pictures* directory. Wildcards in Full path clauses are applied to the string as a whole, rather than on individual path components. So the above example, as well as matching **C:\Data\Pictures\Snapshots\IMG1003.JPG** would also match **C:\Data\Pictures\Weddings\Emily\IMG2138.JPG**. When treated as normal strings (instead of paths) they both match the wildcard pattern provided.  
    
    
- **Location**: This is similar to **Full Path** except it only considers the location (path) of the file, but not the filename. This can be particularly useful when searching [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md), as it lets you filter for files based on their real location on disk.

The **Subfolder**, **Full Path** and **Location** clauses all let you choose from standard wildcards or regular expressions.

Only the **Subfolder** clause stops Opus from recursing into directories. If a **Subfolder** clause does not match a folder then Opus will skip that folder and all of its children, even if some of the children may have matched the filter. On the other hand, with the **Full path** and **Location** clauses, Opus will still examine a folder's children even if the folder itself does not match the filter. Both of these methods can be useful, depending on what you actually want to do. If your aim is to ignore everything below a certain folder then a **Subfolder** clause is usually best because it avoids inspecting the folder's children unnecessarily. For some examples, see the Opus Forum/FAQ post, [How to filter items by location or sub-folder](https://resource.dopus.com/t/how-to-filter-items-by-location-or-sub-folder/7644).

The final clause type is **Filter**. This lets you refer to another pre-configured filter (one listed on the [Filters](/Manual/preferences/preferences_categories/file_operations/filters.md) page in Preferences). For example, you could have a standard filter that excludes certain types of files that you never want to process it, and then refer to that in other, more specific filters that you create later on. Referencing another filter saves you from having to duplicate all those filters' parameters, and also any changes you make later to the referenced filter will automatically have effect on any filters that use it.  

![](/Manual/images/media/filter_-_filter.png) 

  
In this example we use the pre-configured **jpegs** filter to first match **.jpg** files, and then use an **Image Dimensions** clause to only match jpegs that are 1280x1024 or larger.
