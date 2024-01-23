# Codes for clipboard and variables

The **{clip}** code allow you to pass the contents of the clipboard to an external program.

The **{dpi}** code lets you use DPI related information.

The **{\$}** code lets you insert the value of a variable that you have previously set with the **@set** [command modifier](/Manual/customize/creating_your_own_buttons/command_modifiers.md).

| Long form | Short form | Description |
| --- | --- | --- |
| {clip} | {c} | Passes the contents of the clipboard (only if the clipboard contains text data).  <br />If the clipboard text is to be used as a filename or path, you can ask Opus to sanitize it:<br /><br />- **{clip\|cleanfilename}**  <br />  Replaces any illegal filename characters in the string, and also replaces all path separators and colons, so the string can be used as a filename without it adding any additional path levels.  <br />  Example: *C:\Users\Leo\\Hello.txt"* becomes *C;\_Users_Leo\_'Hello.txt'*  <br />  Note that the colon became a semicolon, the double quotes became single quotes, and the backslashes became underscores.<br />- **{clip\|cleanfilepath}**  <br />  Replaces any illegal filename characters in the string, while leaving path separators and colons. (Colons are only left in if they are part of a drive letter at the start of the string.) Should be used when the string can be an absolute path.  <br />  Example: *C:\Users\Leo\\Hello.txt"* becomes *C:\Users\Leo\\Hello.txt'*<br />- **{clip\|cleanfilepathrel}**  <br />  Replaces any illegal filename characters in the string, also replacing colons and "\\" UNC path initiators, so the string can be used as a subdirectory under another path.  <br />  Example: *C:\Users\Leo\\Hello.txt"* becomes *C;\Users\Leo\\Hello.txt'* |
| {dpi} | - | The **{dpi}** control code lets you use DPI-sensitive values with simple commands. This can be useful if you have buttons which specify column or window sizes and you want consistent results from the same button in different DPIs.<br /><br />- **{dpi}** on its own will insert the current DPI. **96** at standard DPI, **192** at 200% DPI, and so on.<br />- **{dpi\|%}** will report the insert DPI scale factor. **100** at standard DPI, **200** at 200% DPI, and so on.<br />- **{dpi\|\<number\>}** will convert a standard 96 DPI pixel width to the current DPI. For example, if you are at 200% DPI, **{dpi\|25}** will output **50**.<br />- **{dpi\|/\<number\>}** will convert from the current DPI back to standard 96 DPI pixels. For example, if you are at 200% DPI, **{dpi\|/50}** will output **25**. |
| {\$*\<variable\>*} | - | Inserts the value of the named variable. This must have been previously set using the **@set** modifier.<br /><br />The **@set** modifier can be used to assign the value of another external code to a variable. For example, if you want to ask the user to enter a string with the **{dlgstring}** code, you could assign that to a variable which would then let you use that string more than once in the function:<br /><br />    @set name {dlgstring|Enter new folder name}<br />    CreateFolder "{$name}"<br />    Go "{$name}" NEWTAB<br /><br />The **FileType NEW** command automatically sets a value called **newfile** to the name of the newly created file. |
| {=*\<eval\>*=} | - | Inserts the value of an [evaluator](evaluator/RAEDME.md) clause. |
