# Codes to display dialogs

The following codes can be used to display various simple dialogs when the command is run. This lets you provide information (like selecting a file or a folder, or entering a string) at "run-time" rather than incorporating the value into the command itself. For more flexibility, you can use a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md).

| Long form | Short form | Description |
| --- | --- | --- |
| {dlgopen} | {Rf} | Displays an **Open File** dialog, which lets you select an existing filename to pass to the command. |
| {dlgmulti} | {Rm} | Displays an **Open File** dialog in multiple selection mode, which lets you select one or more existing files. |
| {dlgsave} | {RF} | Displays a **Save File** dialog, which lets you enter a new filename to pass to the command. |
| {dlgfolder} | {Rd} | Displays a **Select Folder** dialog, which lets you select a folder to pass to the command. |
| {dlgstring} | {Rs} | Displays a dialog that lets you enter an arbitrary string. |
| {dlgstringS} | {RS} | The same as \<ib:inline-code\>`{dlgstring}`\</ib:inline-code\> except the contents of the string field are automatically selected (only applies if a default value is specified - see below). |
| {dlgpassword} | {Rp} | The same as \<ib:inline-code\>`{dlgstring}`\</ib:inline-code\> except the contents of the string field are obscured - useful for entering passwords. |
| {dlgchoose} | {Rc} | Displays a drop-down list that lets you choose from a list of values. |
| {dlgchooseS} | {RC} | The same as \<ib:inline-code\>`{dlgchoose}`\</ib:inline-code\> except the value list is automatically sorted. |

##### Parameters for {dlgopen}, {dlgmulti}, {dlgsize}

The template for these codes is \<ib:inline-code\>`{code|<title>|<default>}`\</ib:inline-code\>.

*\<title\>* specifies the title of the dialog box (a default title will be used if not provided), and *\<default\>* specifies the default filename.

For example, \<ib:inline-code\>`{dlgopen|Select filename|dopus.txt}`\</ib:inline-code\> would set the title to **Select filename** and the default filename to **dopus.txt**.

For \<ib:inline-code\>`{dlgopen}`\</ib:inline-code\> and \<ib:inline-code\>`{dlgmulti}`\</ib:inline-code\> you can specify a wildcard for *\<default\>* to set the filter type of the file dialog.

For example, \<ib:inline-code\>`{dlgopen||*.jpg;*.bmp;*.gif}`\</ib:inline-code\> would leave the dialog title as its default, and set the dialog to filter on **.jpg**, **.bmp** and **.gif** files.

For \<ib:inline-code\>`{dlgsave}`\</ib:inline-code\> you can specify an additional parameter to populate the "Save as Type" dropdown list in the save dialog.

For example, \<ib:inline-code\>`{dlgsave|Title|Default Name.txt|type=#Text Files!*.txt!Doc Files!*.doc}`\</ib:inline-code\>.

The \<ib:inline-code\>`#`\</ib:inline-code\> following the **type=** causes the default "All files" items to be added to the drop-down - take out the \<ib:inline-code\>`#`\</ib:inline-code\> if you don't want this.

Following that are one or more pairs of strings, separated by exclamation marks (\<ib:inline-code\>`!`\</ib:inline-code\>). The first string of each pair is the plain text string shown in the drop-down, and the second string of each pair is the actual file extension. You can also specify multiple extensions for the one type by separating them with semicolons - for example, \<ib:inline-code\>`type=JPEG Files!*.jpg;*.jpeg`\</ib:inline-code\>.

These codes also support the modifiers listed under [Codes for passing filenames](codes_for_passing_filenames.md). To use these modifiers, you must also include the *\<title\>* and *\<default\>* parameters (they can be left blank if desired).

For example \<ib:inline-code\>`{dlgopen|||noext}`\</ib:inline-code\> would strip the extension from the selected filename.

##### Parameters for {dlgfolder}

The template for this codes is \<ib:inline-code\>`{dlgfolder|<title>|<default>}`\</ib:inline-code\>.

*\<title\>* specifies the title of the dialog box (a default title will be used if not provided), and *\<default\>* specifies the default filename.

For example, \<ib:inline-code\>`{dlgfolder|Select folder|C:\Users}`\</ib:inline-code\> would set the title to **Select folder** and the initial selected folder would be **C:\Users**.

This code supports the modifiers listed under [Codes for passing paths](codes_for_passing_paths.md). To use these modifiers, you must also include the *\<title\>* and *\<default\>* parameters (they can be left blank if desired). An additional modifier, \<ib:inline-code\>`expand`\</ib:inline-code\>, is also supported. This causes the initially selected folder to be automatically expanded.

