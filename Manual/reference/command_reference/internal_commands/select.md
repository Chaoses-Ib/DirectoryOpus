# Select

The **Select** internal command is used to:

- Display the *Select* dialog (in either [simple](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.md) or [advanced](/Manual/basic_concepts/selecting_files/advanced_selection.md) modes)
- Select all, deselect all, and invert the current selection of all files and folders
- Select or deselect files by filename with a wildcard pattern
- Select all files in the source that are selected in the destination, and vice versa
- Select all files with extensions matching those already selected
- Convert [checkmarks](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) into selection and vice versa
- Hide files based on whether they are selected or not
- Select a range of files by index
- Select files by date and size

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>

*(no arguments)*</td><td>
-</td><td>
-</td><td>

Displays the *Select* dialog (in either [simple](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.md) or [advanced](/Manual/basic_concepts/selecting_files/advanced_selection.md) modes, depending on which was last used).

*Example:* `Select`
</td></tr><tr><td>
ADVANCED</td><td>
/O</td><td>

*(no value)*</td><td>

Displays the *Select* dialog in [advanced](/Manual/basic_concepts/selecting_files/advanced_selection.md) mode.

*Example:* `Select ADVANCED`
</td></tr><tr><td>
</td><td>
</td><td>

*\<filter name\>*</td><td>

Displays the *Select* dialog in advanced mode, with the specified saved filter already loaded.

*Example:* `Select ADVANCED=MyFilter`
</td></tr><tr><td>
ALL</td><td>
/S</td><td>

*(no value)*</td><td>

Select all files and folders in the current source file display.

*Example:* `Select ALL`
</td></tr><tr><td>
ALLDIRS</td><td>
/S</td><td>

*(no value)*</td><td>

Select all folders in the current source file display.

*Example:* `Select ALLDIRS`
</td></tr><tr><td>
ALLFILES</td><td>
/S</td><td>

*(no value)*</td><td>

Select all files in the current source file display.

*Example:* `Select ALLFILES`
</td></tr><tr><td>
DATE</td><td>
/K</td><td>

*\<date\>*</td><td>

Select files whose last modification timestamps match the specified date. You can specify:

- Just a date, in the format *YYYY-MM-DD*
- Just a time, in the format *HH:MM* (seconds are ignored)
- Both a date and time, in the format *YYYY-MM-DD HH:MM* Note that specifying both a date and time requires quotes around the value, because of the space character separating the two.

You can also use **\>** (greater than) before the date to match all files newer than the specified date, or **\<** (less than) before the date to match all files older than the specified date.

You can also specify an *age* rather than a *date* to test for. For example, to select all files older than 5 days, you might specify `Select DATE ">5 days"`. Valid keywords for age selection are **day**, **week**, **month**, **year**, **hour**, **minute**, **second**.

*Example:* `Select \*.jpg DATE "\>2012-06-15 10:00"`
</td></tr><tr><td>
</td><td>
</td><td>

*\<date1\>***..***\<date2\>*</td><td>

Select files whose last modification timestamps falls between the two specified dates. Both dates are supplied in the format described above.

*Example:* `Select DATE 2012-01-01..2012-12-31 TYPE=files`
</td></tr><tr><td>
</td><td>
</td><td>

**oldest**</td><td>

Select the oldest item in the current source file display. You can combine this with the **PATTERN** argument to select the oldest of a specific type of file.

*Example:* `Select \*.doc DATE=oldest`
</td></tr><tr><td>
</td><td>
</td><td>

**newest**</td><td>

Select the newest item in the current file display.

*Example:* `Select DATE=newest DESELECTNOMATCH`
</td></tr><tr><td>
</td><td>
</td><td>

**created**</td><td>

Normally this command considers the last modification timestamp of each file, however by specifying this keyword you can make it look at the creation time instead.

*Example:* `Select \*.(zip\|7z\|rar) DATE=created,2010-03-10..2010-03-17`
</td></tr><tr><td>
</td><td>
</td><td>

**both**</td><td>

Considers both created and last modification timestamps.

