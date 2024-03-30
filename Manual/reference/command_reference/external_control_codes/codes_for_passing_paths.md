# Codes for passing paths

The following codes are used to pass various paths to external programs. The path codes available offer all possible combinations of the following three criteria:

- **Which path -** either the current source or destination path, or in a dual-display Lister, the left (top) or right (bottom) paths irrespective of their source/destination status.
- **Path required** or **not required** - when a path is required, the command will not be run at all if that path is not valid - for example, when there is no valid destination folder. When the path is not required, the command will still be run and it will act as if the path code was not present at all.
- **Long filenames** or **short filenames** - short filenames are useful for running 16 bit programs or other legacy software that can't handle long filenames.

The long form of each code is built from a combination of keywords that reflect the three criteria. If a long code ends in a **\$** sign it is the "path required" form of the code - it is said to "need" a valid path. Note that the **left** and **right** paths do not support the "required" forms.

<table>
<thead><tr><th>
Long form</th><th>
Short form</th><th>
Description
</th></tr></thead><tbody><tr><td>
{sourcepath}</td><td>
{s!}</td><td>
Source path, long filenames, not required.
</td></tr><tr><td>
{sourcepath\$}</td><td>
{s}</td><td>
Source path, long filenames, required.
</td></tr><tr><td>
{destpath}</td><td>
{d!}</td><td>
Destination path, long filenames, not required.
</td></tr><tr><td>
{destpath\$}</td><td>
{d}</td><td>
Destination path, long filenames, required.
</td></tr><tr><td>
{sourcepathshort}</td><td>
{ss!}</td><td>
Source path, short filenames, not required.
</td></tr><tr><td>
{sourcepathshort\$}</td><td>
{ss}</td><td>
Source path, short filenames, required.
</td></tr><tr><td>
{destpathshort}</td><td>
{ds!}</td><td>
Destination path, short filenames, not required.
</td></tr><tr><td>
{destpathshort\$}</td><td>
{ds}</td><td>
Destination path, short filenames, required.
</td></tr><tr><td>
{leftpath}</td><td>
{l}</td><td>
Left (top) path, long filenames.
</td></tr><tr><td>
{rightpath}</td><td>
{r}</td><td>
Right (bottom) path, long filenames.
</td></tr><tr><td>
{leftpathshort}</td><td>
{ls}</td><td>
Left path, short filenames.
</td></tr><tr><td>
{rightpathshort}</td><td>
{rs}</td><td>
Right path, long filenames.
</td></tr></tbody>
</table>

In addition to the path codes related to current Lister paths, the following codes allow you to pass the values of certain system or application-specific paths.

<table>
<thead><tr><th>
Long form</th><th>
Short form</th><th>
Description
</th></tr></thead><tbody><tr><td>
{apppath}</td><td>
{p}</td><td>

Returns the path of an installed application, as listed in the *App Paths* key in the registry. For example, **{apppath\|winword.exe}** would insert the install path of Microsoft Word.
</td></tr><tr><td>
{apppathshort}</td><td>
{ps}</td><td>
The path of an installed application, in short (8.3) format.
</td></tr><tr><td>
{alias}</td><td>
{A}</td><td>

Returns the path of a [folder alias](/Manual/basic_concepts/the_lister/navigation/aliases.md). For example, **{alias\|mydocuments}** would return the path to your documents folder.

You can use **{alias\|libraries}** to resolve the path of a library folder; for example, **{alias\|libraries}/Documents** would return the real (default) path of the *Documents* library.
</td></tr><tr><td>
{aliasshort}</td><td>
{As}</td><td>
The path of a folder alias, in short (8.3) format.
</td></tr></tbody>
</table>

The path codes support the following modifiers. These can be added to the control code sequence using a vertical bar (**\|**) to separate the filename code from the modifier - for example, **{sourcepath\|noterm}** strips the trailing termination character from the path. Multiple modifiers can be provided using additional vertical bars to separate them - for example **{sourcepath\|nopath\|noterm}** combines both **nopath** and **noterm** together.

<table>
<thead><tr><th>
Modifier</th><th>
Description
</th></tr></thead><tbody><tr><td>

**escbackslash**</td><td>

Automatically escapes any occurrences of **\\** in the path, turning them into **\\**.  
This can be necessary when using codes like **{sourcepath}** to insert paths into strings which will have sequences like \n and \\ interpreted specially.  
For example, a command to add the source and destination paths to the clipboard on separate lines:

**[Clipboard](../internal_commands/clipboard.md) EXPANDNEWLINES SET {sourcepath\|escbackslash}\n{destpath\|escbackslash}**.

In this example, if the source path was *C:\New Folder\\* then it would be converted to *C:\\New Folder\\*. If the *\N* sequence had not been escaped, it would have removed the letter *N* from the path and put *ew Folder\\* on a separate line. More subtly, if the *\\* on the end of the source path was not also escaped, it would have interfered with the *\n* which comes between the two paths in the example command.
</td></tr><tr><td>

**escforfilter**</td><td>

Intended for inserting paths into inline filter definitions.  
The same as **escbackslash** and **escwild** combined, but easier to remember and less to type.
</td></tr><tr><td>

**escnl**</td><td>

