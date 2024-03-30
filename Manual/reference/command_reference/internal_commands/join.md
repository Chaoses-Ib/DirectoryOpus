# Join

The **Join** internal command can be used to join multiple files together into a single larger file. It is mainly used when you have a file that has been split into multiple parts, say for transmission via email.

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>

\<nobr\>*(no argument)*\</nobr\></td><td>
-</td><td>
-</td><td>

Displays the **[Join Files](/Manual/additional_functionality/joining_files.md)** dialog. All currently selected files will be added to the list; you can re-order this list, remove items from it and add additional items to it from within the dialog.

*Example:* `Join`
</td></tr><tr><td>
CONVERT</td><td>
/K</td><td>
uudecode</td><td>

Specifies that joined files should be uudecoded.

*Example:* `Join /temp/part1.uuenc.txt /temp/part2.uuenc.txt CONVERT=uudecode TO /temp/original.bin`
</td></tr><tr><td>
</td><td>
</td><td>
base64</td><td>
Joined files will be decoded using base64-encoding.
</td></tr><tr><td>
</td><td>
</td><td>
text</td><td>
Files will be joined as text. Different encoding formats will be normalised to UTF-8.
</td></tr><tr><td>
FROM</td><td>
/M</td><td>

*\<filename\> ...*</td><td>

Specify the files that will be joined. Remember to enclose each file in quotes if it contains spaces.

*Example:* `Join /temp/part1.bin /temp/part2.bin`
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(no value)*</td><td>

Writes the joined file to the source folder instead of the destination.

*Example:* `Join HERE`
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<output file\>*</td><td>

Specifies the name of the joined file.

*Example:* `Join part1.bin part2.bin part3.bin TO original.jpg HERE`
</td></tr></tbody>
</table>

