# Display

![](/Manual/images/media/folder_options_-_tabs_-_display_1.png)

On the **Display** tab of the Folder Options dialog, the **View** section contains options relating to the view mode of the file display.

- **View as**: you can have the file display automatically switch to thumbnails, or details, for example.  
  \* **Auto-size columns**: This option causes column widths in details and power mode to be automatically sized to fit their contents. Instead of using this option, which affects all columns, you can also configure this on a per-column basis on the **Columns** tab.   
  \* **Hide file extension in Filename column**: This does just what it says - you might want to enable this if you have added the separate *Extension* column (or if you just hate file extensions!)  
  ![](/Manual/images/media/sorting_options_xnewx.png)

Also on the **Display** tab, the **Sorting Options** section contains options that affect the sorting of the file list (other than the actual field or fields the list is sorted by - this is specified on the **Columns** tab).

- **Ignore prefix**: This lets you specify one or more filename prefixes that Opus will ignore when sorting the file list. The screenshot above shows that ***The \|A \|An** *has been given, which means a leading ***The***, ***A*** or ***An*** (all three are followed by a space) at the beginning of a filename will be ignored when sorting. If you specify more than one prefix you must separate them with a vertical bar character as shown above.

- **Mixing**: This option lets you choose how files and folders are to be sorted with respect to each other. You can choose to list all the files before the folders, all the folders before the files, or to have files and folders interspersed.

- **Keep folders sorted alphabetically**: With this option on, folders will always be sorted alphabetically even when the list is sorted by another field. This doesn't apply if you have chosen *Mix files and folders together* for the **Mixing** option.

- **Keep folders at the top when grouped**: When the file list is grouped, folders will always be kept in their own group which will be displayed before all other file groups.  
  \* **Manual sorting**: Lets you enable [manual sorting](../../sorting_and_grouping/manual_sorting.md) in a folder.

- **Numeric order filename sorting**: This option changes the way files and folders that begin or end with a number are sorted by name. When off, digits in names are treated like any other character when sorting. When turned on, digits at the beginning or end of a name are sorted based on their numerical value. 

![](/Manual/images/media/numeric_sorting_off.png)![](/Manual/images/media/numeric_sorting_on.png)

The image on the left shows an example of sort order when numeric order sorting is off; the image on the right is with it on.

- **Reverse sort order**: This option reverses the order of the sort - for example, if the sort is normally from A to Z, it would instead be from Z to A.

- **Sort name and extension separately**: When enabled, Opus sorts folders by name by splitting up the filename stem and the extension, and sorting them separately (i.e. it sorts by the stem first, and only if the stem is the same does it consider the file extension). This has the effect of keeping names with the same stem together, for example:

![](/Manual/images/media/sortnameext-1.png)  ![](/Manual/images/media/sortnameext-2.png)

In  above image, there are only three files with the stem *Test*, and a fourth with the stem *Test.bbb.* In the image on the left, with the option turned on, Opus has sorted two groups separately. In the image on the right, Opus has considered the whole filename including the extension as a single string.

- **Word sort**: This option enables special handling for punctuation characters in filenames. In a word sort, all punctuation marks and other non-alphanumeric characters, except for the hyphen and the apostrophe, come before any alphanumeric character. The hyphen and the apostrophe are treated differently than the other non-alphanumeric symbols, in order to ensure that words such as "coop" and "co-op" stay together within a sorted list.

![](/Manual/images/media/word_sort_off.png)![](/Manual/images/media/word_sort_on.png)

In the image on the left, word sort is turned off; it is turned on in the image on the right.  
\* **When grouped, combine groups with only one member into the “Other” group**: When enabled, and the file display is grouped, any items in a group by themselves will instead be shown in a group called *Other* (prevents cluttering up the folder with lots of groups containing only one file).
