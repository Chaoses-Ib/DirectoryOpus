# Codes for passing filenames

The following codes are used to pass the names of selected files to external programs. The filename codes available offer all possible combinations of the following five criteria:

- **Full paths** or **filename only** - whether the full path and name of selected items are passed (e.g. *C:\Program Files\GPSoftware\Directory Opus\dopus.exe*) or just the filename (e.g. *dopus.exe*).
- **One at a time** or **all at once** - when multiple files are selected, this determines whether a command is repeated once for each selected file, or run once only, with all selected filenames passed on the same command line (separated by spaces).
- **Selected items required** or **not required** - when selected items are required and none are selected, the command will not be run at all. When selected items are not required, the command will still be run and it will act as if the filename code was not present at all.
- **Long filenames** or **short filenames** - short filenames are useful for running 16 bit programs or other legacy software that can't handle long filenames.
- **Source** or **destination file display** - in a dual-display Lister, you can pass selected files from the destination file display as well as from the source.

The long form of each code is built from a combination of keywords that reflect the five criteria. If a long code ends in a **\$** sign it is the "selected items required" form of the code - it is said to "need" selected items.

<table>
<thead><tr><th>
Long form</th><th>
Short form</th><th>
Description
</th></tr></thead><tbody><tr><td>
{filepath}</td><td>
{f!}</td><td>

Passes the full path and filename of each selected item. Files are passed one at a time - a command that uses this code will be repeated once for each additional selected item. If no files are selected the command will still be run, passing an empty string for this code.  
*Full paths, one at a time, selected items not required, long filenames, source file display*
</td></tr><tr><td>
{filepath\$}</td><td>
{f}</td><td>

The "need" form of **{filepath}** (requires at least one selected item in the file list).  
*Full paths, one at a time, selected items required, long filenames, source file display*
</td></tr><tr><td>
{file}</td><td>
{o!}</td><td>
Passes the filename only of each selected item (without its path). Multiple files are passed one at a time.  
Filenames only, one at a time, selected items not required, long filenames, source file display
</td></tr><tr><td>
{file\$}</td><td>
{o}</td><td>

The "need" form of **{file}**.  
*Filenames only, one at a time, selected items required, long filenames, source file display*
</td></tr><tr><td>
{allfilepath}</td><td>
{F!}</td><td>

Passes the full path and filename of all selected items at once. The command will only be run once, no matter how many items are selected - the names of all selected items will be passed on the command line separated by spaces. You can use the **sep=** modifier (described below) to specify an alternative separator character.  
*Full paths, all at once, selected items not required, long filenames, source file display*
</td></tr><tr><td>
{allfilepath\$}</td><td>
{F}</td><td>

The "need" form of **{allfilepath}**.  
*Full paths, all at once, selected items required, long filenames, source file display*
</td></tr><tr><td>
{allfile}</td><td>
{O!}</td><td>
Passes the filename only of all selected items at once. File paths are not passed.  
Filenames only, all at once, selected items not required, long filenames, source file display
</td></tr><tr><td>
{allfile\$}</td><td>
{O}</td><td>

The "need" form of **{allfile}**.  
Filenames only, all at once, selected items required, long filenames, source file display
</td></tr><tr><td>
{filepathshort}</td><td>
{fs!}</td><td>

Passes the full path and filename of each selected item, in short (8.3) format. This is useful for running 16 bit programs or other legacy software that can't handle long filenames.  
*Full paths, one at a time, selected items not required, short filenames, source file display*
</td></tr><tr><td>
{filepathshort\$}</td><td>
{fs}</td><td>

The "need" form of **{filepathshort}**.  
*Full paths, one at a time, selected items required, short filenames, source file display*
</td></tr><tr><td>
{fileshort}</td><td>
{os!}</td><td>
Passes the filename only (no paths) of each selected item, in short (8.3) format.  
Filenames only, one at a time, selected items not required, short filenames, source file display
</td></tr><tr><td>
{fileshort\$}</td><td>
{os}</td><td>

The "need" form of **{fileshort}**.  
Filenames only, one at a time, selected items required, short filenames, source file display
</td></tr><tr><td>
{allfilepathshort}</td><td>
{Fs!}</td><td>

