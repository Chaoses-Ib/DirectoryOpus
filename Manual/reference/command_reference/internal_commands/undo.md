# Undo

The **Undo** internal command can be used to:

- Undo the last undoable file operation (undo delete to recycle bin, etc)
- Undo any one of the previous operations via a menu
- Display a list of undoable operations and undo all or individual operations

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>

*(no argument)*</td><td>
-</td><td>
-</td><td>

Undoes the most recent undoable file operation. Not all file operations are undoable - for example, files deleted from network or removable drives can not be undone.

*Example:* `Undo`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(no value)*</td><td>

When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.

When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.

*Example:* `Undo LIST HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

You can specify the heading text if you want it to be different to the button's label.

*Example:* `Undo LIST HEADING="Undo List"`
</td></tr><tr><td>
ITEM</td><td>
/K</td><td>

*\<index\>*</td><td>

Undoes the specified action from the undo list. The *\<index\>* indicates the operation to undo, as displayed in the undo list.

*Example:* `Undo ITEM 3`
</td></tr><tr><td>
LIST</td><td>
/O</td><td>

*(no value)*</td><td>

Displays a list of undoable actions (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Any operation from the list can be undone simply by selecting it from the list.

*Example:* `Undo LIST`
</td></tr><tr><td>
</td><td>
</td><td>

**nokeys**</td><td>

Disables the automatically-assigned hotkeys that are normally added to the generated list.

*Example:* `Undo LIST=nokeys`
</td></tr><tr><td>
</td><td>
</td><td>

**menu**</td><td>

Displays the undo list in a sub-menu.

*Example:* `Undo LIST=menu,nokeys`
</td></tr><tr><td>
PAGE</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the *Undo Log* page of the [utility panel](/Manual/basic_concepts/the_lister/utility_panel.md). This displays a list of undoable actions, and lets you undo individual operations or all of them.

*Example:* `Undo PAGE`
</td></tr></tbody>
</table>

