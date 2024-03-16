# Numbering Files

Using the **Numbering** option in the Advanced Rename dialog, Opus can rename files with (or add to the existing name) an automatically incrementing number. You can specify the starting number, the number of digits (for zero-padding) and the incremental value. You can also specify the exact position in the new name where the number will appear.

![](/Manual/images/media/13/numbering_files.png)

In this example, we're tidying up the mixed-case names as well as renumbering the files. The special \<ib:inline-code\>`[#]`\</ib:inline-code\> code is used in the **New name** field to indicate where the number is to be inserted. The **Numbering from** option specifies the starting number (in this case, 100) and the number of leading zeros lets you control zero padding. In this example, \<ib:inline-code\>`0100`\</ib:inline-code\> indicates that the number is to be padded to four digits.

Note that if you don't specify the \<ib:inline-code\>`[#]`\</ib:inline-code\> code, Opus will automatically insert the number at the end of the filename, before the file extension (so we could have left it out of the above example for the same results).