Passes the short (8.3) form of the full path and filename of all selected items at once.  
*Full paths, all at once, selected items not required, short filenames, source file display*
</td></tr><tr><td>
{allfilepathshort\$}</td><td>
{Fs}</td><td>

The "need" form of **{allfilepathshort}**.  
*Full paths, all at once, selected items required, short filenames, source file display*
</td></tr><tr><td>
{allfileshort}</td><td>
{Os!}</td><td>
Passes the filename only of all selected items at once, in short (8.3) format.  
Filenames only, all at once, selected items not required, short filenames, source file display
</td></tr><tr><td>
{allfileshort\$}</td><td>
{Os}</td><td>

The "need" form of **{allfileshort}**.  
Filenames only, all at once, selected items required, short filenames, source file display
</td></tr><tr><td>
{filepathdest}</td><td>
{fd!}</td><td>

Passes the full path and filename of each selected item in the destination file display. Files are passed one at a time - a command that uses this code will be repeated once for each additional selected item. If no files are selected in the destination, or there is currently no destination, the command will still be run, passing an empty string for this code.  
*Full paths, one at a time, selected items not required, long filenames, destination file display*
</td></tr><tr><td>
{filepathdest\$}</td><td>
{fd}</td><td>

The "need" form of **{filepathdest}**. If there are no files selected in the destination, or there is currently no destination, the command will not be executed.  
*Full paths, one at a time, selected items required, long filenames, destination file display*
</td></tr><tr><td>
{filedest}</td><td>
{od!}</td><td>
Passes the filename only of each selected item from the destination file display (without its path). Multiple files are passed one at a time.  
Filenames only, one at a time, selected items not required, long filenames, destination file display
</td></tr><tr><td>
{filedest\$}</td><td>
{od}</td><td>

The "need" form of **{filedest}**.  
Filenames only, one at a time, selected items required, long filenames, destination file display
</td></tr><tr><td>
{allfilepathdest}</td><td>
{Fd!}</td><td>

Passes the full path and filename of all selected items, from the destination file display, all at once. The command will only be run once, no matter how many items are selected - the names of all selected items will be passed on the command line separated by spaces.  
*Full paths, all at once, selected items not required, long filenames, destination file display*
</td></tr><tr><td>
{allfilepathdest\$}</td><td>
{Fd}</td><td>

The "need" form of **{allfilepathdest}**.  
*Full paths, all at once, selected items required, long filenames, destination file display*
</td></tr><tr><td>
{allfiledest}</td><td>
{Od!}</td><td>
Passes the filename only of all selected items at once, from the destination file display. File paths are not passed.  
Filenames only, all at once, selected items not required, long filenames, destination file display
</td></tr><tr><td>
{allfiledest\$}</td><td>
{Od}</td><td>

The "need" form of **{allfiledest}**.  
Filenames only, all at once, selected items required, long filenames, destination file display
</td></tr><tr><td>
{filepathshortdest}</td><td>
{fsd!}</td><td>

Passes the full path and filename of each selected item, in short (8.3) format, from the destination file display. This is useful for running 16 bit programs or other legacy software that can't handle long filenames.  
*Full paths, one at a time, selected items not required, short filenames, destination file display*
</td></tr><tr><td>
{filepathshortdest\$}</td><td>
{fsd}</td><td>

The "need" form of **{filepathshortdest}**.  
*Full paths, one at a time, selected items required, short filenames, destination file display*
</td></tr><tr><td>
{fileshortdest}</td><td>
{osd!}</td><td>
Passes the filename only (no paths) of each selected item in the destination file display, in short (8.3) format.  
Filenames only, one at a time, selected items not required, short filenames, destination file display
</td></tr><tr><td>
{fileshortdest\$}</td><td>
{osd}</td><td>

The "need" form of **{fileshortdest}**.  
Filenames only, one at a time, selected items required, short filenames, destination file display
</td></tr><tr><td>
{allfilepathshortdest}</td><td>
{Fsd!}</td><td>

Passes the short (8.3) form of the full path and filename of all selected items at once, from the destination file display.  
*Full paths, all at once, selected items not required, short filenames, destination file display*
</td></tr><tr><td>
{allfilepathshortdest\$}</td><td>
{Fsd}</td><td>

