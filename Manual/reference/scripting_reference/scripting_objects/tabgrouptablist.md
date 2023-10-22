# TabGroupTabList

The **TabGroupTabList** object represents a list of folders that will open as [file display tabs](/Manual/basic_concepts/the_lister/tabs/RAEDME.md) when the parent [tab group](/Manual/basic_concepts/the_lister/tabs/tab_groups.md) is opened. You can obtain this object from the **tabs**, **lefttabs** and **righttabs** properties of the **[TabGroup](tabgroup.md)** object.

The **TabGroupsTabList** object is a collection of **[TabGroupTabEntry](tabgrouptabentry.md)** objects; you can enumerate it to discover each folder tab.

| Property Name | Return Type | Description |
| --- | --- | --- |
| active | object:**[TabGroupTabEntry](tabgrouptabentry.md)** | Returns a **[TabGroupTabEntry](tabgrouptabentry.md)** object representing the active (default) folder tab in this tab list. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| AddTab | *\<object:***[TabGroupTabEntry](tabgrouptabentry.md)***\>*  <br />   <br />or<br /><br />\<string:path\>  <br />\<string:name\> | object:**[TabGroupTabEntry](tabgrouptabentry.md)** | Adds a folder tab entry to this list. You can provide a  <br />**[TabGroupTabEntry](tabgrouptabentry.md)**object, or the *path* and optional *name* of the new folder tab. |
| DeleteTab | *\<object:***[TabGroupTabEntry](tabgrouptabentry.md)***\>*<br /><br />or<br /><br />\<int:index\> | *none* | Deletes a folder tab entry from this list. You can provide a  <br />**[TabGroupTabEntry](tabgrouptabentry.md)**object, or the index of the tab entry to delete. If you specify the index as **-1** then all tab entries will be deleted. |
| InsertTabAt | *\<object:***[TabGroupTabEntry](tabgrouptabentry.md)***\>*  <br />*\\* or<br /><br />\<string:path\>  <br />\<string:name\><br /><br />\<int:index\> | object:**[TabGroupTabEntry](tabgrouptabentry.md)** | Inserts a folder tab entry to this list. You can provide a  <br />**[TabGroupTabEntry](tabgrouptabentry.md)**object, or the *path* and optional *name* of the new folder tab. The final parameter must be the index indicating the desired insertion position. |
| MoveTabTo | *\<object:***[TabGroupTabEntry](tabgrouptabentry.md)***\>  <br />\<object:***TabGroupTabList***\>*  <br />\<int:index\> | *none* | Moves the specified tab entry to a new position, and optionally a new tab list. If the second parameter is a **TabGroupTabList** object then the tab entry will be moved to that list. The final parameter must be the index indicating the desired insertion position. |

