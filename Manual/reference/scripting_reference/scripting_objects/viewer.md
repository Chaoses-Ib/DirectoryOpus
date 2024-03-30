# Viewer

The **Viewer** object represents a standalone [image viewer](/Manual/additional_functionality/viewing_images/README.md). A collection of **Viewer** objects is returned by the **[Viewers](viewers.md)** object, which is obtainable via the **[DOpus](dopus.md).viewers** property. For functions launched from within a viewer (e.g. from its toolbar), the current **Viewer** object is provided by the **[ClickData](clickdata.md).[func](func.md).viewer** property.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
bottom</td><td>

*int*</td><td>
Returns the bottom coordinate of the viewer window.
</td></tr><tr><td>
current</td><td>

*object:***[Item](item.md)**</td><td>

Returns an **[Item](item.md)** object representing the currently displayed image.
</td></tr><tr><td>
desktop</td><td>

*string*</td><td>
Returns the ID of the virtual desktop this viewer is on.
</td></tr><tr><td>
files</td><td>

*object:***[Items](items.md)**</td><td>

Returns an **[Items](items.md)** object representing the images in the viewer's list.
</td></tr><tr><td>
foreground</td><td>

*bool*</td><td>

Returns **True** if the viewer is currently the foreground (active) window in the system.
</td></tr><tr><td>
imagesize</td><td>

*object:***[Rect](rect.md)**</td><td>

Returns a **[Rect](rect.md)** object representing the size of the currently displayed image (native size, ignoring any scaling).
</td></tr><tr><td>
index</td><td>

*int*</td><td>
Returns the index of the currently viewed image within the viewer's list of files.
</td></tr><tr><td>
lastactive</td><td>

*bool*</td><td>

Returns **True** if the viewer is the most recently active viewer.
</td></tr><tr><td>
left</td><td>

*int*</td><td>
Returns the left coordinate of the viewer window.
</td></tr><tr><td>
parentlister</td><td>

*object:***[Lister](lister.md)**</td><td>

Returns a **[Lister](lister.md)** object representing the Lister that launched the viewer (if there was one, and if it still exists) or, if viewer re-use is enabled, last sent files to the viewer.

There may be a **parentlister** object in situations where there is no longer a **parenttab** object. For example, if the tab was closed since the viewer opened, or if a request to open an image from something other than a folder tab was received by the viewer, then there will no longer be a **parenttab** but the **parentlister** property will persist.

This property is a snapshot of the situation when the **Viewer** scripting object was created; it won't change in reaction to script actions.
</td></tr><tr><td>
parentlisterlinked</td><td>

*bool*</td><td>

Returns **True** if the viewer is in *Lister-Linked* mode with the parent Lister. This means the viewer acts like a detached preview pane, displaying each file as it is selected in the Lister.

This property is a snapshot of the situation when the **Viewer** scripting object was created; it won't change in reaction to script actions.
</td></tr><tr><td>
parenttab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the tab that launched the viewer (if there was one, and if it still exists) or, if viewer re-use is enabled, last sent files to the viewer.

If you want the **[Lister](lister.md)** rather than the Tab, the **parentlister** property (above) should be used, as it is more persistent. Additionally, do not assume **parenttab** is still the active tab in the Lister; query the Lister object if you need that.

This property is a snapshot of the situation when the **Viewer** scripting object was created; it won't change in reaction to script actions.
</td></tr><tr><td>
right</td><td>

*int*</td><td>
Returns the right coordinate of the viewer window.
</td></tr><tr><td>
selection</td><td>

*object:***[Rect](rect.md)**</td><td>

Returns a **[Rect](rect.md)** object representing the current selection area (if any) of the image. If there's no selection the rectangle will be empty.
</td></tr><tr><td>
title</td><td>

*string*</td><td>

Returns or sets the title bar string for the viewer window.

You can use several special "tokens" in the title string to insert various pieces of information:

|            |                                                                                                      |
|------------|------------------------------------------------------------------------------------------------------|
| **%P**     | full path of the currently viewed image                                                              |
| **%N**     | name of the current displayed image                                                                  |
| **%R**     | drive root of the current image                                                                      |
| **%E**     | displays \* if the image's metadata has been modified and not saved                                  |
| **%I**     | current image's index (number) in the list of images                                                 |
| **%O**     | total number of images in the list                                                                   |
| **%W**     | width of the current image                                                                           |
| **%H**     | height of the current image                                                                          |
| **%D**     | depth of the current image (bits per pixel)                                                          |
| **%M**     | current image's dimensions                                                                           |
| **%S**     | file size on disk                                                                                    |
| **%F**     | folder name                                                                                          |
| **%C**     | collection name if current image is [marked](/Manual/additional_functionality/viewing_images/image_marking.md) |
| **%L**     | any [labels](/Manual/file_operations/labels.md) assigned to the current image                                  |
| **%T**     | original title (useful for simply adding a prefix or suffix to the title)                            |
| **%%%%%%** | insert a literal % character                                                                         |
</td></tr><tr><td>
top</td><td>

*int*</td><td>
Returns the top coordinate of the viewer window.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddFile</td><td>

\<string:filepath\>  
\<int:index\></td><td>

*none*</td><td>

Adds the specified file to the viewer's current list of files. You can either pass a string or a **[Path](path.md)** object to indicate the file to add to the list. By default the file will be added to the end of the list, unless you specify a 0-based index as the second argument.
</td></tr><tr><td>
Command</td><td>

\<string:command\> or  
\<**[Command](command.md)**:command\></td><td>

*none*</td><td>

Runs a command in the context of this viewer window. You can either pass a string or a **[Command](command.md)**object.

If the argument you pass is a string then it can only be a viewer command argument as documented for the **[Show](../../command_reference/internal_commands/show.md) VIEWERCMD** command. For example, **Command("next")** would run the **Show VIEWERCMD=next ** command in the context of this viewer.

If you pass a **[Command](command.md)** object then all commands (internal or external) can be used.
</td></tr><tr><td>
IsOnCurrentDesktop</td><td>

*none*</td><td>

*bool*</td><td>

Returns **True** if the viewer is on the current virtual desktop.
</td></tr><tr><td>
MoveToDesktop</td><td>

\<string:desktop\></td><td>

*bool*</td><td>

Moves the viewer window to the specified virtual desktop. Returns **True** if successful.
</td></tr><tr><td>
RemoveFile</td><td>

\<int:index\> or  
\<string:filepath\></td><td>

*none*</td><td>

Removes the specified file from the viewer's current list of files. You can either pass the 0-based index of the file to remove, or the filepath (either as a string or a **[Path](path.md)** object).
</td></tr><tr><td>
SetTaskbarGroup</td><td>

\<string:group\></td><td>

*bool*</td><td>

Used to change how the viewer window is grouped with other Opus windows on the taskbar. Specify a group name to move the window into an alternative group, or omit the group argument to reset back to the default group. If one or more windows are moved into the same group, they will be grouped together, separate from other the default group.

This only works when taskbar grouping is enabled. Group names are limited to 103 characters and will be truncated if longer. Spaces and dots in group names are automatically converted to underscores.

Returns true on success.
</td></tr></tbody>
</table>

