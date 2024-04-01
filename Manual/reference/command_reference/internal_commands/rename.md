# Rename

The **Rename** internal command can be used to:

- Trigger [inline rename](/Manual/file_operations/renaming_files/inline_rename.md) mode, letting you quickly edit the name of a file or folder
- Display the [Rename](/Manual/file_operations/renaming_files/README.md) dialog, letting you perform wildcard and scripted renames on multiple files at once
- Perform automated rename operations
- [Embed a rename script](/Manual/customize/creating_your_own_buttons/embedding_rename_scripts.md) in a button or hotkey

Note that the [Advanced Rename](/Manual/file_operations/renaming_files/advanced_rename/README.md) dialog lets you automatically create a command line using the user interface - simply configure the dialog as desired and then select **Create function from current settings** from the dropdown **Clipboard** menu at the bottom of the dialog.

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>

*(no argument)*</td><td>
-</td><td>
-</td><td>

Displays the **[Rename](/Manual/file_operations/renaming_files/README.md)** dialog. The rename operation will be performed on all selected files and folders. The dialog will open in the last mode it was used in (either [simple](/Manual/file_operations/renaming_files/simple_wildcard_rename.md) or [advanced](/Manual/file_operations/renaming_files/advanced_rename/README.md)).

*Example:* `Rename`
</td></tr><tr><td>
ADVANCED</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the Rename dialog in [advanced](/Manual/file_operations/renaming_files/advanced_rename/README.md) mode.

*Example:* `Rename ADVANCED`

When combined with rename patterns or preset names, the **ADVANCED** argument can be used to ensure the command opens the Rename dialog instead of immediately renaming all selected items.

*Example:* `Rename ADVANCED PATTERN=* TO=*.bak`  
*Example:* `Rename ADVANCED PRESET="Number Files"`
</td></tr><tr><td>
APPLYNOMATCH</td><td>
/S</td><td>

*(no value)*</td><td>

Turns on the **Apply actions even if pattern doesn't match** option for the rename function. This makes things like the **CASE** argument apply to all filenames, whether they match the old name pattern (given by the **PATTERN** argument) or not.

*Example:* `Rename PATTERN "*.jpeg" TO "*.jpg" CASE=allwords APPLYNOMATCH`
</td></tr><tr><td>
AUTONUMBER</td><td>
/S</td><td>

*(no value)*</td><td>

Automatically adds an incrementing number to the end of new filenames if they clash with existing files.

*Example:* `Rename PATTERN "The *" TO * AUTONUMBER`
</td></tr><tr><td>
BY</td><td>
/K/N</td><td>

*\<increment\>*</td><td>

Specifies the increment when renaming files with automatic numbering (using the **NUMBER** option). If not specified the default increment is 1.

*Example:* `Rename NUMBER BY 2`
</td></tr><tr><td>
CASE</td><td>
/K</td><td>

**upper**</td><td>

Converts filenames to all-upper case.

*Example:* `Rename CASE=upper`
</td></tr><tr><td>
</td><td>
</td><td>

**lower**</td><td>

Converts filenames to all-lower case.

*Example:* `Rename CASE=lower NUMBER`
</td></tr><tr><td>
</td><td>
</td><td>

**firstword**</td><td>

Capitalizes the first letter of the filename.

*Example:* `Rename CASE=firstword`
</td></tr><tr><td>
</td><td>
</td><td>

**allwords**</td><td>

Capitalizes the first letter of each word of the filename.

*Example:* `Rename CASE=allwords`
</td></tr><tr><td>
</td><td>
</td><td>

**extupper**</td><td>

Converts the filename extension to upper case.

*Example:* `Rename CASE=extupper`
</td></tr><tr><td>
</td><td>
</td><td>

**extlower**</td><td>

Converts the filename extension to lower case.

*Example:* `Rename CASE=extlower`
</td></tr><tr><td>
</td><td>
</td><td>

**extignore**</td><td>

Ignores the extension while applying case changes to the filename. Use this in conjunction with one of the other keywords.

*Example:* `Rename CASE=upper,extignore`
</td></tr><tr><td>
FINDREP</td><td>
/O</td><td>

*(no value)*</td><td>

Enable find-and-replace mode. The **PATTERN** argument must be used to provide the string to find, and the **TO** argument provides the string to replace it with. You can optionally combine this with the **REGEXP** argument.

*Example:* `Rename FINDREP PATTERN="jones" TO="smith"`
</td></tr><tr><td>
</td><td>
</td><td>

**ext**</td><td>

Makes find-and-replace operate in the filename extension as well as in the stem of the filename.

