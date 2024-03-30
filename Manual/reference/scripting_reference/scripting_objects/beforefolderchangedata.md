# BeforeFolderChangeData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnBeforeFolderChange](../scripting_events/onbeforefolderchange.md)** event, the method receives a **BeforeFolderChangeData** object before the new folder is read.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
action</td><td>

*string*</td><td>

Returns a string indicating the action that triggered the folder read. The string will be one of the following: *normal*, *refresh*, *refreshsearch*, *refreshsub*, *parent*, *root*, *back*, *forward*, *dblclk*.  
The *refreshsub* actions means the folder (and sub-folders) are being refreshed while Flat View is on. The other action names should be self-explanatory.
</td></tr><tr><td>
initial</td><td>

*bool*</td><td>

Returns **True** if this is the first path to be read into this tab (i.e. previously the tab was empty).
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.md)**</td><td>

Returns a **[Path](path.md)** object representing the new path that is to be read.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  
The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  
If no qualifiers were down, the string will be: *none*
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the tab that is changing folder.
</td></tr></tbody>
</table>

