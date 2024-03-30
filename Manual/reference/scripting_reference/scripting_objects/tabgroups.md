# TabGroups

The **TabGroups** object lets your script query and modify the configured [Folder Tab Groups](/Manual/basic_concepts/the_lister/tabs/tab_groups.md). You can obtain a **TabGroups** object from the **[DOpus](dopus.md).TabGroups** property.

The **TabGroups** object is a collection of **[TabGroup](tabgroup.md)** objects; you can enumerate it to discover the top-level tab groups and folders. Folders can also be enumerated to discover the tab groups and folders they contain, and so on.

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddChildFolder</td><td>

*\<object:***[TabGroup](tabgroup.md)**\> or \<string:name\></td><td>

*object:**[TabGroup](tabgroup.md)***</td><td>

Adds a new folder to the list of tab groups. You can either provide a **[TabGroup](tabgroup.md)**object (which has the folder property set to **True**) or the name for the new folder. If the operation succeeds a **[TabGroup](tabgroup.md)**object is returned which represents the new folder. If the operation fails **False** is returned.
</td></tr><tr><td>
AddChildGroup</td><td>

*\<object:***[TabGroup](tabgroup.md)**\> or \<string:name\></td><td>

*object:**[TabGroup](tabgroup.md)***</td><td>

Adds a new tab group to the list of tab groups. You can either provide a **[TabGroup](tabgroup.md)**object or the name for the new group. If the operation succeeds a **[TabGroup](tabgroup.md)**object is returned which represents the new tab group. If the operation fails **False** is returned.
</td></tr><tr><td>
DeleteChild</td><td>

*\<object:***[TabGroup](tabgroup.md)**\></td><td>

*none*</td><td>
Deletes the child item (folder or tab group).
</td></tr><tr><td>
Save</td><td>

*none*</td><td>

*none*</td><td>

Saves the tab group list and any changes you have made.  
Note that this only saves changes made to the object it is called on, and each use of **DOpus.TabGroups** creates a new, independent object. Therefore, you should modify tab groups like this (JScript):`var tabGroups = DOpus.TabGroups;
    var group = tabGroups.AddChildGroup("New Tab Group");
    if (!group)
        DOpus.Output("Group already exists");
    else {
        group.desc = "Example description";
        var tabs = group.tabs;
        tabs.AddTab("C:\\");
        tabGroups.Save();
    }`  
And not like this:`// This will not work correctly.
    var group = DOpus.TabGroups.AddChildGroup("New Tab Group");
    if (!group)
        DOpus.Output("Group already exists");
    else {
        group.desc = "Example description";
        group.tabs.AddTab("C:\\");
        DOpus.TabGroups.Save();
    }`  
The second example will not work because the last line creates a second, unrelated snapshot of the current state, which is unaffected by the unsaved changes to the first snapshot, and then saves the second snapshot without making any changes to it.
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

Updates the **TabGroups** object to reflect any changes made through the Preferences user interface.
</td></tr></tbody>
</table>