For example \<ib:inline-code\>`{dlgfolder||C:\Program Files|expand}`\</ib:inline-code\> would set **C:\Program Files** as the default folder and automatically expand it in the displayed dialog.

##### Parameters for {dlgstring}, {dlgstringS} and {dlgpassword}

The template for these codes is \<ib:inline-code\>`{code|<message>|<default>}`\</ib:inline-code\>.

*\<message\>* specifies the message displayed in the dialog box, and *\<default\>* specifies the default value of the string field.

You can include line-breaks in the message text using the special code \<ib:inline-code\>`\n`\</ib:inline-code\> (and if you need to include a literal \<ib:inline-code\>`\n`\</ib:inline-code\> sequence in the text you must escape the \<ib:inline-code\>`\`\</ib:inline-code\> character, as in \<ib:inline-code\>`\\`\</ib:inline-code\>).

![](/Manual/images/media/dlgstring.png)

For example, \<ib:inline-code\>`{dlgstring|Please enter the string.\nThen click OK.|default string}`\</ib:inline-code\>.

The optional \<ib:inline-code\>`doublequotes`\</ib:inline-code\> modifier can be used if you want any quote characters the user types to be doubled (\<ib:inline-code\>`"`\</ib:inline-code\> turns into \<ib:inline-code\>`""`\</ib:inline-code\>). This must follow the *\<default\>* parameter, which should be blank if it is not used. Doubling quotes allows quote characters the user types to be included inside command parameters, provided there are explicit quotes around parameter itself.

For example, \<ib:inline-code\>`SetAttr META "comment:{dlgstring|Enter Comment||doublequotes}"`\</ib:inline-code\>

Additionally, \<ib:inline-code\>`{dlgpassword}`\</ib:inline-code\> accepts an optional \<ib:inline-code\>`confirm`\</ib:inline-code\> modifier, which must also follow the *\<default\>* parameter. If this is specified, the dialog will display two password fields, and you must enter the same value in both fields (as a confirmation) before the OK button will be enabled.

For example, \<ib:inline-code\>`{dlgpassword|Please enter your password twice.||confirm}`\</ib:inline-code\>.

If both \<ib:inline-code\>`doublequotes`\</ib:inline-code\> and \<ib:inline-code\>`confirm`\</ib:inline-code\> are needed at once, they can be specified in any order.

For example, \<ib:inline-code\>`{dlgpassword|Please enter your password twice.||confirm|doublequotes}`\</ib:inline-code\>.

##### Parameters for {dlgchoose}, {dlgchooseS}

The template for these codes is \<ib:inline-code\>`{code|<message>|<option 1>[=<value 1>][+<option 2>[=<value 2>]...]}`\</ib:inline-code\>.

*\<message\>* specifies the message displayed in the dialog box. You can include line-breaks in the message text using the special code \<ib:inline-code\>`\n`\</ib:inline-code\> (and if you need to include a literal \<ib:inline-code\>`\n`\</ib:inline-code\> sequence in the text you must escape the \<ib:inline-code\>`\`\</ib:inline-code\> character, as in \<ib:inline-code\>`\\n`\</ib:inline-code\>.

*\<option 1\>* is the text displayed for the first option in the drop-down list, *\<option 2\>* is the second option, and so on. Multiple options are separated with a \<ib:inline-code\>`+`\</ib:inline-code\> sign.

*\<value 1\>* is an optional value associated with the first option. If provided, the *option* is displayed in the drop-down list, and the *value* is what is passed through on the command line. If *values* aren't provided, the *option* text is used for both.

You can specify the option which is selected by default by adding \<ib:inline-code\>`default:`\</ib:inline-code\> before it; otherwise, the first option (after sorting) will be the initial selection. You can also use the \<ib:inline-code\>`notdefault:`\</ib:inline-code\> prefix, which will simply be removed, if you need to use \<ib:inline-code\>`default:`\</ib:inline-code\> or \<ib:inline-code\>`notdefault:`\</ib:inline-code\> as a literal prefix.

![](/Manual/images/media/dlgchoose.png)

For example, \<ib:inline-code\>`{dlgchoose|Select encoding quality|default:High=320+Medium=256+Low=128}`\</ib:inline-code\> would add the options **High**, **Medium** and **Low** to the drop-down list, with **High** as the initial selection, and would pass one of the values **320**, **256** or **128** (respectively) through to the command line.

If you need to include a \<ib:inline-code\>`+`\</ib:inline-code\> or \<ib:inline-code\>`=`\</ib:inline-code\> character in either an option name or its value, you can do this by doubling the character up.