Automatically escapes any occurrences of **\n** in the path, turning them into **\\n**.  
(This is a weaker version of **escbackslash**, above. You should probably use **escbackslash** instead.)  
Using **escnl** helps when using codes like **{sourcepath}** as the message text for a dialog code like **[{dlgstring}](codes_to_display_dialogs.md)**. For example, the path *C:\New Folder\\* would be converted to *C:\\New Folder\\*. If the **\n** sequence weren't escaped, it would have been converted into a line-break in the dialog message text.
</td></tr><tr><td>

**escregex**  
**escregexp**</td><td>

Automatically escapes any regular expression characters in the path. Used when passing paths to internal commands that understand [regular expressions](../../wildcard_reference/regular_expression_syntax.md), in case a path contains characters like **\\**, **.**, **(** and **)** which have special meaning to some functions. For example, **{sourcepath\|escregexp\|noterm}** would turn *C:\Accounts (2010)\\* into *C:\\Accounts \\2010\\*.  
For convenience, both the "regex" and "regexp" spellings are allowed and do the same thing.
</td></tr><tr><td>

**escwild**</td><td>

Automatically escapes any wildcard characters in the path. Used when passing paths to internal commands that understand [standard wildcards](../../wildcard_reference/pattern_matching_syntax.md), in case a path contains characters like **(** and **)** which have special meaning to some functions. For example, **{sourcepath\|escwild\|noterm}** would turn *C:\Accounts (2010)\\* into *C:\Accounts '(2010')*.
</td></tr><tr><td>

**nopath**</td><td>

Returns only the final component of the path. For example, if **{sourcepath}** returns *C:\Program Files\GPSoftware\Directory Opus\\*, **{sourcepath\|nopath}** would return *Directory Opus\\*.
</td></tr><tr><td>

**noroot**</td><td>

Returns the path without the root, i.e. without the first component. For example, if **{sourcepath}** returns *C:\Program Files\GPSoftware\Directory Opus\\*, **{sourcepath\|noroot}** would return *Program Files\GPSoftware\Directory Opus\\*. With UNC network paths, the result is relative to the share, with the computer and share itself removed. With FTP paths, the result is relative to the site's root and excludes the site itself. You can combine **noroot** with **..** to get a parent path with the root removed. For example, **{sourcepath\|..\|noroot}**
</td></tr><tr><td>

**noshort**</td><td>

Suppresses automatic shortening of paths which are longer than 260 characters. Opus itself can handle very long paths but many Windows programs cannot. When sending very long paths to external programs, Opus normally uses the short (8.3) versions to reduce problems. Use **noshort** to prevent this when you know the target program can cope. For example, **{sourcepath\|noshort}**.
</td></tr><tr><td>

**noterm**</td><td>

Strips the trailing path separator from the returned path. For example, **{sourcepath\|noterm}** might return *C:\Program Files\GPSoftware\Directory Opus*.
</td></tr><tr><td>

**subdir**</td><td>

Replaces characters in the path so that it can be added below another path. For example, **{sourcepath\|subdir}** might return *C;\Program Files*. Note that a semi-colon has replaced the colon, allowing the path to be used as a sub-directory, say if you wanted to backup the files from there into *D:\Backups\C;\Program Files*.
</td></tr><tr><td>

**cleanfilename**</td><td>

Replaces any illegal filename characters in the string, and also replaces all path separators and colons, so the string can be used as a filename without it adding any additional path levels. Similar to **subdir** in this context, but it also replaces path separators.
</td></tr><tr><td>

**cleanfilepath**</td><td>
Replaces any illegal filename characters in the string, while leaving path separators and colons. (Colons are only left in if they are part of a drive letter at the start of the string.) Should be used when the string can be an absolute path. (Will not usually have an effect in this context, given the input should already a valid file name or path. More useful with clipboard data.)
</td></tr><tr><td>

**cleanfilepathrel**</td><td>

Replaces any illegal filename characters in the string, also replacing colons and "\\" UNC path initiators, so the string can be used as a subdirectory under another path. Similar to **subdir** in this context, given the input is already a file name or path. (Unlike **subdir**, **cleanfilepathrel** can also be used with arbitrary clipboard input.)
</td></tr><tr><td>

**wsl**</td><td>

Returns the path in WSL (Windows System for Linux) format (e.g. **/mnt/c/Program Files/** instead of **C:\Program Files**).
</td></tr><tr><td>

**pair**</td><td>

If the path in question has a [paired folder](/Manual/preferences/preferences_categories/frequently_used_paths/paired_folders.md) then this modifier returns its pair. You can combine this with other modifiers, for example **{sourcepath\|pair\|..}** would return the pair's parent.

Additional modifiers can be used to override the paired folder's "If non-existent" mode. For example, you might want this in a button which will create the paired folder if it doesn't already exist. Supported modifiers are **pairgotoparent**, **pairignorepair** and **pairuseanyway**.
</td></tr><tr><td>

**..**</td><td>

Modifies the code to refer to the path's parent rather than the path itself. You can pass multiple **..** modifiers separated by **\\** to return folders higher up the tree. For example **{destpath\|..\\.}** would return the parent of the parent of the current destination path.
</td></tr><tr><td>

**\\**</td><td>

Modifies the code to refer to the root of the drive of the specified path. For example **{sourcepath\|\\** might return **C:\\**.
</td></tr></tbody>
</table>

