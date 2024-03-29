# Rename Macro Language

Although you don’t need to understand the rename macro language (using the [macro builder](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.md) is much easier!), it’s described here for reference.

![](/Manual/images/media/image083.png)

The macro language describes one or more operations, each with a position relative to either the beginning or end of each filename. Above is a simple macro that removes 6 characters from the end of each name, and inserts the word “Final” at the start of each name.

The components of each macro expression are:

1.  **Anchor**: The first character of operation macro is either an **L** or an **R**, to indicate whether the position is relative (anchored) to the **l**eft or **r**ight of the filename.

1.  **Offset**: Next is the offset in characters from the anchor position.

1.  **Operation**: (Optional) <u>One</u> of the following operation characters can appear next.

      * **–** remove text

      * **C** copy text to clipboard

      * **X** cut text to clipboard

      * **V** paste clipboard contents

1.  **Length:** For\*\* –\*\* (remove), **C** (copy) and **X** (cut), the length in characters to cut, copy or remove is next. You can use \* for the length to signify to the end of each name (however long that is).

1.  **Insert**: (Optional) To insert characters at the current position in the name, use a **+** followed by the text to insert.

1.  **Separator**: If the macro contains additional operations they should be separated by a **/** character.

Using this information we can now decode the macros shown in the above example:

- **R0-6**: Right-anchor, 0 characters from the end of the filename, **remove** 6 characters.

- **L0+Final**: Left-anchor, 0 characters from the beginning of the filename, **insert** the word “Final”.

And here’s an example of this macro in action:

![](/Manual/images/media/image085.png)

As you can see, the suffix **\_draft** was removed from each filename (by the **R0-6** expression) and the prefix **Final** was inserted (by the **L0+Final** expression).

Let’s have a look at a more complicated macro example.

![](/Manual/images/media/image087.png)

Using the guide on the previous page, we can break this down and decode each component as follows:

- **R0-6**: Right-anchor, 0 characters from the end of the filename, **remove** 6 characters.

- **R0X2**: Right-anchor, 0 characters from the end, **cut** 2 characters to the clipboard.

- **R0-1**: Right-anchor, 0 characters from the end, **remove** 1 character.

- **R7V**: Right-anchor, 7 characters from the end, **paste** the clipboard contents.

- **R7+**.: Right-anchor, 7 characters from the end, **insert** a full-stop.

- **R0X2**: Right-anchor, 0 characters from the end, **cut** 2 characters to the clipboard.

- **R0-1**: Right-anchor, 0 characters from the end, **remove** 1 character.

- **R4V**: Right-anchor, 4 characters from the end, **paste** the clipboard contents.

- **R4+**.: Right-anchor, 4 characters from the end, **insert** a full-stop.

- **L0+Final**: Left-anchor, 0 characters from the beginning of the filename, **insert** the word “Final”.

As you can see, this macro makes use of the clipboard functionality of the macro language. Clipboard operations are performed on a per-filename basis – when it says “**cut** 2 characters to the clipboard”,  that means in each filename two characters – potentially different for each file – are cut to the clipboard. What this means of course is that you can move parts of filenames around using simple clipboard operations.

Here’s an example of this macro in use:

![](/Manual/images/media/image089.png)

Like the first example, the suffix **\_draft** was removed from each filename (by the **R0-6** expression) and the prefix **Final** was inserted (by the **L0+Final** expression). But as well as that, the date in each filename has been rearranged. Using multiple clipboard cut / insert steps, **2007-10-15** has been turned into **15.10.2007**.

 