The "need" form of **{allfilepathshortdest}**.  
*Full paths, all at once, selected items required, short filenames, destination file display*
</td></tr><tr><td>
{allfileshortdest}</td><td>
{Osd!}</td><td>
Passes the filename only of all selected items at once, in short (8.3) format, from the destination file display.  
Filenames only, all at once, selected items not required, short filenames, destination file display
</td></tr><tr><td>
{allfileshortdest\$}</td><td>
{Osd}</td><td>

The "need" form of **{allfileshortdest}**.  
Filenames only, all at once, selected items required, short filenames, destination file display
</td></tr></tbody>
</table>

The filename codes all support the following modifiers. These can be added to the control code sequence using a vertical bar (**\|**) to separate the filename code from the modifier - for example, **{file\|noext}** strips the file extension from the returned filename. Multiple modifiers can be provided using additional vertical bars to separate them - for example **{file\|noext\|escwild}** combines both **noext** and **escwild** together.

<table>
<thead><tr><th>
Modifier</th><th>
Description
</th></tr></thead><tbody><tr><td>

**noext**</td><td>

Strips the filename extension from filenames. For example, if **{file}** returned *cat_photo.jpg* then **{file\|noext}** would return *cat_photo*. Note that if the item is a folder then its name will not be changed, even if it contains a dot, as folders are not considered to have file extensions.
</td></tr><tr><td>

**ext**</td><td>

Returns only the filename extension (the opposite of **noext**). For example, if **{file}** returned *cat_photo.jpg* then **{file\|ext}** would return *.jpg*. Note that if the item is a folder then nothing is returned, even the folder's name contains a dot.
</td></tr><tr><td>

**ext2**</td><td>

Returns the filename extension without the dot. For example, if **{file\|ext}** returned *.jpg* then **{file\|ext2}** would return *jpg*.
</td></tr><tr><td>

**ext=***\<ext\>*</td><td>

Replaces the original filename extension with the specified one. For example, **{file\|ext=tmp}** would return the name of each selected file with the extension changed to *.tmp*. Folder names are not changed, even if they contain dots.
</td></tr><tr><td>

**escbackslash**</td><td>

Automatically escapes any occurrences of **\\** in the filename, turning them into **\\**.  
This can be necessary when using codes like **{filepath}** to insert paths into strings which will have sequences like \n and \\ interpreted specially.  
For example, a command to add the selected file from the source and the selected file from the destination to the clipboard on separate lines:

**[Clipboard](../internal_commands/clipboard.md) EXPANDNEWLINES SET {filepath\|escbackslash}\n{filepathdest\|escbackslash}**.

In this example, if the source file was *C:\New Folder\test.txt* then it would be converted to *C:\\New Folder\\text.txt*. If the *\N* sequence had not been escaped, it would have removed the letter *N* from the path and put *ew Folder\text.txt* on a separate line. (There are more subtle cases when dealing with folder paths, but they are less important with file paths.)
</td></tr><tr><td>

**escforfilter**</td><td>

Intended for inserting paths into inline filter definitions.  
The same as **escbackslash** and **escwild** combined, but easier to remember and less to type.
</td></tr><tr><td>

**escnl**</td><td>

Automatically escapes any occurrences of **\n** in the filename, turning them into **\\n**.  
(This is a weaker version of **escbackslash**, above. You should probably use **escbackslash** instead.)  
Using **escnl** helps when using codes like **{filepath}** as the message text for a dialog code like **[{dlgstring}](codes_to_display_dialogs.md)**. For example, the path *C:\New Folder\test.txt* would be converted to *C:\\New Folder\test.txt*. If the *\N* sequence wasn't escaped, it would have been converted into a line-break in the dialog message text.
</td></tr><tr><td>

**escregex**  
**escregexp**</td><td>

Automatically escapes any regular expression characters in the filename. Used when passing filenames to internal commands that understand [regular expressions](../../wildcard_reference/regular_expression_syntax.md), in case a filename contains characters like **\\**, **.**, **(** and **)** which have special meaning to some functions. For example, **{file\|escregexp\|noext}** would turn *Accounts (2010).xls* into *Accounts \\2010\\*.  
For convenience, both the "regex" and "regexp" spellings are allowed and do the same thing.
</td></tr><tr><td>

