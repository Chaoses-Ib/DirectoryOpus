# Flat View

Flat View is a mode you can turn on in a Lister that enables you to view all the contents of a folder's sub-folders at once. In effect it collapses, or flattens, the display of a nested hierarchy of folders and files into a single folder.

If you want to be able to control which folders are expanded, [expandable folders](expandable_folders.md) may be a better choice. Flat View is similar to expandable folders, except it expands **everything** automatically.

### Turning on Flat View

You can turn Flat View on using the ![](/Manual/images/media/13/flatviewbutton.png) button on the default toolbar - right-click the button to see a menu of the different modes. You can also use the commands in the **Folder / Flat View** sub-menu.

### Flat View modes

Flat View has three different modes:

- **Mixed**: Displays the contents of the current folder and all its sub-folders (and all their sub-folders, and so on recursively) as if they were all in the one location.
- **Mixed (No Folders)**: Displays all the files in the current folder and all sub-folders as if they were all in the one location. Sub-folders themselves are hidden from the display.
- **Grouped**: Displays the contents of all sub-folders as a tree hierarchy.

The Flat View toolbar button cycles through these modes every time you click it.

### Flat View folder format

From the [Folders / Folder Formats](/Manual/preferences/preferences_categories/folders/folder_formats/README.md) page you can configure a format for **Flat View** (in the *Folder Type Formats* category). This is used automatically whenever you turn Flat View on. By default it's set to add the *Location (relative)* column to the file display.

### Working in Flat View

For the most part you don't have to treat a Lister that's in Flat View mode any differently to any other - you can double-click, drag-and-drop, view, copy, and delete files in the same way you normally do. You can use drag-and-drop to move or copy files into nested sub-folders - you can even move files from one sub-folder to another in this way.

### Drag and drop

If you drop a file into the file display - but **not** onto a sub-folder - then the base folder will be used as the target. Normally when you drag a file you can't drop it in the source folder - as this would be a no-op - but in Flat View you can do this, and one effect of this is that it can be easy to accidentally move a file from a nested sub-folder to the base folder without necessarily meaning to. You can always undo such operations, but it's worth remembering this is a possibility.

### Copying nested files

The only real difference in file operations in Flat View mode comes when you copy files from within sub-folders (via drag-and-drop, copy-and-paste or using the **Copy Files** command). You can choose two ways of performing the copy:

- **Recreate**: Opus will recreate the source folder structure (relative to the base folder) in the destination.
- **Same Folder**: Discards the source folder structure - all files would be copied directly into the target folder.
