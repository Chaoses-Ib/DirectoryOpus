# TabGroupTabList

The **TabGroupTabList** object represents a list of folders that will open as [file display tabs](/Manual/basic_concepts/the_lister/tabs/README.md) when the parent [tab group](/Manual/basic_concepts/the_lister/tabs/tab_groups.md) is opened. You can obtain this object from the **tabs**, **lefttabs** and **righttabs** properties of the **[TabGroup](tabgroup.md)** object.

The **TabGroupsTabList** object is a collection of **[TabGroupTabEntry](tabgrouptabentry.md)** objects; you can enumerate it to discover each folder tab.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
active</td><td>

object:**[TabGroupTabEntry](tabgrouptabentry.md)**</td><td>

Returns a **[TabGroupTabEntry](tabgrouptabentry.md)** object representing the active (default) folder tab in this tab list.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddTab</td><td>

*\<object:***[TabGroupTabEntry](tabgrouptabentry.md)***\>*  
   
or

\<string:path\>  
\<string:name\></td><td>

object:**[TabGroupTabEntry](tabgrouptabentry.md)**</td><td>

Adds a folder tab entry to this list. You can provide a  
**[TabGroupTabEntry](tabgrouptabentry.md)**object, or the *path* and optional *name* of the new folder tab.
</td></tr><tr><td>
DeleteTab</td><td>

*\<object:***[TabGroupTabEntry](tabgrouptabentry.md)***\>*

or

\<int:index\></td><td>

*none*</td><td>

Deletes a folder tab entry from this list. You can provide a  
**[TabGroupTabEntry](tabgrouptabentry.md)**object, or the index of the tab entry to delete. If you specify the index as **-1** then all tab entries will be deleted.
</td></tr><tr><td>
InsertTabAt</td><td>

*\<object:***[TabGroupTabEntry](tabgrouptabentry.md)***\>*  
*\\* or

\<string:path\>  
\<string:name\>

\<int:index\></td><td>

object:**[TabGroupTabEntry](tabgrouptabentry.md)**</td><td>

Inserts a folder tab entry to this list. You can provide a  
**[TabGroupTabEntry](tabgrouptabentry.md)**object, or the *path* and optional *name* of the new folder tab. The final parameter must be the index indicating the desired insertion position.
</td></tr><tr><td>
MoveTabTo</td><td>

*\<object:***[TabGroupTabEntry](tabgrouptabentry.md)***\>  
\<object:***TabGroupTabList***\>*  
\<int:index\></td><td>

*none*</td><td>

Moves the specified tab entry to a new position, and optionally a new tab list. If the second parameter is a **TabGroupTabList** object then the tab entry will be moved to that list. The final parameter must be the index indicating the desired insertion position.
</td></tr></tbody>
</table>

