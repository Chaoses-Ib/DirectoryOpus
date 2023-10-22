# OnDoubleClick

The **OnDoubleClick** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) to receive notification when the user double-clicks on a file or folder in a tab.

By default your event handler is passed an **[Item](../scripting_objects/item.md)** object corresponding to the item that was double-clicked. Because constructing an Item object may take some time (e.g. on a network drive) you have the option for your handler to be called twice - once with only the path to the item, and a second time (if desired) with the full **Item** object. To do this:

1.  Set the **[ScriptInitData](../scripting_objects/scriptinitdata.md).early_dblclk** property to **True** when you initialize your script.
2.  Your **OnDoubleClick** event will then be called with a the **early** property set to **True** in the **[DoubleClickData](../scripting_objects/doubleclickdata.md)** object.
3.  When **early** is **True**, the **item** property is not present; instead, the **path** property provides the full path of the object, and the **is_dir** property indicates whether the item is a folder or file.
4.  When the **OnDoubleClick** method returns, it will be called a second time, with **early** set to **False** and a full **Item** object available in the **item** property.
5.  If you sets the **skipfull** property to **True** in the **[DoubleClickData](../scripting_objects/doubleclickdata.md)** object at the "early" stage, the second call to **OnDoubleClick** doesn't occur.

| **Method Name:** | OnDoubleClick |
| --- | --- |
| **Argument Type:** | **[DoubleClickData](../scripting_objects/doubleclickdata.md)** |
| **Return Type:** | *bool* or *string* |
| **Description:** | The **DoubleClickData.tab** property identifies the tab, and the **item** property identifies the item that has been double-clicked.<br /><br />You can return two different types from this event:<br /><br />- *bool*: If you return **True**, the double-click will be cancelled and the file will not be opened. If you return **False** the double-click will be allowed to continue (this is the default).<br />- *string*: You can return a *string* to change the function to be performed on the file. For example, you could return the string *"Show"* to run the internal **Show** command on the file. |