*Example:* `Rename FINDREP=ext PATTERN="jpg" TO="jpeg"`
</td></tr><tr><td>
FROM</td><td>
</td><td>

*\<filename\> ...*</td><td>

Renames the files specified on the command line, rather than those selected in the source file display. This argument can accept filenames or [wildcard patterns](../../wildcard_reference/pattern_matching_syntax.md). Remember to enclose each filename in quotes if it contains spaces.

*Example:* `Rename FROM C:\Spool\\.tmp TO *.temp`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(no value)*</td><td>

When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.

When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.

*Example:* `Rename PRESET=!list,favesonly HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

You can specify the heading text if you want it to be different to the button's label.

*Example:* `Rename PRESET=!list HEADING="Rename Presets"`
</td></tr><tr><td>
IGNOREEXT</td><td>
/S</td><td>

*(no value)*</td><td>

Turns on the **Ignore extensions** option for the rename function. Filename extensions won't be affected and don't need to be accounted for in any wildcard patterns.

*Example:* `Rename PATTERN * TO *_backup IGNOREEXT`

The **Ignore extensions** option is off by default for non-interactive renames, to avoid breaking old buttons. You only need to use the **IGNOREEXT** argument with rename commands which specify everything on the command line and do not open the Rename dialog.

The **Ignore extensions** option is on by default for interactive renames which open the dialog. You can turn the option off in the dialog via the separate **NOIGNOREEXT** argument, documented below.
</td></tr><tr><td>
INLINE</td><td>
/O</td><td>

*(no value)*</td><td>

Activates [inline renaming](/Manual/file_operations/renaming_files/inline_rename.md) on the item in the source file display that currently has focus.

*Example:* `Rename INLINE`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Automatically selects the entire filename for editing.

*Example:* `Rename INLINE=all`
</td></tr><tr><td>
</td><td>
</td><td>

**name**</td><td>

Automatically selects the filename's stem (but not the extension). Selects the whole name for a folder.

*Example:* `Rename INLINE=name`
</td></tr><tr><td>
</td><td>
</td><td>

**endstem**</td><td>

Positions the cursor at the end of the filename's stem (before the extension), but does not automatically select any part of the name.

*Example:* `Rename INLINE=endstem`
</td></tr><tr><td>
</td><td>
</td><td>

**ext**</td><td>

Automatically selects the filename's extension. Selects the whole name for a folder.

*Example:* `Rename INLINE=ext`
</td></tr><tr><td>
</td><td>
</td><td>

**home**</td><td>

Positions the cursor at the beginning of the filename.

*Example:* `Rename INLINE=home`
</td></tr><tr><td>
</td><td>
</td><td>

**end**</td><td>

Positions the cursor at the end of the filename.

*Example:* `Rename INLINE=end`
</td></tr><tr><td>
</td><td>
</td><td>

**single**</td><td>

If more than one item is selected, the **Rename** dialog will be displayed. Without this, inline rename will begin on the focused item only.

*Example:* `Rename INLINE=name,single`
</td></tr><tr><td>
MACRO</td><td>
/K</td><td>
</td><td>

Lets you specify a rename [macro operation](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.md) string. You can use the macro builder in the Rename dialog to generate these strings and then hardcode them in a command.

*Example:* `Rename` MACRO R0-6/L0+Final
</td></tr><tr><td>
MATCHCASE</td><td>
/S</td><td>

*(no value)*</td><td>

Makes the rename operation case-sensitive. Patterns and search strings must match the exact case of the filename.

*Example:* `Rename PATTERN *.jpG TO *.JPG MATCHCASE`
</td></tr><tr><td>
NOFILEINFO</td><td>
/S</td><td>

*(no value)*</td><td>

Disable file information metadata insertion. For example, the string **{mp3title}** would normally insert the title of an MP3 file in the new filename. With **NOFILEINFO** specified, the literal string "{mp3title}" would be inserted in the new filename.

*Example:* `Rename PATTERN * TO *_{name} NOFILEINFO `
</td></tr><tr><td>
NOIGNOREEXT</td><td>
/S</td><td>

*(no value)*</td><td>

Turns off the **Ignore Extension** option in the Rename dialog when it first opens. You only need to use this argument when opening the Rename dialog for interactive use.

*Example:* `Rename PATTERN *.JPEG TO *.JPG ADVANCED NOIGNOREEXT`

For non-interactive use of the Rename command, the **Ignore Extension** option is off by default (to avoid breaking old buttons) and can be turned on via the separate **IGNOREEXT** argument, documented above.
</td></tr><tr><td>
NOMATCHNOFAIL</td><td>
/S</td><td>

*(no value)*</td><td>

Files which do not match the rename pattern are not 'failed'. This can be useful with multi-line functions which need to do some optional renaming before passing all of the files to additional commands.

By default, when **NOMATCHNOFAIL** is not used, if a file does not match the rename pattern then it will be flagged as a failure and skipped by the rest of the function (unless the very next command is another **Rename**, in which case the file gets a second chance).

If **NOMATCHNOFAIL** is used then files which do not match the rename pattern are still passed to subsequent commands.

*Example:* `Rename PATTERN "* Backup"*" TO"*"* NOMATCHNOFAIL`
</td></tr><tr><td>
NUMBER</td><td>
/O</td><td>

