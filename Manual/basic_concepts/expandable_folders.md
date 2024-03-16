# Expandable Folders

You can expand individual folders in the file display just like you can in the folder tree. This lets you see the contents of sub-folders and copy files in and out of them without having to actually navigate to the folder in question.

![](/Manual/images/media/13/expanded_folders.png)

##### Enabling expandable folders

You can enable or disable expandable folders from the [File Displays / Folder Expansion](/Manual/preferences/preferences_categories/file_displays/folder_expansion.md) Preferences page.

##### Expanding a folder

When expandable folders are enabled, a small area on the left of the filename is reserved for an arrow glyph. To expand a folder, either:

- Click the arrow glyph, or
- With focus on the folder, press <kbd>Alt+Down</kbd>

To collapse a folder, click the glyph again, or press <kbd>Alt+Up</kbd>.

##### Drag and drop

When a folder is expanded, you can drag files into its sub-folders to copy or move them. You can also drag files out of sub-folders into the current (parent folder), or drop them on other folders to move them around.

On the [Folder Expansion](/Manual/preferences/preferences_categories/file_displays/folder_expansion.md) Preferences page there's an option to enable "spring-loaded" folders, which expand when you drag over them and then collapse again when the drag operation is finished.

##### Hiding the expansion glyphs

If you only want to use expandable folders sometimes, you can turn on the **Hide expand buttons until a folder is expanded** option. Expandable folders will still be enabled, but the expansion glyphs will be hidden until at least one sub-folder is expanded. To expand sub-folders without the glpyhs being visible, you can use the <kbd>Alt+Down</kbd> key, or configure your own key to run the `Go EXPANDBRANCH` internal command.

##### Copying nested files

When you copy files from within sub-folders (via drag-and-drop, copy-and-paste or using the **Copy Files** command), you can choose two ways of performing the copy:

- **Recreate**: Opus will recreate the source folder structure (relative to the base folder) in the destination.
- **Same Folder**: Discards the source folder structure - all files would be copied directly into the target folder.
