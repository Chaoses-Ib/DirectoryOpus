# Numbering Files

Using the **Sequential numbering** option in the Advanced Rename dialog, Opus can rename files with (or add to the existing name) an automatically incrementing number. You can specify the starting number, the number of digits (for zero-padding) and the incremental value. You can also specify the exact position in the new name where the number will appear.

![](/Manual/images/media/numbering_files.png)

In this example, we are tidying up the mixed-case names as well as renumbering the files. The special **\[#\]** code is used in the **New name** field to indicate where the number is to be inserted. The **Sequential numbering from** option specifies the starting number (in this case, 100) and the number of leading zeros lets you control zero padding. In this example, 0100 indicates that the number is to be padded to four digits.

Note that if you don't specify the **\[#\]** code, Opus will automatically insert the number at the end of the filename, before the file extension (so we could have left it out of the above example for the same results).
