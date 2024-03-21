# Evaluator Columns

This page lets you create your own columns which can use the [evaluator](/Manual/evaluator/README.md) to manipulate the filename or other metadata to produce the text they display.

For example, you could use the evaluator's [RegEx()](/Manual/reference/evaluator/regex.md) function to extract a portion of the filename and display it in a separate column.

Your configured columns are shown in the list. Use the toolbar buttons above the list to add, edit or delete columns. You can also use the share button to copy a column's definition to the clipboard, or paste one in.

At the bottom is a field labelled **Example file**. This lets you select a file which will then be fed to all the defined columns in the list, to populate the **Example** column. This lets you see how your columns work in real-time.

Clicking the **Add** or **Edit** button displays the column editor.

##### Column editor

![evalcolumn_editor.png](/Manual/images/media/13/evalcolumn_editor.png)

The image above shows the definition for the default **Image Bytes** column, one of the built-in example evaluator columns.

- **Title**: Defines the title of your column. This is shown in column lists throughout Opus.
- **Header title**: Lets you provide an optional title that's used in the column header in the Lister. If you leave this empty the **Title** is used instead.
- **Keyword**: Defines a keyword that lets your column be controlled programmatically. All evaluation column keywords begin with the prefix `eval:`, followed by the specified keyword. For example, the above column could be turned on using the command \<nobr\>`Set COLUMNSTOGGLE=eval:imagebytes`\</nobr\>.
- **Evaluator code**: This is where you enter the evaluator code that produces the column content. See the [Evaluator](/Manual/evaluator/applicable_contexts/evaluator_columns.md) section for more details.
- **Type**: The type of the column determines how it displays the content that your code produces.
  ^Type^Description^

  |           |                                                                                                |
  |-----------|------------------------------------------------------------------------------------------------|
  | Date      | Displays the provided value as a date using the current locale settings.                       |
  | Date/Time | Displays it as a date and time using the current locale settings.                              |
  | Double    | Displays a double-precision number. The number of decimal places will be limited.              |
  | Graph     | Displays the value as a graph (expects a value from 0 to 100).                                 |
  | Percent   | Displays the value as a percentage.                                                            |
  | Rating    | Displays the value as one or more stars. The maximum number of stars is configured separately. |
  | Signed    | Displays a signed value.                                                                       |
  | Size      | Displays the value as a file size, with an appropriate suffix.                                 |
  | Text      | Displays plain text.                                                                           |
  | Time      | Displays the value as a time using the current locale settings.                                |
  | Unsigned  | Displays an unsigned value.                                                                    |

- **Graph color**: When the type is set to *Graph*, this lets you configure the "fill" color for the graph.
- **Max stars**: When the type is set to *Rating*, this lets you configure the maximum number of stars in the column.
- **Category**: Defines the category that the column will appear in in column lists.
- **Alignment**: Defines the column alignment (left, right, or centered).
- **Default width**: An optional default width for the column, which can be specified either in pixels or characters.
- **Reverse sort by default**: Turn this on for columns like date fields where you want to reverse the normal sort order by default (so that e.g. the newest files are at the top instead of the bottom.)
- **Refresh if file changes**: If turned on, Opus will regenerate your column's content for a given file if it detects that the file has changed. The **Include attributes** option makes this happen if the only change is to the file attributes, rather than its size or datestamp.
- **Refresh if name changes**: If a file is renamed, Opus will regenerate your column's content if this option is turned on. You'd want this for any evaluator column that was based on the filename.
- **Filesystem folders only**: If turned on this column will only be available in normal filesystem folders (e.g. C:) and not in locations such as FTP sites or archives. You'd want this option on if your column depends on metadata that's only available for real files.
- **Custom grouping**: If turned on, the evaluation clause will be called separately with the variable `operation` set to the value `"group"`. This lets you return the name of the group you want the item placed into by default.

See the section on the [Evaluator](/Manual/evaluator/README.md) for more information about where you can use the evaluator.
