# TabGroup

The **TabGroup** object represents a [folder tab group](/Manual/basic_concepts/the_lister/tabs/tab_groups.md)or a folder into which other tab groups can be organized. Individual **TabGroup** objects can be accessed or enumerated from the **[TabGroups](tabgroups.md)** object.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
closeexisting</td><td>

*bool*</td><td>

**True** if the **Close existing folder tabs when opening this group** option is turned on for this group. Only present when the **folder** property is **False**.
</td></tr><tr><td>
desc</td><td>

*string*</td><td>

The description of this tab group, if any. Only present when the **folder** property is **False**.
</td></tr><tr><td>
dual</td><td>

*bool*</td><td>

**True** if the **Define tabs on specific sides of a dual-display Lister** option is turned on for this group. Only present when the **folder** property is **False**.
</td></tr><tr><td>
folder</td><td>

*bool*</td><td>

**True** if this object represents a folder within the tab group list, **False** if it's an actual tab group.
</td></tr><tr><td>
hidden</td><td>

*bool*</td><td>

**True** if this tab group or folder should be hidden from menus which list tab groups. The group will still always be visible in Preferences.
</td></tr><tr><td>
lefttabs</td><td>

*object:***[TabGroupTabList](tabgrouptablist.md)**</td><td>

Returns a **[TabGroupTabList](tabgrouptablist.md)** object representing the tabs in this group that open in the left/top side of a dual-display Lister. Only present when the **folder** property is **False** and the **dual** property is **True**.
</td></tr><tr><td>
name</td><td>

*string*</td><td>
The name of this group or folder.
</td></tr><tr><td>
righttabs</td><td>

*object:***[TabGroupTabList](tabgrouptablist.md)**</td><td>

Returns a **[TabGroupTabList](tabgrouptablist.md)** object representing the tabs in this group that open in the right/bottom side of a dual-display Lister. Only present when the **folder** property is **False** and the **dual** property is **True**.
</td></tr><tr><td>
tabs</td><td>

*object:***[TabGroupTabList](tabgrouptablist.md)**</td><td>

Returns a **[TabGroupTabList](tabgrouptablist.md)** object representing the tabs in this group. Only present when both the **folder** and **dual** properties are **False**.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddChildFolder</td><td>

*\<object:***TabGroup**\> or \<string:name\></td><td>

*object:**TabGroup***</td><td>

Adds a new sub-folder to this tab group folder. Only available when the **folder** property is **True**. You can either provide a **TabGroup** object (which itself has the folder property set to **True**) or the name for the new folder. If the operation succeeds a **TabGroup** object is returned which represents the new folder. If the operation fails **False** is returned.
</td></tr><tr><td>
AddChildGroup</td><td>

*\<object:***TabGroup**\> or \<string:name\></td><td>

*object:**TabGroup***</td><td>

Adds a new tab group to this tab group folder. Only available when the **folder** property is **True.** You can either provide a **TabGroup** object or the name for the new group. If the operation succeeds a **TabGroup** object is returned which represents the new tab group. If the operation fails **False** is returned.
</td></tr><tr><td>
DeleteChild</td><td>

*\<object:***TabGroup**\></td><td>

*none*</td><td>
Deletes the child item (folder or tab group).
</td></tr><tr><td>
Duplicate</td><td>

*none*</td><td>

*object:**TabGroup***</td><td>
Returns a duplicate of this tab group or folder. When it's returned the duplicate has not yet been added to a tab list.
</td></tr><tr><td>
Link</td><td>

*\<object:***[TabGroupTabEntry](tabgrouptabentry.md)**\>  
*\<object:***[TabGroupTabEntry](tabgrouptabentry.md)**\>  
\<string:type\></td><td>

*none*</td><td>

In a tab group that has specific left and right tabs specified, this method links together a tab from the left side and a tab from the right side. Only available if the **dual** property is set to **True**. You can provide **[TabGroupTabEntry](tabgrouptabentry.md)**objects or the index numbers of the tabs you want to link.

The optional *type* parameter can be set to **"slave"** to specify that the tabs should be slaved to each other.
</td></tr><tr><td>
Unlink</td><td>

*\<object:***[TabGroupTabEntry](tabgrouptabentry.md)**\>* *</td><td>

*none*</td><td>

Unlinks the specified tab from its partner. Only available if the **dual** property is set to **True**.
</td></tr></tbody>
</table>