**escwild**</td><td>

Automatically escapes any wildcard characters in the filename. Used when passing filenames to internal commands that understand [standard wildcards](../../wildcard_reference/pattern_matching_syntax.md), in case a filename contains characters like **(** and **)** which have special meaning to some functions. For example, **{file\|escwild\|noext}** would turn *Accounts (2010).xls* into *Accounts '(2010')*.
</td></tr><tr><td>

**file**</td><td>

Redirects the filenames to a temporary text file. This is useful with external programs that can accept a list of files from a text file rather than on the command line. (In turn, that is useful because command lines have a maximum length which may limit the number of filenames you can pass directly.) The name of the temporary file is passed on the command line in place of the filenames themselves. In the text file, each filename is separated by a space. If a filename or its path contains an embedded space it will be surrounded by quotes. For example, **{allfilepath\|file}**.
</td></tr><tr><td>

**filem**</td><td>

The same as **file** except that each filename is written to a separate line in the text file. For example, **{allfilepath\|filem}**.
</td></tr><tr><td>

**fileq**</td><td>

The same as **file** except that each filename is always surrounded by quotes, whether it contains an embedded space or not. For example, **{allfilepath\|fileq}**.
</td></tr><tr><td>

**filemq**</td><td>

The same as **filem** except that each filename is always surrounded by quotes. For example, **{allfilepath\|filemq}**.
</td></tr><tr><td>

**utf8**</td><td>

Forces the file written by **file**, **filem** or **fileq** to use UTF-8 format. For example, **{allfilepath\|filem\|utf8}**.
</td></tr><tr><td>

**ucsle**</td><td>

Forces the file written by **file**, **filem** or **fileq** to use UCS-16LE format. For example, **{allfilepath\|filem\|ucsle}**.
</td></tr><tr><td>

**ucsbe**</td><td>

Forces the file written by **file**, **filem** or **fileq** to use UCS-16BE format. For example, **{allfilepath\|filem\|ucsbe}**.
</td></tr><tr><td>

**urlencode**</td><td>

