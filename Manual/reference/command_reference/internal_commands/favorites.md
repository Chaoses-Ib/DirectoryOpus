# Favorites

The **Favorites** internal command can be used to:

- Display a dynamic list of your [Favorite folders](/Manual/basic_concepts/the_lister/navigation/favorites.md) (either all Favorites or a specific sub-branch)
- Display a dynamic list of your [SmartFavorite folders](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md)
- Add a folder to your Favorites
- Create a new [folder alias](/Manual/basic_concepts/the_lister/navigation/aliases.md)
- Edit your Favorite folders (by opening Preferences to the [Favorites List](/Manual/preferences/preferences_categories/frequently_used_paths/favorites_list.md) page)

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

Displays a dynamically generated list of your [favorite folders](/Manual/basic_concepts/the_lister/navigation/favorites.md) - you can navigate to a folder simply by selecting it from this list. Acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md).

Some of the arguments of this command can modify the appearance and behaviour of the dynamic list. Note the **PATH** argument lets you optionally specify a sub-branch of the Favorites list.

*Example:* `Favorites`
</td></tr><tr><td>
ADD</td><td>
/O</td><td>

*(no value)*</td><td>

Add the current source folder to your Favorites list. The entire path of the folder will be displayed in the Favorites list by default.

*Example:* `Favorites ADD`
</td></tr><tr><td>
</td><td>
</td><td>

**nameonly**</td><td>

Add the current source folder to your Favorites list, with the name of the favorite entry set to the name of the folder (so that only the name shows in the Favorites list, not the entire path).

*Example:* `Favorites ADD=nameonly`
</td></tr><tr><td>
</td><td>
</td><td>

**alias**</td><td>

Add or modify a folder alias instead of a favorite. You may use the **NAME** argument to specify the name of the alias, or omit it to automatically use the folder's name. You may use the **PATH** argument to specify the path the alias should point to, or omit it to automatically use the current path.

There are two alternative syntaxes for adding an alias. Using **ADD=alias** is the same as using **ALIAS=set**, other than the behavior of the **PATH** and **NAME** arguments as noted.

*Example:* `Favorites ADD=alias PATH "C:\Users\Jon\Documents"`
</td></tr><tr><td>
ADDDIALOG</td><td>
/S</td><td>

*(no value)*</td><td>

Display a dialog that lets you edit the name and path when adding a new favorite folder.

*Example:* `Favorites ADDDIALOG`
</td></tr><tr><td>
ALIAS</td><td>
/K</td><td>

**delete**</td><td>

Deletes a folder alias. The alias name must be given by the **NAME** argument, and is not optional.

*Example:* `Favorites ALIAS=delete NAME=MyAlias`
</td></tr><tr><td>
</td><td>
</td><td>

**set**</td><td>

Creates or modifies a folder alias. The alias name must be given by the **NAME** argument, and the path must be given by the **PATH** argument, with neither being optional.

*Example:* `Favorites ALIAS=set NAME=MyAlias PATH "C:\Users\Jon\Documents"`
</td></tr><tr><td>
</td><td>
</td><td>

**list**</td><td>

Generates a dynamic list of aliases, instead of the regular Favorite list. Use this if you want a menu of your aliases which (depending on other arguments) you can click on to go to them, copy files to them, and so on.  
By default only your user-defined aliases are shown; use the \*\*builtin \*\*or **all** keywords to override this.

*Example:* `Favorites ALIAS=list NOOPENINTABS SHOWICONS`
</td></tr><tr><td>
</td><td>
</td><td>

**builtin**</td><td>

Use in conjunction with the **list** keyword to only show the large list of built-in aliases (by default only user-defined aliases are included).

*Example:* `Favorites ALIAS=list,builtin SHOWICONS`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Use in conjunction with the **list** keyword to include both user-defined and built-in aliases in the list.

*Example:* `Favorites ALIAS=list,all`
</td></tr><tr><td>
AUTOCREATE</td><td>
/S</td><td>

*\<branch path\>*</td><td>

