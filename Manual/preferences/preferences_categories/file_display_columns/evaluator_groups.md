# Evaluator Groups

This page lets you define *grouping schemes* that use the [evaluator](/Manual/evaluator/RAEDME.md) to control how files and folders are grouped (when [grouping](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md) is enabled in the file display).

The provided evaluator code will be invoked for each file and folder, to determine which group the item is placed in.

Grouping schemes are assigned on a per-column basis. When you create a scheme, you also decide which column or columns (if your scheme is generic enough) it applies to.

A grouping scheme can optionally replace the default grouping rules for a particular column. If additional schemes are created besides the default, they are shown in a sub-menu when choosing the column to group by.

![group_schemes.png](/Manual/images/media/13/group_schemes.png)

The default configuration defines five additional grouping schemes for the **Name** column, as an example.

Your configured schemes are shown in the list. Use the toolbar buttons above the list to add, edit or delete schemes. You can also use the share button to copy a scheme's definition to the clipboard, or paste one in.

Clicking the **Add** or **Edit** button displays the scheme editor.

##### Grouping scheme editor

![group_scheme_editor.png](/Manual/images/media/13/group_scheme_editor.png)

This example scheme groups items together based on the first letter of their filename.

The **Name** field defines a name for the scheme that can be used to activate it programmatically. For example, you could turn grouping on using this scheme with the command `Set GROUPBY=name GROUPSCHEME=first_letter`.

The **Description** is shown in the menu when selecting a column to group by.

The **Definition** tab is where the group scheme is defined.

##### Definition tab

Schemes can either use *static groups* or *dynamic groups*.

If the **Static groups** option is turned off, the evaluator code must return the name of the group to place each item in. In the example above, the evaluation code returns the first letter of the filename, converted to uppercase, as the group name. So all files that start with the same letter will end up in the same group. If the name doesn't begin with a letter or number, it returns an empty string - this means the item will be placed in the *Unspecified* group.

If the **Static groups** option is turned on, additional controls are shown which let you predefine the groups.

![group_scheme_editor_static.png](/Manual/images/media/13/group_scheme_editor_static.png)

Each group is numbered, and the evaluation clause must return the number of the group each item should be placed in (or `0` for *Unspecified*).

The evaluation clause is given a variable called `value` that provides the value being grouped for each file or folder. For example, if grouping by name, this will be the filename of each item.

The **Sort groups alphabetically** option controls the order that groups are ordered. If turned on, they'll be sorted alphabetically. If turned off, the evaluation clause can specify the order - see the [evaluator](/Manual/evaluator/applicable_contexts/evaluator_groups.md) section for more details on this and also what other variables are available to the evaluator in this context.

The **Reverse group order** option reverses the sort order of the groups.

##### Columns tab

This tab is where you specify which columns a scheme applies to. This affects what is shown in group menus (as shown in the screenshot above) - a scheme won't be offered there unless it's been associated with the column in question.

If your scheme is generic enough, you can add it to multiple columns (e.g. the first letter one above can really apply to any column).

Select the columns you want to apply your scheme to in the list on the left and click the <kbd>Right</kbd> button to move it into the selected list on the right.

Note that programmatically, you can apply any scheme when grouping - for example, the command \<nobr\>`Set GROUPBY=type GROUPSCHEME=first_letter`\</nobr\> would apply the "first letter" scheme to the type column, even though by default it's only associated with the name column.

See the section on the [evaluator](/Manual/evaluator/RAEDME.md) for more information about where you can use the evaluator.
