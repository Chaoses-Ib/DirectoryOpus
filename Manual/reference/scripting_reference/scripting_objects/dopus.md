# DOpus

The **DOpus** object is one of the two global script objects provided by Opus, and is available to *all* scripts. It provides various helper methods, and collections that let you access things like Listers and toolbars.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
aliases</td><td>

*object:***[Aliases](aliases.md)**</td><td>

The **[Aliases](aliases.md)**object gives the script access to the defined [folder aliases](/Manual/basic_concepts/the_lister/navigation/aliases.md).
</td></tr><tr><td>
favoriteformats</td><td>

*collection*:**[Format](format.md)**</td><td>

Returns a collection of **[Format](format.md)** objects representing the used-defined favorite formats.
</td></tr><tr><td>
favorites</td><td>

*object:***[Favorites](favorites.md)**</td><td>

Returns a **[Favorites](favorites.md)**object which lets you query and modify the user-defined favorite folders.
</td></tr><tr><td>
filetypegroups</td><td>

*object*:**[FiletypeGroups](filetypegroups.md)**</td><td>

Returns a **[FiletypeGroups](filetypegroups.md)** object which lets you enumerate and query the configured [file type groups](/Manual/file_types/file_type_groups.md).
</td></tr><tr><td>
filters</td><td>

*object:***[GlobalFilters](/Manual/basic_concepts/folder_options/folder_options_dialog/filters.md)**</td><td>

Returns a **[GlobalFilters](globalfilters.md)** object which lets you access information about the global filter settings (configured on the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences).
</td></tr><tr><td>
language</td><td>

*string*</td><td>
Returns a string representing the current user interface language.
</td></tr><tr><td>
listers</td><td>

*object:***[Listers](listers.md)**</td><td>

Returns a **[Listers](listers.md)** object which represents any currently open Lister windows (each one is represented by a **[Lister](lister.md)** object).
</td></tr><tr><td>
smartfavorites</td><td>

*object:***[SmartFavorites](smartfavorites.md)**</td><td>

Returns a **[SmartFavorites](smartfavorites.md)** object which lets you query the [SmartFavorites](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md)data.
</td></tr><tr><td>
spacingscheme</td><td>

*string*</td><td>

Returns the name of the current [UI spacing scheme](/Manual/preferences/preferences_categories/user_interface/spacing.md) (if any).
</td></tr><tr><td>
strings</td><td>

*object:***[ScriptStrings](scriptstrings.md)**</td><td>

Returns a **[ScriptStrings](scriptstrings.md)** object which lets your script access any strings defined as [string resources](/Manual/scripting/resources/string_resources.md).
</td></tr><tr><td>
tabgroups</td><td>

*object:***[TabGroups](tabgroups.md)**</td><td>

Returns a **[TabGroups](tabgroups.md)** object which lets your script access and manipulate the configured [folder tab groups](/Manual/basic_concepts/the_lister/tabs/tab_groups.md).
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.md)**</td><td>

This **[Vars](vars.md)** object represents all defined variables with *global scope*.
</td></tr><tr><td>
version</td><td>

*object:***[Version](version.md)**</td><td>

The **[Version](version.md)** object provides information about the current Opus program version.
</td></tr><tr><td>
viewers</td><td>

*object:***[Viewers](viewers.md)**</td><td>

Returns a **Viewers** object which represents any currently open [standalone image viewers](/Manual/additional_functionality/viewing_images/README.md) (each one is represented by a **[Viewer](viewer.md)** object).
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
ClearOutput</td><td>

*none*</td><td>

*none*</td><td>
Clears the script output log.
</td></tr><tr><td>
Create</td><td>

*none*</td><td>

*object:***[DOpusFactory](dopusfactory.md)**</td><td>

Creates and returns a new **[DOpusFactory](dopusfactory.md)** object, which can be used to create various lightweight helper objects like **[Blob](blob.md)**, **[Map](map.md)** and **[Vector](vector.md)**.
</td></tr><tr><td>
Delay</td><td>

