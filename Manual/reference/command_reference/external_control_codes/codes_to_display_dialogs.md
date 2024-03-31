# Codes to display dialogs

The following codes can be used to display various simple dialogs when the command is run. This lets you provide information (like selecting a file or a folder, or entering a string) at "run-time" rather than incorporating the value into the command itself. For more flexibility, you can use a [script dialog](/Manual/scripting/script_dialogs/README.md).

<table>
<thead><tr><th>
Long form</th><th>
Short form</th><th>
Description
</th></tr></thead><tbody><tr><td>
{dlgopen}</td><td>
{Rf}</td><td>

Displays an **Open File** dialog, which lets you select an existing filename to pass to the command.
</td></tr><tr><td>
{dlgmulti}</td><td>
{Rm}</td><td>

Displays an **Open File** dialog in multiple selection mode, which lets you select one or more existing files.
</td></tr><tr><td>
{dlgsave}</td><td>
{RF}</td><td>

Displays a **Save File** dialog, which lets you enter a new filename to pass to the command.
</td></tr><tr><td>
{dlgfolder}</td><td>
{Rd}</td><td>

Displays a **Select Folder** dialog, which lets you select a folder to pass to the command.
</td></tr><tr><td>
{dlgstring}</td><td>
{Rs}</td><td>
Displays a dialog that lets you enter an arbitrary string.
</td></tr><tr><td>
{dlgstringS}</td><td>
{RS}</td><td>

The same as `{dlgstring}` except the contents of the string field are automatically selected (only applies if a default value is specified - see below).
</td></tr><tr><td>
{dlgpassword}</td><td>
{Rp}</td><td>

The same as `{dlgstring}` except the contents of the string field are obscured - useful for entering passwords.
</td></tr><tr><td>
{dlgchoose}</td><td>
{Rc}</td><td>
Displays a drop-down list that lets you choose from a list of values.
</td></tr><tr><td>
{dlgchooseS}</td><td>
{RC}</td><td>

The same as `{dlgchoose}` except the value list is automatically sorted.
</td></tr></tbody>
</table>

### Parameters for {dlgopen}, {dlgmulti}, {dlgsize}

The template for these codes is `{code|<title>|<default>}`.

*\<title\>* specifies the title of the dialog box (a default title will be used if not provided), and *\<default\>* specifies the default filename.

For example, `{dlgopen|Select filename|dopus.txt}` would set the title to **Select filename** and the default filename to **dopus.txt**.

For `{dlgopen}` and `{dlgmulti}` you can specify a wildcard for *\<default\>* to set the filter type of the file dialog.

For example, `{dlgopen||*.jpg;*.bmp;*.gif}` would leave the dialog title as its default, and set the dialog to filter on **.jpg**, **.bmp** and **.gif** files.

For `{dlgsave}` you can specify an additional parameter to populate the "Save as Type" dropdown list in the save dialog.

For example, `{dlgsave|Title|Default Name.txt|type=#Text Files!*.txt!Doc Files!*.doc}`.

The `#` following the **type=** causes the default "All files" items to be added to the drop-down - take out the `#` if you don't want this.

Following that are one or more pairs of strings, separated by exclamation marks (`!`). The first string of each pair is the plain text string shown in the drop-down, and the second string of each pair is the actual file extension. You can also specify multiple extensions for the one type by separating them with semicolons - for example, `type=JPEG Files!*.jpg;*.jpeg`.

These codes also support the modifiers listed under [Codes for passing filenames](codes_for_passing_filenames.md). To use these modifiers, you must also include the *\<title\>* and *\<default\>* parameters (they can be left blank if desired).

For example `{dlgopen|||noext}` would strip the extension from the selected filename.

### Parameters for {dlgfolder}

The template for this codes is `{dlgfolder|<title>|<default>}`.

*\<title\>* specifies the title of the dialog box (a default title will be used if not provided), and *\<default\>* specifies the default filename.

For example, `{dlgfolder|Select folder|C:\Users}` would set the title to **Select folder** and the initial selected folder would be **C:\Users**.

This code supports the modifiers listed under [Codes for passing paths](codes_for_passing_paths.md). To use these modifiers, you must also include the *\<title\>* and *\<default\>* parameters (they can be left blank if desired). An additional modifier, `expand`, is also supported. This causes the initially selected folder to be automatically expanded.

For example `{dlgfolder||C:\Program Files|expand}` would set **C:\Program Files** as the default folder and automatically expand it in the displayed dialog.

### Parameters for {dlgstring}, {dlgstringS} and {dlgpassword}

The template for these codes is `{code|<message>|<default>}`.

*\<message\>* specifies the message displayed in the dialog box, and *\<default\>* specifies the default value of the string field.

You can include line-breaks in the message text using the special code `\n` (and if you need to include a literal `\n` sequence in the text you must escape the `\` character, as in `\\`).

![](/Manual/images/media/dlgstring.png)

For example, `{dlgstring|Please enter the string.\nThen click OK.|default string}`.

The optional `doublequotes` modifier can be used if you want any quote characters the user types to be doubled (`"` turns into `""`). This must follow the *\<default\>* parameter, which should be blank if it is not used. Doubling quotes allows quote characters the user types to be included inside command parameters, provided there are explicit quotes around parameter itself.

For example, `SetAttr META "comment:{dlgstring|Enter Comment||doublequotes}"`

Additionally, `{dlgpassword}` accepts an optional `confirm` modifier, which must also follow the *\<default\>* parameter. If this is specified, the dialog will display two password fields, and you must enter the same value in both fields (as a confirmation) before the OK button will be enabled.

For example, `{dlgpassword|Please enter your password twice.||confirm}`.

If both `doublequotes` and `confirm` are needed at once, they can be specified in any order.

For example, `{dlgpassword|Please enter your password twice.||confirm|doublequotes}`.

### Parameters for {dlgchoose}, {dlgchooseS}

The template for these codes is `{code|<message>|<option 1>[=<value 1>][+<option 2>[=<value 2>]...]}`.

*\<message\>* specifies the message displayed in the dialog box. You can include line-breaks in the message text using the special code `\n` (and if you need to include a literal `\n` sequence in the text you must escape the `\` character, as in `\\n`.

*\<option 1\>* is the text displayed for the first option in the drop-down list, *\<option 2\>* is the second option, and so on. Multiple options are separated with a `+` sign.

*\<value 1\>* is an optional value associated with the first option. If provided, the *option* is displayed in the drop-down list, and the *value* is what is passed through on the command line. If *values* aren't provided, the *option* text is used for both.

You can specify the option which is selected by default by adding `default:` before it; otherwise, the first option (after sorting) will be the initial selection. You can also use the `notdefault:` prefix, which will simply be removed, if you need to use `default:` or `notdefault:` as a literal prefix.

![](/Manual/images/media/dlgchoose.png)

For example, `{dlgchoose|Select encoding quality|default:High=320+Medium=256+Low=128}` would add the options **High**, **Medium** and **Low** to the drop-down list, with **High** as the initial selection, and would pass one of the values **320**, **256** or **128** (respectively) through to the command line.

If you need to include a `+` or `=` character in either an option name or its value, you can do this by doubling the character up.