URL-encodes the filename it adds to the command line. Useful if you want to pass the filename to the Internet in some way. For example, you could have a context menu command which does an automatic Google search for the selected filename with: **[https://www.google.com/search?q={file\|urlencode](https://www.google.com/search?q=%7Bfile%7Curlencode)}**
</td></tr><tr><td>

**nobom**</td><td>

Prevents a BOM from being written that identifies the file type. For example, **{allfilepath\|filem\|utf8\|nobom}**.
</td></tr><tr><td>

**cronly**</td><td>

When used with **filem** or **filemq**, makes it so the file has only CR (carriage return) characters between each line. The default is CR,LF pairs as is standard on Windows. For example, **{allfilepath\|filem\|cronly}**.
</td></tr><tr><td>

**lfonly**</td><td>

When used with **filem** or **filemq**, makes it so the file has only LF (line feed) characters between each line. The default is CR,LF pairs as is standard on Windows. For example, **{allfilepath\|filem\|lfonly}**.
</td></tr><tr><td>

**nopath**</td><td>

Returns only the final component of the path. For example, if **{filepath}** returns *C:\Program Files\GPSoftware\Directory Opus\\*, **{filepath\|nopath}** would return *Directory Opus\\*. You would normally use something like **{file}** to get just the name of something, but using **{filepath\|nopath}** has the subtle difference of including the \\ on the end of the name when the item is a folder.
</td></tr><tr><td>

**noroot**</td><td>

Removes the root (i.e. the first component) from the file's path. For example, if **{filepath}** returns *C:\Windows\Notepad.exe*, **{filepath\|noroot}** would return *Windows\Notepad.exe*. With UNC network paths, the result is relative to the share, with the computer and share itself removed. With FTP paths, the result is relative to the site's root and excludes the site itself. You can combine **noroot** with **..** to get a parent path with the root removed. For example, **{filepath\|..\|noroot}**
</td></tr><tr><td>

**noshort**</td><td>

Suppresses automatic shortening of file paths which are longer than 260 characters. Opus itself can handle very long paths but many Windows programs cannot. When sending very long paths to external programs, Opus normally uses the short (8.3) versions to reduce problems. Use **noshort** to prevent this when you know the target program can cope. For example, **{filepath\|noshort}**.
</td></tr><tr><td>

**noterm**</td><td>

Removes the trailing path separator from folder paths. For example, **{filepath}** might return *C:\Program Files\\* whereas **{filepath\|noterm}** would return *C:\Program Files*.
</td></tr><tr><td>

**notermdrive**</td><td>

Similar to **noterm**, but also removes the trailing path separator when the resultant path is a drive root with no sub-directory. For example, both **{sourcepath}** and **{sourcepath\|noterm}** might return *C:\\* whereas *C:* would be returned by **{sourcepath\|notermdrive}**. Drive roots are a special case in Windows and generally require a trailing backslash, but there are exceptions (like the Windows **subst** command) where the backslash must be omitted.
</td></tr><tr><td>

**subdir**</td><td>

Replaces characters in the file's path so that the full path can be added below another path. For example, **{filepath\|subdir}** might return *C;\Windows\Notepad.exe*. Note that a semi-colon has replaced the colon, allowing the path to be used relative to another directory, say if you wanted to create a backup of the file called *D:\Backups\C;\Windows\Notepad.exe*.
</td></tr><tr><td>

**regex**</td><td>

Allows testing and manipulation of the filename.

|                                                     |                                                                                              |
|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| **{file\|regex=*\<pattern\>*)**                     | only process the file if the pattern matches; otherwise it will be skipped                   |
| **{file\|regex=*\<pattern\>*\|to=*\<new name\>*)**  | output the result of the regular expression search and replace (only if the pattern matches) |
| **{file\|regex!=*\<pattern\>*\|to=*\<new name\>*)** | as above, but if the pattern doesn't match it outputs the original filename unchanged        |

If your regular expression contains a \| symbol, you should enclose the whole pattern in quotes.
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

**sep=**</td><td>

Lets you specify an alternative separator for codes that insert multiple filenames on the one line. For example, **{allfilepath}** normally inserts all selected filepaths separated by spaces. You could use **{allfilepath\|sep=,}** to have the filepaths comma-separated instead.
</td></tr><tr><td>

**..**</td><td>

Modifies the code to refer to the selected item's parent folder rather than the item itself. You can pass multiple .. modifiers separated by **\\** to return folders higher up the tree. For example **{filepath\|..\\.}** would return the name of the item's parent's parent.
</td></tr><tr><td>

**\\**</td><td>

Modifies the code to refer to the root of the drive of the selected item. For example **{filepath\|\\** might return **C:\\**.
</td></tr><tr><td>

**driveletter**</td><td>

Modifies the code to refer to the drive letter, on its own, at the start of the selected item's path. For example **{filepath\|driveletter}** might return *C*. If the path is not relative to a drive letter, the whole path will be inserted as-is.  
You can also use **{filepath\|\\** to get something like *C:\\*, or **{filepath\|\\notermdrive}** to get something like *C:*, while handling non-drive roots (e.g. UNC paths) differently.
</td></tr><tr><td>

**drivelabel**</td><td>

Modifies the code to refer to the label for the drive letter at the start of the selected item's path. For example **{filepath\|drivelabel}** might return *System*. If the path is not relative to a drive letter, the whole path will be inserted as-is.
</td></tr></tbody>
</table>

In addition to the above codes, the following control codes are supported to provide compatibility with Windows Explorer. They can not be used in MS-DOS batch functions.

<table>
<thead><tr><th>
Modifier</th><th>
Equivalent To
</th></tr></thead><tbody><tr><td>

**%1**</td><td>
{filepath}
</td></tr><tr><td>

**%2**</td><td>
{filepath}
</td></tr><tr><td>

**%L**</td><td>
{filepath}
</td></tr><tr><td>

**%V**</td><td>
{filepath} if anything is selected; {sourcepath} otherwise
</td></tr><tr><td>

**%**\*</td><td>
{allfilepath}
</td></tr></tbody>
</table>