\<int:time\></td><td>

*none*</td><td>
Delays for the specified number of milliseconds before returning.
</td></tr><tr><td>
Dlg</td><td>

*none*</td><td>

*object:***[Dialog](dialog.md)**</td><td>

Creates a new **[Dialog](dialog.md)** object, that lets you display dialogs and popup menus.

**Note:** Scripts should not usually use this when responding to events triggered by toolbars or folder tabs. The **Dialog** returned by **DOpus.Dlg** will not have its parent window configured. Most scripting events provide you an object which can either create a pre-configured **Dialog** or which includes a **SourceTab** property or similar which can do the same. In almost all situations you should use those instead.
</td></tr><tr><td>
DPI</td><td>

*none*</td><td>

*object:***[DPI](dpi.md)**</td><td>

Creates the **[DPI](dpi.md)** helper object which assists when dealing with different system scaling settings (e.g. high-DPI monitors).
</td></tr><tr><td>
FlushConfig</td><td>

*none*</td><td>

*none*</td><td>
Forces Opus to write any configuration changes to disk immediately.
</td></tr><tr><td>
FSUtil</td><td>

*none*</td><td>

*object:***[FSUtil](fsutil.md)**</td><td>

Creates a new **[FSUtil](fsutil.md)** object, that provides helper methods for accessing the file system.
</td></tr><tr><td>
GetClip</td><td>

*none*  
or \<string:type\></td><td>

*string*  
or *object:***[Items](items.md)**</td><td>

Retrieves the current contents of the system clipboard, if it contains either text or files.

You can control the returned type by passing either "**text**" or "**files**" for the *\<type\>* argument - Opus will convert to the requested type if possible.

If *\<type\>* is not specified the contents will be returned in their native format.
</td></tr><tr><td>
GetClipFormat</td><td>

*none* or \<string:flags\></td><td>

*string*</td><td>

Returns a string indicating the native format of the clipboard contents.

Optional flags:

|       |                                            |
|-------|--------------------------------------------|
| **c** | Differentiate between cut and copied files |

Possible return values:

|                  |                                                      |
|------------------|------------------------------------------------------|
| **files**        | Files, if **flags** omitted or doesn't include **c** |
| **files_copy**   | Files via Copy (Ctrl-C), if **flags** includes **c** |
| **files_cut**    | Files via Cut (Ctrl-X), if **flags** includes **c**  |
| **image**        | Bitmap data                                          |
| **text**         | Text data                                            |
| \<empty string\> | Empty clipboard, or any other type of data           |
</td></tr><tr><td>
GetListers</td><td>

*none*  
or \<string:flags\></td><td>

*object:***[Listers](listers.md)**</td><td>

Returns a **[Listers](listers.md)** object which represents any currently open Lister windows (each one is represented by a **[Lister](lister.md)** object). This is the same as using the **listers** property, except that you can specify the optional flags:

|       |                                                                              |
|-------|------------------------------------------------------------------------------|
| **c** | Current desktop only. Only returns Listers from the current virtual desktop. |
</td></tr><tr><td>
GetQualifiers</td><td>

*none*</td><td>

*string*</td><td>

Returns a string indicating which qualifier keys are currently held down. If none are held down, the string will be "**none**". Otherwise, the string can contain any or all of the following, separated by commas: "**shift**", "**ctrl**", "**alt**", "**lwin**", "**rwin**".

Note that many events pass you a similar list of qualifiers. If you are passed a list of qualifiers, you should generally use that list rather than call DOpus.GetQualifiers.

For example, script commands are passed a **[Func](func.md)** object with a *qualifiers* property. That property will tell you which keys were held down when the command was triggered, and that may be different to the keys held down a few seconds later. When the user clicks a button to run a command, they normally expect the command to use the keys they held when they clicked, not the keys they are touching later while waiting for it to finish.

