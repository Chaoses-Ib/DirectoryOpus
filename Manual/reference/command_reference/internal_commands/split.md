# Split

The Split internal command can be used to:

- Split a file into two or more smaller parts
- UUEncode the split files for transmission via email/usenet

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

Displays the **[Split File](/Manual/additional_functionality/splitting_files.md)** dialog, which lets you split the selected files into parts of configurable size. The split files are written to the destination folder by default, and will have a numerical prefix appended to their names to indicate their order.

*Example:* `Split`
</td></tr><tr><td>
FROM</td><td>
/M</td><td>

*\<filename\>, ...*</td><td>

Specify the file or files to be split. If this argument is not provided, all selected files in the current source file display will be used. Remember to enclose the filename with quotes if it contains a space. This is the default argument for the **Split** command and so you don't need to specify the **FROM** keyword.

*Example:* `Split "C:\Video Files\Video.avi"`
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(no value)*</td><td>

Split files will be written to the current source folder instead of the destination folder.

*Example:* `Split HERE`
</td></tr><tr><td>
SIZE</td><td>
/K</td><td>

*\<part size\>*</td><td>

Specify the size of the split parts. This argument lets you automate the split function. The part size is given in bytes, kilobytes (if followed by the **KB** suffix), megabytes (if followed by the **MB** suffix) or gigabytes (if followed by the **GB** suffix).

*Example:* `Split HERE SIZE 1.44MB`
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<destination\>*</td><td>

Split files will be written to the specified folder instead of the current destination file display.

*Example:* `Split SIZE 1000000 TO C:\SplitOutput`
</td></tr><tr><td>
UUENCODE</td><td>
/S</td><td>

*(no value)*</td><td>

Uuencodes the output files. Uuencoding is sometimes used when transmitting files across UseNet or another communications medium that doesn't support 8-bit data.

*Example:* `Split SIZE 1MB UUENCODE`
</td></tr></tbody>
</table>

