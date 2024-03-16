# Simple Wildcard Selection

The **Select Files** dialog has two modes; *simple* and *advanced*. It is accessed with the **Edit / Select by Pattern** command (or push <kbd>Ctrl+S</kbd>). The dialog remembers which mode it was last used in and will open in that mode the next time it is used; you can switch modes using the **Advanced** or **Simple** button at the bottom of the dialog.

![](/Manual/images/media/13/select_files_-_simple.png) 

The simple mode **Select Files** dialog lets you select files in the current file display by typing in a wildcard string using the [standard pattern matching syntax](/Manual/reference/wildcard_reference/pattern_matching_syntax.md). In the example shown above, the string `*.(mp3|m4a)` will select all files that end in either **.mp3** or **.m4a**, when you click the **OK** button.

The **Partial match** option enables partial matching of the string you enter - for example, `kit` would match **Cute Kitten.jpg** if that option was turned on.

Click the **Advanced** button to go to [advanced mode](advanced_selection.md), which lets you use more complex filters to select files.
