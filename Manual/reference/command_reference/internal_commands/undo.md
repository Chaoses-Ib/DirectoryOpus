# Undo

The **Undo** internal command can be used to:

- Undo the last undoable file operation (undo delete to recycle bin, etc)
- Undo any one of the previous operations via a menu
- Display a list of undoable operations and undo all or individual operations

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| *(no argument)* | - | - | Undoes the most recent undoable file operation. Not all file operations are undoable - for example, files deleted from network or removable drives can not be undone.<br /><br />*Example:* `Undo` |
| HEADING | /O | *(no value)* | When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/RAEDME.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.<br /><br />When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.<br /><br />*Example:* `Undo LIST HEADING` |
|  |  | *\<heading text\>* | You can specify the heading text if you want it to be different to the button's label.<br /><br />*Example:* `Undo LIST HEADING="Undo List"` |
| ITEM | /K | *\<index\>* | Undoes the specified action from the undo list. The *\<index\>* indicates the operation to undo, as displayed in the undo list.<br /><br />*Example:* `Undo ITEM 3` |
| LIST | /O | *(no value)* | Displays a list of undoable actions (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/RAEDME.md)). Any operation from the list can be undone simply by selecting it from the list.<br /><br />*Example:* `Undo LIST` |
|  |  | **nokeys** | Disables the automatically-assigned hotkeys that are normally added to the generated list.<br /><br />*Example:* `Undo LIST=nokeys` |
|  |  | **menu** | Displays the undo list in a sub-menu.<br /><br />*Example:* `Undo LIST=menu,nokeys` |
| PAGE | /S | *(no value)* | Displays the *Undo Log* page of the [utility panel](/Manual/basic_concepts/the_lister/utility_panel.md). This displays a list of undoable actions, and lets you undo individual operations or all of them.<br /><br />*Example:* `Undo PAGE` |

