# Contents

This page lets you control which root (top level) items are shown in the folder tree, and the order they appear in.

- Use the checkboxes in the list to turn individual items on or off.
- Select an item and use the arrow buttons at the bottom-right of the list to change its position.

Some root items have specific options - these are shown on the right, below the **General options** section, when the item is selected.

Note that even if a folder is hidden from the tree, it will be displayed if you navigate to it or a folder underneath it. For example, if FTP sites are not shown normally in the tree, but you navigate to an FTP site, a temporary entry will be added to the tree as long as you are in the site - it will be removed again when you navigate away (subject to the **Remove dynamically added folders** option described below).

##### General options

These options apply to the tree in general, not to specific folders.

- **Show hidden folders**: Shows folders marked as hidden (the **H** attribute) in the tree (provided they are not filtered out globally.)
- **Show operating system folders**: Shows folders marked with both the **H** and **S** attributes (usually folders relating to Windows itself).
- **Show archives**: Archive files will be shown in the tree as if they were ordinary folders.
- **Show virtual (non-filesystem) folders**: If this option is off virtual folders will not be shown in the tree - for example, the *Recycle Bin* would be hidden by turning this option off.
- **Remove dynamically added folders**: Root folders that are added dynamically (to show a branch that is normally hidden) are removed again when you navigate away. When off, they stay until the window closes.

##### Display under the Desktop item

Many items have an option called **Display under the Desktop item**. If this is turned on, the item will be shown as a child of the *Desktop* folder. If turned off, the item will be at the root level.

##### Aliases options

- **Show built-in aliases**: All folder aliases, including the internal default aliases, will be shown. With this option turned off only user-defined aliases are shown.

##### Desktop options

- **Show extra folders**: By default, Opus filters out the plethora of random folders Windows 11 adds to the tree's Desktop branch. This option lets you turn them back on.

##### Favorites options

- **Display separators in favorites tree**: If your favorites list has separators between branches, these will be shown in the tree as well.
- **Merge Favorites and Smart Favorites**: Smart Favorites will be shown under the *Favorites* item, instead of (optionally) under their own item.

##### FTP options

- **Site roots always to go initial folder**: Changes what happens when you're already connected to an FTP site and then click its name in the folder tree again, for sites with an *initial folder* specified in their FTP Address Book entry.
  Whether this option is on or off, if you are not connected to an FTP site and click its name in the folder tree, you will connect to the site and navigate to its *initial folder* (if it has one). The option changes what happens if you then click the site again:

  - If the option is off (the default), you will go to the site's root folder.
  - If the option is on, you will go to the site's *initial folder*.

  The option only affects what happens when you click the site in the tree using the mouse; selection via the keyboard, and navigation via things other than the tree, are not affected.

##### Libraries options

- **Show member folders individually**: Individual member folders are listed in the tree under each library. For example, the *Pictures* library by default contains two members - your personal pictures folder, and the shared public pictures folder. If this option is on, the *Pictures* library will have both these members as separate folders beneath it, with their contents listed under them. If this option is off, the member folders are not shown individually, and the contents of the library are shown merged beneath the library itself.

##### Profile options

- **Use user name as label**: Instead of using the label *Profile*, the profile folder will show your Windows user name.

The list below this option lets you turn individual profile sub-directories on and off.

##### Smart Favorites options

- **Merge Favorites and Smart Favorites**: Smart Favorites will be shown under the *Favorites* item, instead of (optionally) under their own item.
- **Show full paths**: The full folder paths will be shown rather than just the folder name.

##### This PC options

- **Show empty disk drives**: Displays empty disk drives under the *This PC* folder. If turned off, empty removable drives will be hidden.
- **Show non-drive folders**: Displays any items under *This PC* that aren't drive letters.