*Example:* `Select DATE=both,newest`
</td></tr><tr><td>
</td><td>
</td><td>

**next**</td><td>

Modifies the behavior of the **newest** and **oldest** arguments. Normally, `Select DATE=newest` would select the newest file in the list. If it were already selected, nothing would change. If you add the **next** keyword, Opus will progressively select the next newest file each time the command is run.

*Example:* `Select DATE=next,newest`
</td></tr><tr><td>
DESELECT</td><td>
/S</td><td>

*(no value)*</td><td>

Instead of selecting files, the command will deselect them. This is used in conjunction with the **PATTERN**, **ALLDIRS** and **ALLFILES** arguments.

*Example:* `Select \*.jpg DESELECT`
</td></tr><tr><td>
DESELECTNOMATCH</td><td>
/S</td><td>

*(no value)*</td><td>

Files that don't match the pattern will be deselected (normally files that don't match are left alone). This also works when using the **FILTER** argument to select files with a predefined filter.

*Example:* `Select \*.doc DESELECTNOMATCH`
</td></tr><tr><td>
DESELECTOTHERTYPE</td><td>
/S</td><td>

*(no value)*</td><td>

When used with the **TYPE** argument to restrict a selection to either files or folders (or with the **ALLFILES** and **ALLDIRS** arguments), **DESELECTOTHERTYPE** causes all items of the other type to be deselected

*Example:* `Select \* TYPE=files DESELECTOTHERTYPE`
</td></tr><tr><td>
DESTTOSOURCE</td><td>
/O</td><td>

*(no value)*</td><td>

Selects all files and folders in the source file display that are currently selected in the destination. The comparison is only done on the filename - the files are not actually compared.

*Example:* `Select DESTTOSOURCE`
</td></tr><tr><td>
</td><td>
</td><td>

**in**</td><td>

Selects all files and folders in the source file display that exist in the destination.

*Example:* `Select DESTTOSOURCE=in`
</td></tr><tr><td>
</td><td>
</td><td>

**noext**</td><td>

Does not consider file extensions when comparing selected files in the source and destination. For example, if **IMGP1234.JPG** was selected in the destination, and **IMGP1234.WAV** existed in the source, it would be selected.

*Example:* `Select DESTTOSOURCE=noext`
</td></tr><tr><td>
</td><td>
</td><td>

**notin**</td><td>

Selects all files and folders in the source file display that don't exist in the destination.

*Example:* `Select DESTTOSOURCE=notin`
</td></tr><tr><td>
DUPES</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the **Duplicates Selection** dialog, which lets you select files after performing a [duplicates search](/Manual/additional_functionality/duplicate_file_finder.md).

*Example:* `Select DUPES`
</td></tr><tr><td>
EXACT</td><td>
/S</td><td>

*(no value)*</td><td>

Indicates that the PATTERN argument is a literal file name and not a wildcard or regular expression. This allows you to specify an exact filename without having to escape wildcard characters like '(' and ')'.

*Example:* `Select "Cat Photo (1).jpg" EXACT`
</td></tr><tr><td>
FILTER</td><td>
/S</td><td>

*(no value)*</td><td>

Performs file selection using a pre-defined filter. The name of the filter must be given as the value of the **PATTERN** argument. Filters must have previously been configured through the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences.

You can use this with the **TYPE** argument to restrict the filter to either files or folders only.

*Example:* `Select "Image Files" FILTER`

You can also use this from a script, by using the **[Command](../../scripting_reference/scripting_objects/command.md).SetFilter** method to assign a filter to a **Command** object. Running the command `Select FILTER` from that object would select files according to the filter.
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

Lets you define a filter in [text format](/Manual/file_operations/filtered_operations/textual_filters.md) to select matching files. Similar to the **FILTER** argument, however the filter does not need to be predefined.

This is a **/R** argument and so everything after the **FILTERDEF** keyword will be treated as the argument's value.

*Example:* `Select FILTERDEF name match \*.zip and size match \> 2 mb`
</td></tr><tr><td>
FILTERFLAGS</td><td>
/K</td><td>

