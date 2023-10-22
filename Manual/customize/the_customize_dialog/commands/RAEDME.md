# Commands

The Commands page displays a list of commands that you can easily add to toolbars by drag and drop. The commands are divided into a number of categories that loosely groups similar commands (often commands are grouped based on where they appear in [the default toolbars](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/RAEDME.md)).

- **[Edit](/Manual/customize/the_customize_dialog/commands/edit_category_pre-defined_commands.md)**: These are commands that normally appear in the Edit menu (copy, cut, paste, undo, etc.)
- **[File](/Manual/customize/the_customize_dialog/commands/file_category_pre-defined_commands.md)**: This category contains commands that normally appear in the File menu (new Lister, new tab, etc.)
- **[File Commands](/Manual/customize/the_customize_dialog/commands/file_commands_pre-defined_commands.md)**: These are commands that act on files and folders - normally found on the default Operations toolbar (copy file, create folder, delete, etc.)
- **[Go](/Manual/customize/the_customize_dialog/commands/go_category_pre-defined_commands.md)**: These are mostly commands relating to navigation, including FTP, favorites, etc. This category also contains a number of [field commands](../creating_your_own_buttons/editing_the_toolbar/field_buttons/RAEDME.md) that add location fields to the toolbar.
- **[Help](/Manual/customize/the_customize_dialog/commands/help_category_pre-defined_commands.md)**: This category contains commands that normally appear on the Help menu (about, help, etc.)
- **[Miscellaneous](/Manual/preferences/preferences_categories/miscellaneous/RAEDME.md)**: Miscellaneous commands that don't fit in any other category.
- **[New](/Manual/customize/the_customize_dialog/commands/new_category_pre-defined_commands.md)**: This category contains commands that let you create new, empty toolbar buttons and other elements.
- **[Settings](/Manual/customize/the_customize_dialog/commands/settings_category_pre-defined_commands.md)**: This contains commands relating to configuration (Preferences, Customize, etc.)
- **[Script Commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md)**: This contains any commands that have been added by a [Script add-in](/Manual/scripting/script_add-ins/RAEDME.md).
- **[Tools](/Manual/customize/the_customize_dialog/commands/tools_category_pre-defined_commands.md)**: Commands that normally appear in the Tools menu (find, synchronize, etc.)
- **[User-defined Commands](/Manual/customize/the_customize_dialog/commands/user-defined_commands.md)**: This category lists any [User commands](/Manual/customize/the_customize_dialog/commands/user-defined_commands.md) that you have created.
- **[View](/Manual/customize/the_customize_dialog/commands/view_category_pre-defined_commands.md)**: Contains commands that relate to the view and appearance of file displays (view mode, flat view, etc.)

Opus functions are built from a set of [internal commands](/Manual/reference/command_reference/internal_commands/RAEDME.md) (like a simple scripting language), and each command takes multiple parameters ("arguments") that control its behavior. While this can be very flexible it does require delving into the bowels of Opus somewhat, and so many common functions have been supplied in the list on this page as pre-defined commands.

The pre-defined commands have user-friendly names, and if you click on them a description of the command is displayed to the right of the page. To add one of the commands from this list to your toolbars, simply drag it from the list and drop it where you want it to go. When dropped on a toolbar they resolve to their underlying command and arguments in the button that's created, so if you [edit](../creating_your_own_buttons/editing_the_toolbar/RAEDME.md) one of these buttons after dropping it on a toolbar you can see what the "real" command is.

At the bottom of the Customize dialog (when it's showing the Commands page) is a field that lets you filter the commands list.

![](/Manual/images/media/command_filter.png) 

When you enter one or more keywords in the field and press the **Enter** key the list will be filtered to only show those commands whose name or description contains the keyword(s). This can make it very easy to find a pre-defined command when you remember its name but not what category it is in. To clear the filter either press **Escape** when the cursor is in the field, or click the little **X** button at the right-hand end of the field.

The category list on the Commands tab works the same as the similar list on the [Preferences](/Manual/preferences/RAEDME.md) dialog. You can use the keyboard to navigate it: **Cursor Up** / **Down** to move through the list, **Cursor Right** / **Left** to expand or collapse a category, \* to expand all categories and **-***twice* to collapse all categories.

The **Import User Command **and **Export User Command **commands in the *File* menu for this page let you import and export [user-defined commands](/Manual/customize/the_customize_dialog/commands/user-defined_commands.md).

More:

[Edit Category (Pre-defined commands)](/Manual/customize/the_customize_dialog/commands/edit_category_pre-defined_commands.md)  
[File Category (Pre-defined commands)](/Manual/customize/the_customize_dialog/commands/file_category_pre-defined_commands.md)  
[File Commands (Pre-defined commands)](/Manual/customize/the_customize_dialog/commands/file_commands_pre-defined_commands.md)  
[Go Category (Pre-defined commands)](/Manual/customize/the_customize_dialog/commands/go_category_pre-defined_commands.md)  
[Help Category (Pre-defined commands)](/Manual/customize/the_customize_dialog/commands/help_category_pre-defined_commands.md)  
[Miscellaneous Category (Pre-defined commands)](/Manual/customize/the_customize_dialog/commands/miscellaneous_category_pre-defined_commands.md)  
[New Category (Pre-defined commands)](/Manual/customize/the_customize_dialog/commands/new_category_pre-defined_commands.md)  
[Settings Category (Pre-defined commands)](/Manual/customize/the_customize_dialog/commands/settings_category_pre-defined_commands.md)  
[Tools Category (Pre-defined commands)](/Manual/customize/the_customize_dialog/commands/tools_category_pre-defined_commands.md)  
[User-defined Commands](/Manual/customize/the_customize_dialog/commands/user-defined_commands.md)  
[View Category (Pre-defined commands)](/Manual/customize/the_customize_dialog/commands/view_category_pre-defined_commands.md)  
