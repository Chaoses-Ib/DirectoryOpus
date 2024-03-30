# TabGroupTabEntry

The **TabGroupTabEntry** object represents a single [folder tab](/Manual/basic_concepts/the_lister/tabs/README.md). The folder tabs in a tab group can be enumerated via the **[TabGroupTabList](tabgrouptablist.md)** object.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>

**Description**
</th></tr></thead><tbody><tr><td>
color</td><td>

*string*</td><td>
Returns the color, if any, assigned to this tab.
</td></tr><tr><td>
format</td><td>

object:**[Format](format.md)**</td><td>
Returns the folder format of this tab.
</td></tr><tr><td>
linkid</td><td>

*int*</td><td>

Returns the link ID of this tab, if it is linked to another tab. Both tabs will have the same link ID but otherwise the value is meaningless. Use the **[TabGroup](tabgroup.md).Link** and **Unlink** methods to change tab linkage.
</td></tr><tr><td>
linktype</td><td>

*string*</td><td>

If this tab is linked as a slave, returns the string **"slave"**.
</td></tr><tr><td>
locked</td><td>

*string*</td><td>

Returns the lock type of this tab. Valid values are **"on"**, **"off"**, **"changes"** and **"reuse"**.
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Returns the name of this tab if one is assigned. Tabs that don't have specific names assigned will usually show the last component of the path as their name.
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.md)**</td><td>
Returns the path that this tab will load when it's opened.
</td></tr></tbody>
</table>

  

<table>
<thead><tr><th>

**Method Name**</th><th>

**Arguments**</th><th>

**Return Type**</th><th>

**Description**
</th></tr></thead><tbody><tr><td>
Duplicate</td><td>

*none*</td><td>

*object:***TabGroupTabEntry**</td><td>
Returns a duplicate of this tab entry.
</td></tr></tbody>
</table>

 
