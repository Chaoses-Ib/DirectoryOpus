# Control Keys

This page lets you configure control keys that select or modify parts of the filename when using [inline rename](/Manual/file_operations/renaming_files/inline_rename.md) (and in most other places where filenames can be edited).

Keypresses can trigger several types of action:

- They can select a part of the filename using a [regular expression](/Manual/reference/wildcard_reference/regular_expression_syntax.md)
- They can run a [rename preset](/Manual/file_operations/renaming_files/advanced_rename/rename_presets.md)
- They can run [evaluator](/Manual/evaluator/RAEDME.md) code that can modify the name, select part of the filename and/or position the cursor

A number of keys are defined by default, and you can examine them to see how they're configured. For example, the <kbd>Ctrl+A</kbd> key to select the entire contents of the edit field is defined as a simple regular expression that matches the entire string.

##### Control key list

The top half of this page displays a list of defined keys.

- Use the ![](/Manual/images/media/13/button_add.png) **Add** and ![](/Manual/images/media/13/button_delete.png) **Delete** buttons to add or remove control keys.
- The ![](/Manual/images/media/13/button_share.png) **Share** button lets you share a control key's definition with other people
- The ![](/Manual/images/media/13/button_paste.png) **Paste** button lets you paste a new control key in from the clipboard

When you select a key from the list, the bottom half of the page displays its configuration.

##### Control key configuration

- **Name**: Defines a name for the control key, to be shown in the list.
- **Key**: The key itself. This is the key you'll need to press in the edit field to activate the action.
- **Type**: The action type. The various action types are described below.

##### Type: Select via RegEx Match

This action type lets you select a part of the filename using a regular expression. The pattern should include a capture group. The pattern is compared to the entire filename, and if it matches, the portion corresponding to the capture group will be selected.

For example, say you want a key to automatically select the prefix `Copy X of` where X is a number. You could use the regular expression \<nobr\>`(Copy \d of ).*`\</nobr\>. Pressing the associated control key would automatically select the matching prefix.

##### Type: Select via RegEx Search

In contrast to **Select via RegEx Match**, this action performs a *search* on the filename using the provided regular expression. This means that the pattern may match multiple times within the filename. The selection will be moved from one match to the next every time you press the key.

The default **Select words** preset is an example of this. It uses the pattern \<nobr\>`[^\s\.]+`\</nobr\> which basically means "match all characters up to a space or a fullstop". Pressing <kbd>Ctrl+S</kbd> once will select the first word, pressing it again will select the second, and so on.

##### Type: Modify via Rename Preset

This type lets you select one of your [rename presets](/Manual/file_operations/renaming_files/advanced_rename/rename_presets.md) to apply to the filename when the key is pressed. Note that the name in the edit field will be updated but the file itself is not renamed until you press <kbd>Enter</kbd> as normal (i.e. the rename preset is applied to the text in the field, not the file itself).

##### Type: Modify via Evaluator Clause

This type lets you use an [evaluator clause](/Manual/evaluator/RAEDME.md) to change the selection (or position the cursor) and/or modify the contents of the edit field.

The evaluator clause is given variables which tell it the original name, the current value in the field, the type (file or directory), the file's path, and the current selection range.

- It can return a string, which changes the contents of the control.
- It can modify the `selstart` and `selend` variables to change the selection.

See [Rename Control Keys](/Manual/evaluator/applicable_contexts/rename_control_keys.md) in the Evaluator Reference section for full details.

##### Testing your control key

At the bottom of the dialog are two text fields, which let you test the results of the selected control key. In the **Test name** field, you should type or paste an example filename that you want to test against. The results of the test are shown in the **Result** field below.