Automatically creates the branch specified by the **BRANCH** argument if it doesn't already exist. This is most commonly used by the Favorites Bar, in order to automatically create the appropriate branch of the favorites tree when the toolbar is opened.

*Example:* `FAVORITES BRANCH="Favorites Bar" AUTOCREATE`
</td></tr><tr><td>
BRANCH</td><td>
/K</td><td>

*\<branch path\>*</td><td>

Specifies a branch of the favorites tree to display, or when used with the **ADD** or **ADDDIALOG** arguments, the branch to add a new favorite to. To display the entire favorites tree or to add to the root of the favorites tree, omit the **BRANCH** argument entirely. Specify nested branches with a **\\** between each component, similar to a folder path.

If you specify a branch where some or all parts do not exist, when used with **ADD** or **ADDDIALOG** the missing parts will be created. When used to display the favorites list, you can specify the **AUTOCREATE** argument to automatically create the branch if it doesn't already exist.

When used with **ADDDIALOG**, the specified path will be selected by default but can then be changed when interacting with the dialog.

*Example:* `Favorites ADD BRANCH="Test Data\Photos"`
</td></tr><tr><td>
COPYTO</td><td>
/S</td><td>

*(no value)*</td><td>

Modifies the generated list of favorites, turning each item into a "copy" button that will copy selected files to the favorite folder.

*Example:* `Favorites COPYTO`
</td></tr><tr><td>
EDIT</td><td>
/S</td><td>

*(no value)*</td><td>

Display the **[Favorites List](/Manual/preferences/preferences_categories/frequently_used_paths/favorites_list.md)** page in Preferences.

*Example:* `Favorites EDIT`
</td></tr><tr><td>
EXCLUDEBRANCH</td><td>
/K</td><td>

*\<name or pattern\>*</td><td>

When displaying a list of Favorites, you can use the **EXCLUDEBRANCH** argument to exclude whole branches of the favorites tree from the generated list. You can specify the full branch path, or use a [wildcard](../../wildcard_reference/pattern_matching_syntax.md).

*Example:* `Favorites EXCLUDEBRANCH NetworkFaves`
</td></tr><tr><td>
FILTER</td><td>
/K</td><td>

*\<wildcard\>*</td><td>

When displaying a list of Favorites or [SmartFavorites](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md), you can use the **FILTER** argument to filter the list by path, using a [wildcard](../../wildcard_reference/pattern_matching_syntax.md). Paths which do not match the wildcard will be hidden from the generated list, and any sub-branches which become empty will also be pruned.

\`\`Favorites SHOWICONS FILTER C:\\\`\*  
// Shows only paths that begin with C:\\//

*Example:* `Favorites SHOWICONS FILTER "~(\*Program Files\*)"`  
// Shows only paths that do not contain Program Files.//

To filter the list by sub-branch rather than path, see the **PATH** argument instead.
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(no value)*</td><td>

When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.  
When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.

*Example:* `Favorites SMART HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

You can specify the heading text if you want it to be different to the button's label.

*Example:* `Favorites HEADING="Best Folders"`
</td></tr><tr><td>
KEYARGS</td><td>
/K/M</td><td>

*\<qualifier:arguments\> ...*</td><td>

When displaying a list of favorites, this argument lets you assign different behaviour to the items in the list if a qualifier key is held down. This is a multiple value argument - for each qualifier key combination listed, you can define a separate set of arguments that will be used when the item in the list is selected.

For example, you could configure your favorites menu to open favorite folders in a new tab by default, but in a new Lister if the <kbd>Ctrl</kbd> key were held down.

The qualifier part of the value consists of one or more keywords that represent the qualifier keys - **ctrl**, **shift** and **alt**. These can be combined, for example **ctrlshift** means that both the <kbd>Ctrl</kbd> and <kbd>Shift</kbd> keys must be held down. You can also use the keyword **none** to indicate arguments that are applied when no qualifiers are held.

*Example:* `Favorites KEYARGS "ctrl:NEW" "none:NEWTAB=findexisting"`
</td></tr><tr><td>
MENUMARKERS</td><td>
/S</td><td>

*(no value)*</td><td>

If the generated list of favorites includes any submenus, the top-level buttons will display a glyph indicating a dropdown menu.

