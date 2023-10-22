# Split

The Split internal command can be used to:

- Split a file into two or more smaller parts
- UUEncode the split files for transmission via email/usenet

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| *(no argument)* | - | - | Displays the **[Split File](/Manual/additional_functionality/splitting_files.md)** dialog, which lets you split the selected files into parts of configurable size. The split files are written to the destination folder by default, and will have a numerical prefix appended to their names to indicate their order.<br /><br />*Example:* `Split` |
| FROM | /M | *\<filename\>, ...* | Specify the file or files to be split. If this argument is not provided, all selected files in the current source file display will be used. Remember to enclose the filename with quotes if it contains a space. This is the default argument for the **Split** command and so you don't need to specify the **FROM** keyword.<br /><br />*Example:* `Split "C:\Video Files\Video.avi"` |
| HERE | /S | *(no value)* | Split files will be written to the current source folder instead of the destination folder.<br /><br />*Example:* `Split HERE` |
| SIZE | /K | *\<part size\>* | Specify the size of the split parts. This argument lets you automate the split function. The part size is given in bytes, kilobytes (if followed by the **KB** suffix), megabytes (if followed by the **MB** suffix) or gigabytes (if followed by the **GB** suffix).<br /><br />*Example:* `Split HERE SIZE 1.44MB` |
| TO | /K | *\<destination\>* | Split files will be written to the specified folder instead of the current destination file display.<br /><br />*Example:* `Split SIZE 1000000 TO C:\SplitOutput` |
| UUENCODE | /S | *(no value)* | Uuencodes the output files. Uuencoding is sometimes used when transmitting files across UseNet or another communications medium that doesn't support 8-bit data.<br /><br />*Example:* `Split SIZE 1MB UUENCODE` |