*(no value)*</td><td>

Automatically number files. Selected files will be numbered in the order they are presented in the file display, so you should make sure the list is sorted as desired before using this command. The number 1 will be assigned to the first selected file, and the number for each subsequent file will be incremented by the value given for the **BY** argument (or by 1 if **BY** is not provided).

By default the number is added to the end of the filename, in front of the extension. You can specify a different location for the number by providing the **\[#\]** marker in the new filename.

*Example:* `Rename PATTERN * TO \[#\]\* NUMBER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<start\>*</td><td>

Number files starting with the specified number. Providing a value for NUMBER also lets you zero-pad the assigned number. For example, the value **0010** means to start numbering at 10, and zero-pad to four digits. The **\[#\]** marker can also be used to specify zero-padding - **\[#5\]** would zero-pad to five digits.

*Example:* `Rename NUMBER 00001 BY 2`

If you add a **!** before the number, you can use this argument to specify the default value for the corresponding field in the Rename dialog without actually turning on the sequential numbering option. For example, you may want a default of "01" so you get padding to two digits without having to type the extra "0" every time you turn on the option in the UI. If you make use of that, you should also include the **ADVANCED** argument so the Rename dialog appears, instead of it silently performing a rename operation.

*Example:* `Rename ADVANCED NUMBER=!01`
</td></tr><tr><td>
PATTERN</td><td>
/K</td><td>

*\<pattern\>*</td><td>

Specifies a wildcard pattern that represents the old (original) filename. This argument is used when performing a wildcard rename. The Rename command supports a simple wildcard syntax where one or more asterisks supplied for the **PATTERN** argument can be used to copy parts of the original name to the new name. The **PATTERN** argument is also used in conjunction with **REGEXP** to provide the search pattern for a regular expression rename, and in conjunction with **FINDREP** to provide the search string for a find-and-replace rename.

See the section on [Renaming Files](/Manual/file_operations/renaming_files/README.md) for a full discussion of the various renaming modes.

*Example:* `Rename PATTERN IMGP(.*).jpg TO "Image \1.jpg" REGEXP`

Specifying the **FROM** argument as well will mean the command ignores the current file selection and applies the specified rename on all matching files. Only files matching both the TO and PATTERN arguments would be renamed.

*Example:* `Rename FROM *.jpg PATTERN IMGP( *).jpg TO "Image \1.jpg" REGEXP`

If the **PATTERN** and **TO** arguments are both given, the command will normally apply the rename immediately, without prompting for any further interaction; you can add the **ADVANCED** argument to instead display the Rename dialog, with the specified pattern, so that you can preview the operation and make adjustments, or cancel it entirely, as needed.

*Example:* `Rename ADVANCED PATTERN * TO *.bak`
</td></tr><tr><td>
PRESET</td><td>
/K</td><td>

**findrep**</td><td>

Opens the **Rename** dialog in *Find and Replace* mode.

*Example:* `Rename PRESET=findrep`
</td></tr><tr><td>
</td><td>
</td><td>

**regexp**</td><td>

Opens the **Rename** dialog in *Regular Expression* mode.

*Example:* `Rename PRESET=regexp`
</td></tr><tr><td>
</td><td>
</td><td>

**regexpfindrep**</td><td>

Opens the **Rename** dialog in *Regular Expression + Find and Replace* mode.

*Example:* `Rename PRESET=regexpfindrep`
</td></tr><tr><td>
</td><td>
</td><td>

**last  
!last**</td><td>

Specifying **PRESET=last** opens the **Rename** dialog showing the settings from the last time the dialog was used. Similar to opening the dialog and clicking the *Last Rename* button.

*Example:* `Rename PRESET=last`

You can also use **!last** to apply the last rename automatically, without showing the **Rename** dialog first.

*Example:* `Rename PRESET=!last`
</td></tr><tr><td>
</td><td>
</td><td>

**!list**</td><td>

Displays a generated list of saved rename presets (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Selecting a preset from the list will apply that rename operation to the currently selected files and folders.

The generated list can be controlled with the addition of the following keywords:

- **favesonly**: Only displays presets marked as favorites.
- **nofaves**: Only displays presets not marked as favorites.
- **nogroup**: Don't not group favorite and non-favorite presets separately.

*Example:* `Rename PRESET=!list,favesonly`
</td></tr><tr><td>
</td><td>
</td><td>

*\<preset\>*</td><td>

Applies the named saved rename preset to all currently selected files and folders. Rename presets are created through the **[Advanced Rename](/Manual/file_operations/renaming_files/advanced_rename/README.md)** dialog.

*Example:* `Rename PRESET="Number Files"`

You can add the **ADVANCED** argument to make the dialog open and allow you to make changes, or cancel the operation entirely, before the rename is applied.

*Example:* `Rename ADVANCED PRESET="Number Files"`
</td></tr><tr><td>
RECURSE</td><td>
/S</td><td>

*(no value)*</td><td>

The rename operation will operate recursively on all files inside selected sub-folders.

*Example:* `Rename PATTERN *.jpg TO *.jpeg RECURSE`
</td></tr><tr><td>
REGEXP</td><td>
/S</td><td>

*(no value)*</td><td>

Enables regular expression mode. The search pattern must be provided with the **PATTERN** argument, and the replace pattern with the **TO** argument. You can optionally combine this with the **FINDREP** argument.

*Example:* `Rename PATTERN "(.*) - (.*)\\(.*)" TO "\2 - \1.\3" REGEXP`
</td></tr><tr><td>
RENAMEMATCHING</td><td>
/S</td><td>

*(no value)*</td><td>

Keeps files with the same stem and different extensions together when renumbering. For example, **IMGP1032.JPG** and **IMGP1032.WAV** when renamed would be given the same number.

*Example:* `Rename NUMBER 0001 RENAMEMATCHING`
</td></tr><tr><td>
SCRIPTARG</td><td>
/K/M</td><td>

*\<option:value\>,  
\[\<option:value\>,..\]*</td><td>

Used to pass custom field values to a [rename script](/Manual/scripting/rename_scripts/README.md).

*Example:* `Rename PRESET MyRename SCRIPTARG my_option:True`
</td></tr><tr><td>
SIMPLE</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the Rename dialog in [simple](/Manual/file_operations/renaming_files/simple_wildcard_rename.md) mode.

*Example:* `Rename SIMPLE`
</td></tr><tr><td>
TO</td><td>
/O</td><td>

*\<new name\>*</td><td>

Specifies the new name of the file to rename. This argument is also used to specify the 'to' pattern when renaming using wildcards or regular expression, and the 'replace' string when renaming in find-and-replace mode. This argument can also be provided without a value when doing a find-and-replace rename - in that case, the search string would be replaced with nothing.

*Example:* `Rename PATTERN " (Copy)" TO FINDREP`
</td></tr><tr><td>
TYPE</td><td>
/K</td><td>

**files**</td><td>

Force the rename to only operate on files - any selected folders will be ignored.

*Example:* `Rename PATTERN * TO *.bak TYPE=files`
</td></tr><tr><td>
</td><td>
</td><td>

**dirs**</td><td>

Force the rename to only operate on folders.

*Example:* `Rename PATTERN * TO Copy_* TYPE=dirs`
</td></tr><tr><td>
WHENEXISTS</td><td>
/K</td><td>

**ask**</td><td>

Controls what happens if the new filename already exists. The default action is to **ask** the user for each existing file.

*Example:* `Rename PATTERN * TO *.bak WHENEXISTS=ask`
</td></tr><tr><td>
</td><td>
</td><td>

**delete**</td><td>

Performs the rename as requested, deleting the file that already existed.

*Example:* `Rename PATTERN * TO *.bak WHENEXISTS=delete`
</td></tr><tr><td>
</td><td>
</td><td>

**keep**</td><td>

Performs the rename as requested, renaming the old file that already existed.

*Example:* `Rename PATTERN * TO *.bak WHENEXISTS=keep`
</td></tr><tr><td>
</td><td>
</td><td>

**rename**</td><td>

Modifies the new name by adding a suffix to make it unique.

*Example:* `Rename PATTERN * TO *.bak WHENEXISTS=rename`
</td></tr><tr><td>
</td><td>
</td><td>

**skip**</td><td>

Skips any files that already exist, without performing the rename.

*Example:* `Rename PATTERN * TO *.bak WHENEXISTS=skip`
</td></tr></tbody>
</table>