Similarly, events like **[OnBeforeFolderChange](../scripting_events/onbeforefolderchange.md)** will often pass you an object like **[BeforeFolderChangeData](beforefolderchangedata.md)** containing a *qualifiers* property which indicates key state when the event was triggered. You should normally use that instead of calling DOpus.GetQualifiers.

If you do call DOpus.GetQualifiers, you would normally want to call it as soon as possible and then store the result, so there is less time for the user to let go of a key after triggering your script.

If you call DOpus.GetQualifiers more than once, you may get a different result each time, due to keys being pushed or released between calls. Call it once and store the result if you need to do multiple checks and need them to be consistent. This does not generally affect the *qualifiers* properties mentioned earlier, since they are usually stored snapshots of the key state.
</td></tr><tr><td>
LoadImage</td><td>

\<string:filename\> or \<object:**[Blob](blob.md)**\>  
\[\<string:typehint\>\]  
\[\<int:width\>\]  
\[\<int:height\>\]  
\[\<bool:alpha\>\]</td><td>

object:**[Image](image.md)**</td><td>

Loads an image file from the specified file. You can optionally specify the desired size to load the image at, and whether the alpha channel (if any) should be loaded or not. Note that the *typehint* argument should only be provided if passing a **Blob**.

You can load icons from the internal icon set using `#iconname`. E.g. `#copy` would load the copy image from the default set. By default the large size is returned; use `#0:iconname` for the small size. You can also specify a particular icon set using `#setname:iconname` or `#0:setname:iconname`.

Images can be extracted from DLLs and EXEs by appending the icon index to the filename, e.g. `/system/zipfldr.dll,1`.