**select**</td><td>

Select files that match the filter (this argument is used in conjunction with the **FILTER** argument). This is the default behaviour.

*Example:* `Select Documents FILTER FILTERFLAGS=select`
</td></tr><tr><td>
</td><td>
</td><td>

**deselect**</td><td>

Deselect files that match the filter.

*Example:* `Select "Music Files" FILTER FILTERFLAGS=deselect`
</td></tr><tr><td>
</td><td>
</td><td>

**hide**</td><td>

Hide files that match the filter.

*Example:* `Select "Temp Files" FILTER FILTERFLAGS=hide`
</td></tr><tr><td>
</td><td>
</td><td>

**hidenomatch**</td><td>

Hide files that don't match the filter.

*Example:* `Select "Image Files" FILTER FILTERFLAGS=hidenomatch`
</td></tr><tr><td>
FIRST</td><td>
/S</td><td>

*(no value)*</td><td>

Select the first item in the source file display, deselect all other items.

*Example:* `Select FIRST`
</td></tr><tr><td>
FROMCHECKS</td><td>
/S</td><td>

*(no value)*</td><td>

Convert the state of checked items to selections (checked items will be selected, non-checked items will be deselected). This only applies in [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md).

*Example:* `Select FROMCHECKS`
</td></tr><tr><td>
FROMSCRIPT</td><td>
/S</td><td>

*(no value)*</td><td>

This command should be used when running a Select command from a script (e.g. via **Command.RunCommand**). It tells the command to select the files in the **Command** object itself.

*Example:* `Func.Command.RunCommand("Select FROMSCRIPT");`
</td></tr><tr><td>
GROUPNAME</td><td>
/O</td><td>

*(no value)*</td><td>

When the file display is [grouped](/Manual/basic_concepts/sorting_and_grouping/README.md), this lets you select files based on the group they are in. When **GROUPNAME** is used without an associated value, the value of the **PATTERN** argument is used as the name of the group to match.

The example below selects all files in groups beginning with **X**.

*Example:* `Select X\* GROUPNAME`
</td></tr><tr><td>
</td><td>
</td><td>

*\<group name\>*</td><td>

When a value is provided for the **GROUPNAME** argument it specifies the name (or wildcard pattern) of the file group. The selection operation will be confined to files and folders in matching groups.

You can also use this in conjunction with the **SETFOCUS** argument to give input focus to a group header.

*Example:* `Select \*.jpg GROUPNAME Today`  
*Example:* `Select NOPATTERN GROUPNAME Yesterday SETFOCUS`
</td></tr><tr><td>
HIDESEL</td><td>
/O</td><td>

*(no value)*</td><td>

Hide all selected items (both files and folders). This is used either with the **PATTERN** argument to hide all files that match the pattern, or with the **NOPATTERN** argument to hide all currently selected files.

*Example:* `Select \*.tmp HIDESEL`
</td></tr><tr><td>
</td><td>
</td><td>

**dirs**</td><td>

Hide all selected directories.

*Example:* `Select HIDESEL=dirs NOPATTERN`
</td></tr><tr><td>
</td><td>
</td><td>

**files**</td><td>

Hide all selected files.

*Example:* `Select HIDESEL=files NOPATTERN`
</td></tr><tr><td>
HIDEUNAFFECTED</td><td>
/S</td><td>

*(no value)*</td><td>

When used with the [synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md) tool, this hides any items from the list that are not marked to be synchronized (either copied or deleted).

*Example:* `Select HIDEUNAFFECTED`
</td></tr><tr><td>
HIDEUNSEL</td><td>
/O</td><td>

*(no value)*</td><td>

