A number of variables are available to the evaluator in this context. Note that some are only applicable to toolbars in the [standalone image viewer](/Manual/additional_functionality/viewing_images/README.md), and some only apply to Lister toolbars.

<table>
<thead><tr><th>
Variable</th><th>
Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
dest</td><td>

*path*</td><td>
The current destination path.
</td></tr><tr><td>
dest_shell</td><td>

*bool*</td><td>

**True** if the destination is a shell (virtual) folder hosted by Explorer, otherwise **false**.
</td></tr><tr><td>
expanded</td><td>

*uint*</td><td>
Returns the number of expanded directories.
</td></tr><tr><td>
fullscreen</td><td>

*bool*</td><td>

*Viewer only*. **True** if the viewer is fullscreen, otherwise **false**.
</td></tr><tr><td>
key_repeat</td><td>

*bool*</td><td>

**True** if the function was launched from a repeated key press (i.e. the key was held down).
</td></tr><tr><td>
lister_title</td><td>

*string*</td><td>
Returns the current title string of the Lister.
</td></tr><tr><td>
preparse_dummy</td><td>

*bool*</td><td>

**True** if the evaluator is being called with a dummy filename as part of *pre-parsing*. Opus will do this for evaluator expressions inside a `@perfile` block. You should generally respond normally (Opus is querying to find out which values the evaluator expression requires), but you may want to filter out some behaviour (e.g. logging) for pre-parsing.
</td></tr><tr><td>
selbytes</td><td>

*uint64*</td><td>
Returns the number of selected bytes (files + directories that have had their sizes calculated).
</td></tr><tr><td>
seldirs</td><td>

*uint*</td><td>
Returns the number of selected directories.
</td></tr><tr><td>
selfiles</td><td>

*uint*</td><td>
Returns the number of selected files.
</td></tr><tr><td>
selimage</td><td>

*bool*</td><td>

*Viewer only*. **True** if an area of the image has been selected, **false** otherwise.
</td></tr><tr><td>
selitems</td><td>

*uint*</td><td>
Returns the total number of selected items.
</td></tr><tr><td>
selpath</td><td>

*string*</td><td>
Provides the full pathname of the currently selected file. In a Lister this means the selected file with input focus (e.g. the file you right-click on). In the viewer this means the currently viewed image. Note that main toolbars in the Lister are not necessarily refreshed when the file selection changes, and so a button on the main toolbar using this may not always show the correct information.
</td></tr><tr><td>
source</td><td>

*path*</td><td>
The current source path.
</td></tr><tr><td>
source_shell</td><td>

*bool*</td><td>

**True** if the source is a shell (virtual) folder hosted by Explorer, otherwise **false**.
</td></tr><tr><td>
totalbytes</td><td>

*uint64*</td><td>
Returns the total number of bytes (files + directories that have had their sizes calculated).
</td></tr><tr><td>
totaldirs</td><td>

*uint*</td><td>
Returns the total number of directories.
</td></tr><tr><td>
totalfiles</td><td>

*uint*</td><td>
Returns the total number of files.
</td></tr><tr><td>
totalitems</td><td>

*uint*</td><td>
Returns the total number of items.
</td></tr><tr><td>
viewmode</td><td>

*str*</td><td>

Returns the current view mode in the file display. Values are **largeicons**, **smallicons**, **list**, **details**, **power**, **thumbnails** and **tiles**.
</td></tr></tbody>
</table>

As well as the above variables, you can also use [evaluator functions](/Manual/reference/evaluator/README.md) like [ischecked](/Manual/reference/evaluator/ischecked.md) and [isenabled](/Manual/reference/evaluator/isenabled.md) to query other information about the state of the Lister.