You can also provide a **[Blob](blob.md)** object containing the image data instead of a filename. If you do this, the second parameter can be a *typehint* string to provide a type-hint for the data format (e.g. pass ".jpg" if you know it's JPEG data).

The returned **[Image](image.md)** object can be given as the value of the **[Control](control.md).label** property for a static control in a [script dialog](/Manual/scripting/script_dialogs/README.md) (when that control is in "image" mode). You can also assign it as the **icon** property of a **[Dialog](dialog.md)** object to specify a custom window icon for your script dialog.

The defaults for *width* and *height* if not provided are 0, meaning to load the image at its native size. Images are loaded transparently (with alpha) by default; set the *alpha* argument to **False** if you want to disable that.
</td></tr><tr><td>
LoadThumbnail</td><td>

\<string:filename\>  
\[\<int:timeout\>\]  
\[\<int:width\>\]  
\[\<int:height\>\]  
\[\<string:flags\>\]</td><td>

object:**[Image](image.md)**  
or  
*bool* (**False**)</td><td>

Extracts a thumbnail from the specified external file. You can optionally specify a timeout (in milliseconds) and the desired size to load the thumbnail at.

The optional **flags** value supports the following flags (supplied as a string):

|       |                                                                                                                                                                 |
|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **i** | prevents Opus from waiting for thumbnails that may take some time to generate, and instead returns a large icon if the thumbnail can't be generated immediately |
| **c** | modifies the **i** flag to only apply to Cloud storage folders                                                                                                  |

If loading fails (or the timeout expires before the thumbnail could be generated) this method returns **False**.

The returned **[Image](image.md)** object can be given as the value of the **[Control](control.md).label** property for a static control in a [script dialog](/Manual/scripting/script_dialogs/README.md) (when that control is in "image" mode). You can also assign as to the **icon** property of a **[Dialog](dialog.md)** object to specify a custom window icon for your script dialog.
</td></tr><tr><td>
MusicGenres</td><td>

*none*</td><td>

object:**[Vector](vector.md)**</td><td>

Returns a [Vector](vector.md) of strings representing the music genres configured to be shown in the Genre field of the metadata panel.
</td></tr><tr><td>
Notify</td><td>

\<string:title\>  
\<string:message\>  
\[\<string:flags\>\]</td><td>

*none*</td><td>

Displays a system notification (or in Windows 7, a balloon tooltip). This requires the Opus taskbar icon to be added to the taskbar notification area so if it's turned off in Preferences, it will be added temporarily and then removed again.

The optional flags are:

|       |                                                                                        |
|-------|----------------------------------------------------------------------------------------|
| **n** | No sound. Prevents the system from playing a sound when the notification is displayed. |
</td></tr><tr><td>
Output</td><td>

\<string:text\>  
\[\<bool:error\>\]  
\[\<bool:timestamp\>\]</td><td>

*none*</td><td>

Prints the specified text string to the script output log (found in the [Utility Panel, ](/Manual/basic_concepts/the_lister/utility_panel.md) the [CLI](/Manual/additional_functionality/cli.md) in script mode, the *Rename* dialog and the *Command Editor* in script mode).

If the second argument is provided and set to **True**, the message will be displayed as an error. This means the text will be displayed in red and if no log windows are currently open, a warning icon will flash in the Lister status bar to alert the user of an error condition.

If the optional third argument is provided and set to **True** then the log message will have a timestamp prepended to it. Timestamps only appear in the utility panel, not in places like the Command Editor's output panel. Error messages always get timestamps so if the second argument is **True** then the third is ignored
</td></tr><tr><td>
ReloadScript</td><td>

\<string:file\></td><td>

*none*</td><td>

Causes Opus to reload and reinitialize the specified script. You must provide the full pathname of the script on disk (if a script add-in wants to reload itself you can pass the value of the **[Script](script.md).file** property).
</td></tr><tr><td>
SendCustomMsg</td><td>

\<string:msg\>  
\[\<int:data\> or  
\<object:data\>\]</td><td>

*bool*</td><td>

Sends a named message to any existing script dialogs that have registered to receive that message via **[Dialog](dialog.md).AddCustomMsg**.

Any dialogs that have registered for the message will receive a "custom" **[Msg](msg.md)** in their message loop, with the message name in the `name` property.

You can optionally pass a single numeric value, or a container object (e.g. a **[Map](map.md)**) along with the message, which will be received by the dialog in either the `data` or `object` property of the **Msg**.
</td></tr><tr><td>
SendKey</td><td>

\<string:key\></td><td>

*bool*</td><td>

Sends the specified keystroke to the system. The key will be routed to whichever window currently has focus. For example, `DOpus.SendKey("win+v");` sends the <kbd>Win</kbd>+<kbd>V</kbd> key to the system, which opens the Windows clipboard viewer.

Supported qualifier keys are `shift`, `ctrl`, `alt` and `win`.

As well as letters and numbers, the following named keys are also supported: `backspace`, `capslock`, `delete`, `down`, `end`, `enter`, `escape`, `home`, `insert`, `left`, `numlock`, `pagedown`, `pageup`, `pause`, `printscr`, `right`, `scrlock`, `space`, `tab`, `up`.
</td></tr><tr><td>
SetClip</td><td>

\<string:text\>  
or *object:***[Items](items.md)**  
or *none*</td><td>

*none*</td><td>

Places the specified text, or **[Items](items.md)** object (or similar, see below) on the system clipboard. If called with no arguments the clipboard will be cleared.

When passing a file list, you can also give a **[Vector](vector.md)** of **[Item](item.md)** or **[Path](path.md)** objects, or full path strings, instead of a collection. Or a **[StringSet](stringset.md)** or **[UnorderedSet](unorderedset.md)** of full path strings.
</td></tr><tr><td>
Toolbars</td><td>

\<string:type\></td><td>

object:**[Toolbars](toolbars.md) **</td><td>

Returns a **[Toolbars](toolbars.md)** object which lets you enumerate all defined toolbars (whether they are currently open or not).

You can restrict this object to only return in-use toolbars by specifying the optional *type* parameter - specify **"listers"** to only return toolbars currently turned on in a Lister, and **"docks"** to only return toolbars that are currently floating.
</td></tr><tr><td>
TypeOf</td><td>

*any*</td><td>

*string*</td><td>
Returns a string indicating the type of an object or variable.
</td></tr></tbody>
</table>

