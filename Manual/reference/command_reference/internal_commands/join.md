# Join

The **Join** internal command can be used to join multiple files together into a single larger file. It is mainly used when you have a file that has been split into multiple parts, say for transmission via email.

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| \<nobr\>*(no argument)*\</nobr\> | - | - | Displays the **[Join Files](/Manual/additional_functionality/joining_files.md)** dialog. All currently selected files will be added to the list; you can re-order this list, remove items from it and add additional items to it from within the dialog.<br /><br />*Example:* `Join` |
| CONVERT | /K | uudecode | Specifies that joined files should be uudecoded.<br /><br />*Example:* `Join /temp/part1.uuenc.txt /temp/part2.uuenc.txt CONVERT=uudecode TO /temp/original.bin` |
|  |  | base64 | Joined files will be decoded using base64-encoding. |
|  |  | text | Files will be joined as text. Different encoding formats will be normalised to UTF-8. |
| FROM | /M | *\<filename\> ...* | Specify the files that will be joined. Remember to enclose each file in quotes if it contains spaces.<br /><br />*Example:* `Join /temp/part1.bin /temp/part2.bin` |
| HERE | /S | *(no value)* | Writes the joined file to the source folder instead of the destination.<br /><br />*Example:* `Join HERE` |
| TO | /K | *\<output file\>* | Specifies the name of the joined file.<br /><br />*Example:* `Join part1.bin part2.bin part3.bin TO original.jpg HERE` |