Hide all unselected items (both files and folders). This is used either with the **PATTERN** argument (files that don't match the pattern will be hidden), or with the **NOPATTERN** argument (all currently unselected files will be hidden).

*Example:* `Select NOPATTERN HIDEUNSEL`
</td></tr><tr><td>
</td><td>
</td><td>

**dirs**</td><td>

Hide all unselected directories.

*Example:* `Select HIDEUNSEL=dirs NOPATTERN`
</td></tr><tr><td>
</td><td>
</td><td>

**files**</td><td>

Hide all unselected files.

*Example:* `Select HIDEUNSEL=files NOPATTERN`
</td></tr><tr><td>
IGNORECHECKBOXMODE</td><td>
/S</td><td>

*(no value)*</td><td>

The command will act as if the file display is not in [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md), even if it is. Normally, the Select command will check and uncheck files while in checkbox mode, but this argument allows you to modify the normal file selection and leave the checkboxes alone. In particular, it allows scripts to set the normal selection and focus item to a particular file without modifying the checkbox states.

*Example:* `Select "dopus.exe" IGNORECHECKBOXMODE`
</td></tr><tr><td>
INVERT</td><td>
/S</td><td>

*(no value)*</td><td>

Inverts the selection state of all items in the source file display.

*Example:* `Select INVERT`
</td></tr><tr><td>
LAST</td><td>
/S</td><td>

*(no value)*</td><td>

Selects the last item in the source file display, deselect all other items.

*Example:* `Select LAST`
</td></tr><tr><td>
MAKEVISIBLE</td><td>
/O</td><td>

*(no value)*</td><td>

Ensures that the first selected item is visible in the file display. The list will be scrolled if needed. Similar to the **SETFOCUS** argument except the viewer pane will not update to show the new selection.

*Example:* `Select \*.doc MAKEVISIBLE`
</td></tr><tr><td>
</td><td>
</td><td>

**immediate**</td><td>

Prevents the short delay that normally occurs before the selected file is scrolled into view.

*Example:* `Select NEXT MAKEVISIBLE=immediate`
</td></tr><tr><td>
NEXT</td><td>
/O</td><td>

*(no value)*</td><td>

Selects the next item in the file display. The first item immediately following the first currently selected item will be selected, and all other items deselected.

*Example:* `Select NEXT`
</td></tr><tr><td>
</td><td>
</td><td>

**mark**</td><td>

Toggles the selection state of the currently focused item, and moves the input focus to the next item in the list. This is the equivalent of pressing the **Insert** key in the file display.

*Example:* `Select NEXT=mark`
</td></tr><tr><td>
</td><td>
</td><td>

**nodeselect**</td><td>

Prevents any currently selected items from being deselected.

*Example:* `Select NEXT=nodeselect`
</td></tr><tr><td>
</td><td>
</td><td>

**row**</td><td>

In the icon display modes (e.g. Thumbnails mode) this will move the selection down one row (vertically instead of horizontally). Ignored in Details and Power modes.

*Example:* `Select NEXT=row,mark`
</td></tr><tr><td>
NONE</td><td>
/S</td><td>

*(no value)*</td><td>

Deselects all items in the source file display.

*Example:* `Select NONE`
</td></tr><tr><td>
NOPATTERN</td><td>
/S</td><td>

*(no value)*</td><td>

The **Select** command normally requires a value for the **PATTERN** argument to operate, but in some cases you may need it to operate without supplying a pattern. For example, the **HIDESEL** and **HIDEUNSEL** arguments can be used to hide all currently selected or unselected items without applying a new wildcard selection first.

*Example:* `Select HIDESEL NOPATTERN`
</td></tr><tr><td>
PATTERN</td><td>
</td><td>

*\<pattern\>*</td><td>

Specify a wildcard pattern. All items matching the supplied pattern will be selected (or deselected, hidden, etc. based on the other arguments for this command). The pattern can be specified using [standard pattern matching](../../wildcard_reference/pattern_matching_syntax.md) syntax, or [regular expressions](../../wildcard_reference/regular_expression_syntax.md) if the **REGEXP** argument is supplied. The **PATTERN** argument is also used to provide the name of a pre-defined filter in conjunction with the **FILTER** argument.

This is the default argument for the **Select** command and so the **PATTERN** keyword does not need to be supplied.

*Example:* `Select \*.(bmp\|jpg\|gif) HIDEUNSEL`
</td></tr><tr><td>
PREV</td><td>
/O</td><td>

*(no value)*</td><td>

Select the previous item in the file display. The first item immediately preceding the last currently selected item will be selected, and all other items deselected.

*Example:* `Select PREV`
</td></tr><tr><td>
</td><td>
</td><td>

**mark**</td><td>

Toggles the selection state of the currently focused item, and moves the input focus to the previous item in the list. Similar to pressing the **Insert** key, except the focus moves to the previous rather than the next item.

*Example:* `Select PREV=mark`
</td></tr><tr><td>
</td><td>
</td><td>

**nodeselect**</td><td>

Prevents any currently selected items from being deselected.

*Example:* `Select PREV=nodeselect`
</td></tr><tr><td>
</td><td>
</td><td>

**row**</td><td>

In the icon display modes (e.g. Thumbnails mode) this will move the selection up one row (vertically instead of horizontally). Ignored in Details and Power modes.

*Example:* `Select PREV=row,mark`
</td></tr><tr><td>
RANGE</td><td>
/K</td><td>

*\<range\>*</td><td>

Selects a range of items based on their index (their position in the list). This command is equivalent to the range selection mode of the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field. The *\<range\>* value consists of one or more comma-separated ranges; each range can be a single number, or two numbers separated by a hyphen to indicate all numbers within that range.

*Example:* `Select RANGE 3,8-15,22-25,30`
</td></tr><tr><td>
REGEXP</td><td>
/S</td><td>

*(no value)*</td><td>

Use [regular expression](../../wildcard_reference/regular_expression_syntax.md) mode instead of standard pattern matching.

*Example:* `Select .\*\\jpg REGEXP`
</td></tr><tr><td>
RESELECT</td><td>
/S</td><td>

*(no value)*</td><td>

Reselects all files and folders that were used (and deselected) by the previously executed command.

*Example:* `Select RESELECT`
</td></tr><tr><td>
SETFOCUS</td><td>
/S</td><td>

*(no value)*</td><td>

Ensures that the first selected item is visible in the file display. The list will be scrolled if needed. Additionally, if the viewer pane is open the first selected file will be automatically viewed if possible.

*Example:* `Select \*.jpg SETFOCUS`
</td></tr><tr><td>
SHOWFOCUS</td><td>
/S</td><td>

*(no value)*</td><td>

If necessary, scrolls the file display to make the currently focused item visible. The selection will not be modified.

*Example:* `Select SHOWFOCUS`
</td></tr><tr><td>
SHOWHIDDEN</td><td>
/O</td><td>

*(no value)*</td><td>

Reveal any files or folders that have previously been hidden by commands using the **HIDESEL** or **HIDEUNSEL** arguments. The other way to reveal files hidden this way is by re-reading the folder (e.g. press **F5**).

*Example:* `Select NOPATTERN SHOWHIDDEN`
</td></tr><tr><td>
</td><td>
</td><td>

**dirs**</td><td>

Reveals all hidden directories.

*Example:* `Select SHOWHIDDEN=dirs NOPATTERN`
</td></tr><tr><td>
</td><td>
</td><td>

**files**</td><td>

Reveals all hidden files.

*Example:* `Select SHOWHIDDEN=files NOPATTERN`
</td></tr><tr><td>
SHOWUNAFFECTED</td><td>
/S</td><td>

*(no value)*</td><td>

When used with the [synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md) tool, this reveals any items that have previously been hidden because they were not marked to be synchronized (either copied or deleted).

*Example:* `Select SHOWUNAFFECTED`
</td></tr><tr><td>
SIMILAR</td><td>
/S</td><td>

*(no value)*</td><td>

Selects all files with the same file extensions as the currently selected files. For example, if a single **.jpg** and a single **.gif** file are currently selected, this command would select *all* **.jpg** and **.gif** files in the source file display.

*Example:* `Select SIMILAR`
</td></tr><tr><td>
</td><td>
</td><td>

**trueext**</td><td>

Causes the command to ignore multi-part extensions. E.g. **file.part1.rar**, **file.part2.rar** and **file.part3.rar** would all be considered to be **.rar** files rather than having different extensions.

*Example:* `Select SIMILAR=trueext`
</td></tr><tr><td>
SIMILARBASE</td><td>
/S</td><td>

*(no value)*</td><td>

Selects all files with the same base-names as the currently selected files. For example, if **cat.jpg** and **dog.gif** are currently selected, this command would select *all* **cat.**\* and **dog.**\* files in the source file display.

*Example:* `Select SIMILARBASE`
</td></tr><tr><td>
SIMPLE</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the *Select* dialog in [simple](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.md) mode.

*Example:* `Select SIMPLE`
</td></tr><tr><td>
SIZE</td><td>
/K</td><td>

*\<size\>*</td><td>

Select files whose size matches the specified size. By default the size specified is treated as bytes, but you can use the following suffixes to use different units:

- **kb** - kilobytes
- **mb** - megabytes
- **gb** - gigabytes You can also use **\>** (greater than) before the size to match all files larger than the specified size, or **\<** (less than) before the size to match all files smaller than the specified size.

*Example:* `Select \*.png SIZE \>2mb`
</td></tr><tr><td>
</td><td>
</td><td>

*\<size1\>***..***\<size2\>*</td><td>

Select files whose size falls between the two specified sizes. Both sizes are supplied in the format described above.

*Example:* `Select SIZE 500kb..5mb DESELECTNOMATCH`
</td></tr><tr><td>
</td><td>
</td><td>

**largest**</td><td>

Select the largest item in the current source file display. You can combine this with the **PATTERN** argument to select the largest of a specific type of file.

*Example:* `Select \*.doc SIZE=largest`
</td></tr><tr><td>
</td><td>
</td><td>

**smallest**</td><td>

Select the smallest item in the current file display.

*Example:* `Select SIZE=smallest`
</td></tr><tr><td>
SOURCETODEST</td><td>
/O</td><td>

*(no value)*</td><td>

Selects all files and folders in the destination file display that are currently selected in the source. The comparison is only done on the filename - the files are not actually compared.

*Example:* `Select SOURCETODEST`
</td></tr><tr><td>
</td><td>
</td><td>

**in**</td><td>

Selects all files and folders in the destination file display that exist in the source.

*Example:* `Select SOURCETODEST=in`
</td></tr><tr><td>
</td><td>
</td><td>

**noext**</td><td>

Does not consider file extensions when comparing selected files in the source and destination. For example, if **IMGP1234.JPG** was selected in the source, and **IMGP1234.WAV** existed in the destination, it would be selected.

*Example:* `Select SOURCETODEST=noext`
</td></tr><tr><td>
</td><td>
</td><td>

**notin**</td><td>

Selects all files and folders in the destination file display that don't exist in the source.

*Example:* `Select SOURCETODEST=notin`
</td></tr><tr><td>
THIS</td><td>
/S</td><td>

*(no value)*</td><td>

Selects the current focus entry. It is possible for the entry with input focus to not be selected (for example, if you move the focus highlight with **Control + Cursor-Down**) and this command will select whichever entry is currently focused.

*Example:* `Select THIS`
</td></tr><tr><td>
TOCHECKS</td><td>
/S</td><td>

*(no value)*</td><td>

Convert item selection states to check states. Selected items will be checked, and unselected items will be unchecked. If the file display is not currently in [checkbox mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/checkbox_mode.md) it will be turned on automatically.

*Example:* `Select TOCHECKS`
</td></tr><tr><td>
TYPE</td><td>
/K</td><td>

**files**</td><td>

Force the selection to only affect files - even if folders match the pattern they will be unaffected.

You can add the **DESELECTOTHERTYPE** argument to deselect all items of the "other" type.

*Example:* `Select a\* TYPE=files`
</td></tr><tr><td>
</td><td>
</td><td>

**dirs**</td><td>

Force the selection to only affect folders.

*Example:* `Select "new \*" TYPE=dirs`
</td></tr></tbody>
</table>