*Example:* `Favorites MENUMARKERS`
</td></tr><tr><td>
MOVETO</td><td>
/S</td><td>

*(no value)*</td><td>

Modifies the generated list of favorites, turning each item into a "move" button that will move selected files to the favorite folder.

*Example:* `Favorites MOVETO`
</td></tr><tr><td>
MULTIFUNC</td><td>
/O</td><td>

*(no value)*</td><td>

The generated list of favorites will be [multiple function buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/multiple_function_buttons.md) (three-button buttons) - clicking them with the left mouse button will act as if **OPENINLEFT** were set, the right button will act as if **OPENINRIGHT** were set, and the middle mouse button will act as if **NEW** were set.

*Example:* `Favorites MULTIFUNC`
</td></tr><tr><td>
</td><td>
</td><td>

**tabs**</td><td>

Similar to the above except the left and right mouse button functions will open a new tab on the appropriate side of the Lister. You can control how new tabs are opened with the **NEWTAB** argument.

*Example:* `Favorites MULTIFUNC=tabs`
</td></tr><tr><td>
NAME</td><td>
/K</td><td>

*\<name\>*</td><td>

Specifies the name of the newly created favorite or alias. If a name is not provided, the name of the folder will be used by default.

*Example:* `Favorites ADD=alias NAME=docs PATH "C:\Users\Jon\Documents"`
</td></tr><tr><td>
NAMESONLY</td><td>
/S</td><td>

*(no value)*</td><td>

When listing Smart Favorites, each item in the list will only display its respective folder's name, not the full path. Full paths are displayed in tooltips instead.  
(The **NAMESONLY** argument does not work with the normal Favorites list, since you are free to edit item labels in that as you wish. See the **ADD=nameonly** argument, above, if you wish to automate suppression of full paths when adding normal favorites.)

*Example:* `Favorites SMART NAMESONLY`
</td></tr><tr><td>
NEW</td><td>
/S</td><td>

*(no value)*</td><td>

Favorites selected from the list generated by this command will open in a new Lister instead of the current one.

*Example:* `Favorites NEW`
</td></tr><tr><td>
NEWTAB</td><td>
/O</td><td>

*(no value)*</td><td>

Favorites selected from the list generated by this command will open in a [new tab](/Manual/basic_concepts/the_lister/tabs/README.md).

*Example:* `Favorites NEWTAB`
</td></tr><tr><td>
</td><td>
</td><td>

**deflister**</td><td>

If no lister exists, the Default Lister will open with an additional tab for the folder. If a lister exists, the folder will open normally in a new tab within the existing lister.

*Example:* `Favorites NEWTAB=deflister`
</td></tr><tr><td>
</td><td>
</td><td>

**findexisting**</td><td>

Look for the folder in an existing tab before opening a new one. If found, the existing tab will be brought to the front; otherwise a new tab will be opened. The active tab is checked first, and nothing will happen if the active tab already displays the selected path.

*Example:* `Favorites NEWTAB=findexisting`
</td></tr><tr><td>
</td><td>
</td><td>

**findinactive**</td><td>

Like **findexisting**, except that if the active tab already has the selected path then a new tab will be opened. Intended for buttons which switch to existing tabs to reduce clutter while retaining the ability to open a second tab for the same folder when needed.

*Example:* `Favorites NEWTAB=findinactive`
</td></tr><tr><td>
</td><td>
</td><td>

**nofocus**</td><td>

New tabs opened by favorites selected from the list will not be brought to the front.

*Example:* `Favorites NEWTAB=nofocus OPENINDUAL`
</td></tr><tr><td>
</td><td>
</td><td>

**tofront**</td><td>

If the folder was found in an existing tab, bring that tab to the front (only used with **findexisting**).

*Example:* `Favorites NEWTAB=findexisting,tofront`
</td></tr><tr><td>
NOLABELS</td><td>
/S</td><td>

*(no value)*</td><td>

The favorites list displayed by this command will not show any labels for the favorite folders. Only affects the top-level items; sub-menus will still display labels. Should be combined with **SHOWICONS**.

