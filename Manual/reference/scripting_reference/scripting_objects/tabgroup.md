# TabGroup

The **TabGroup** object represents a [folder tab group](/Manual/basic_concepts/the_lister/tabs/tab_groups.md)or a folder into which other tab groups can be organized. Individual **TabGroup** objects can be accessed or enumerated from the **[TabGroups](tabgroups.md)** object.

| Property Name | Return Type | Description |
| --- | --- | --- |
| closeexisting | *bool* | **True** if the **Close existing folder tabs when opening this group** option is turned on for this group. Only present when the **folder** property is **False**. |
| desc | *string* | The description of this tab group, if any. Only present when the **folder** property is **False**. |
| dual | *bool* | **True** if the **Define tabs on specific sides of a dual-display Lister** option is turned on for this group. Only present when the **folder** property is **False**. |
| folder | *bool* | **True** if this object represents a folder within the tab group list, **False** if it's an actual tab group. |
| hidden | *bool* | **True** if this tab group or folder should be hidden from menus which list tab groups. The group will still always be visible in Preferences. |
| lefttabs | *object:***[TabGroupTabList](tabgrouptablist.md)** | Returns a **[TabGroupTabList](tabgrouptablist.md)** object representing the tabs in this group that open in the left/top side of a dual-display Lister. Only present when the **folder** property is **False** and the **dual** property is **True**. |
| name | *string* | The name of this group or folder. |
| righttabs | *object:***[TabGroupTabList](tabgrouptablist.md)** | Returns a **[TabGroupTabList](tabgrouptablist.md)** object representing the tabs in this group that open in the right/bottom side of a dual-display Lister. Only present when the **folder** property is **False** and the **dual** property is **True**. |
| tabs | *object:***[TabGroupTabList](tabgrouptablist.md)** | Returns a **[TabGroupTabList](tabgrouptablist.md)** object representing the tabs in this group. Only present when both the **folder** and **dual** properties are **False**. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| AddChildFolder | *\<object:***TabGroup**\> or \<string:name\> | *object:**TabGroup*** | Adds a new sub-folder to this tab group folder. Only available when the **folder** property is **True**. You can either provide a **TabGroup** object (which itself has the folder property set to **True**) or the name for the new folder. If the operation succeeds a **TabGroup** object is returned which represents the new folder. If the operation fails **False** is returned. |
| AddChildGroup | *\<object:***TabGroup**\> or \<string:name\> | *object:**TabGroup*** | Adds a new tab group to this tab group folder. Only available when the **folder** property is **True.** You can either provide a **TabGroup** object or the name for the new group. If the operation succeeds a **TabGroup** object is returned which represents the new tab group. If the operation fails **False** is returned. |
| DeleteChild | *\<object:***TabGroup**\> | *none* | Deletes the child item (folder or tab group). |
| Duplicate | *none* | *object:**TabGroup*** | Returns a duplicate of this tab group or folder. When it's returned the duplicate has not yet been added to a tab list. |
| Link | *\<object:***[TabGroupTabEntry](tabgrouptabentry.md)**\>  <br />*\<object:***[TabGroupTabEntry](tabgrouptabentry.md)**\>  <br />\<string:type\> | *none* | In a tab group that has specific left and right tabs specified, this method links together a tab from the left side and a tab from the right side. Only available if the **dual** property is set to **True**. You can provide **[TabGroupTabEntry](tabgrouptabentry.md)**objects or the index numbers of the tabs you want to link.<br /><br />The optional *type* parameter can be set to **"slave"** to specify that the tabs should be slaved to each other. |
| Unlink | *\<object:***[TabGroupTabEntry](tabgrouptabentry.md)**\>* * | *none* | Unlinks the specified tab from its partner. Only available if the **dual** property is set to **True**. |

