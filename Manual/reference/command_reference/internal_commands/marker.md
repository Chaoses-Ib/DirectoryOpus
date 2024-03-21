# Marker

The **Marker** internal command is used to display toolbar buttons and menu items that are added dynamically by third-party namespace extensions (it acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). For example, an FTP namespace extension may add buttons to the toolbar to switch between ASCII and binary transfer modes.

Explorer allows a third-party namespace extension to totally replace the toolbar and menu contents. However, Directory Opus gives full control to the user over the state of the toolbars, and therefore the **Marker** command is needed to mark the place where these commands are to appear.

The system that allows namespace extensions to add toolbar buttons has been deprecated by Microsoft in later versions of Windows, so these days this command is often not needed - however it remains for backwards compatibility reasons.

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| HEADING | /O | *(no value)* | When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.<br /><br />When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.<br /><br />*Example:* `Marker TOOLBAR` |
|  |  | *\<heading\>* | You can specify the heading text if you want it to be different to the button's label.<br /><br />*Example:* `Marker TOOLBAR HEADING="Extra Toolbar Commands"` |
| ID | /K/N | *\<id\>* | Send a namespace-specific command direct to the namespace folder currently displayed in the active Lister. You need to know the exact command ID that the namespace uses, which can be hard to determine. Ordinarily you will never use this option directly - Opus uses it when generating the dynamic buttons that are added by the **Marker** command.<br /><br />*Example:* `Marker ID 1002` |
| MENU | /K | *\<name\>* | Marks the spot where namespace-specific menu items will be displayed. The *name* parameter is a keyword corresponding to one of the standard Explorer menus (**file**, **edit**, **view**, **tools**, **help**), **other** (commands not fitting into any of those menus) and **all** (all namespace-specific menu items).<br /><br />*Example:* `Marker MENU=file` |
| TOOLBAR | /S | *(no value)* | Marks the spot where namespace-specific toolbar buttons are displayed.<br /><br />*Example:* `Marker TOOLBAR` |