*Example:* `Favorites NOLABELS SHOWICONS`
</td></tr><tr><td>
NOOPENINTABS</td><td>
/S</td><td>

*(no value)*</td><td>

Do not add the **Open in tabs** command that is normally displayed at the bottom of the generated favorites list.

*Example:* `Favorites NOOPENINTABS`
</td></tr><tr><td>
OPENINDEST</td><td>
/S</td><td>

*(no value)*</td><td>

Favorites selected from the list will open in the destination file display or Lister.

*Example:* `Favorites OPENINDEST`
</td></tr><tr><td>
OPENINDUAL</td><td>
/S</td><td>

*(no value)*</td><td>

Favorites selected from the list will open in the other file display of a dual-display Lister. The Lister will be set to dual-display mode if it isn't in that mode already.

*Example:* `Favorites OPENINDUAL`
</td></tr><tr><td>
OPENINLEFT</td><td>
/S</td><td>

*(no value)*</td><td>

Favorites will open in the left-hand (or top) display of a dual-display Lister.

*Example:* `Favorites KEYARGS none:OPENINLEFT ctrl:OPENINRIGHT`
</td></tr><tr><td>
OPENINRIGHT</td><td>
/S</td><td>

*(no value)*</td><td>

Favorites will open in the right-hand (or bottom) display of a dual-display Lister.

*Example:* `Favorites NEWTAB OPENINRIGHT`
</td></tr><tr><td>
PATH</td><td>
</td><td>

*\<folder path\>*</td><td>

When used with the **ADD** argument, specifies the path to add as a favorite or alias. Without this, the current source folder will be used.

When used without the **ADD** argument, this modifies the dynamically generated list of favorite folders to only show the contents of a specified sub-branch of the favorites list. The branch path must be preceded with an asterisk. You can also use the **BRANCH** argument instead of this method - note that **BRANCH** does not require the asterisk in front of the branch path.

To filter the list by path rather than sub-branch, see the **FILTER** argument.

**PATH** is the default argument for the **Favorites** command; you do not need to specify the **PATH** keyword itself.

*Example:* `Favorites /desktop ADD`  
*Example:* `Favorites \*Projects` <nobr>(equivalent to `Favorites BRANCH=Projects`)</nobr>
</td></tr><tr><td>
SHOWICONS</td><td>
/S</td><td>

*(no value)*</td><td>

The favorites list displayed by this command will display icons for the items within it. Note that the button that contains the **Favorites** command must also have its **Show image** option turned on.

*Example:* `Favorites SHOWICONS`
</td></tr><tr><td>
SMART</td><td>
/O</td><td>

*(no value)*</td><td>

Generates a dynamic list of [SmartFavorites](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md) instead of the regular Favorite list. The number of folders displayed in the list is specified on the **[SmartFavorites](/Manual/preferences/preferences_categories/frequently_used_paths/smartfavorites.md)** Preferences page.

*Example:* `Favorites SMART`

Add the **NAMESONLY** argument to show only folder names instead of full paths, and move the full paths into tooltips.

*Example:* `Favorites SMART NAMESONLY`
</td></tr><tr><td>
</td><td>
</td><td>

*\<number of items\>*</td><td>

Display the specified number of SmartFavorites (overrides the number set in Preferences).

*Example:* `Favorites SMART 20 SHOWICONS NEWTAB`
</td></tr><tr><td>
</td><td>
</td><td>

**clear**</td><td>

Clears the SmartFavorites list, the same as clicking the option to do so within the Preferences dialog.

*Example:* `Favorites SMART=clear`
</td></tr><tr><td>
USEQUALKEYS</td><td>
/S</td><td>

*(no value)*</td><td>

Activates pre-configured behaviour for the main qualifier keys - **Control** will open the favorite folder in the dual-display, **Shift** in a new Lister and **Alt** in a new tab.

This is equivalent to <nobr>`Favorites KEYARGS ctrl:OPENINDUAL shift:NEW alt:NEWTAB`</nobr>.

*Example:* `Favorites USEQUALKEYS`
</td></tr></tbody>
</table>

