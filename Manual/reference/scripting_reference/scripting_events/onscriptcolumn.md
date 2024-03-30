# OnScriptColumn

The **OnScriptColumn** event is the entry point for a [custom column](/Manual/scripting/example_scripts/adding_a_new_column.md) added by a [script add-in](/Manual/scripting/script_add-ins/README.md). The actual name of the event is defined by the script itself, when the command is added via the **[ScriptInitData](../scripting_objects/scriptinitdata.md).AddColumn** method - **OnScriptColumn** is merely a placeholder name.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnScriptColumn
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[ScriptColumnData](../scripting_objects/scriptcolumndata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

When a script add-in adds a new column using **[ScriptInitData](../scripting_objects/scriptinitdata.md).AddCommand**, it specifies the name of its entry point with the **ScriptColumn.method** property. When Opus wants to retrieve the value of the column for a particular file or folder, Opus will call that method within your script.  
The **[ScriptColumnData](../scripting_objects/scriptcolumndata.md).item** property provides information about the file or folder in question, and the **col** property identifies the column you should return data for (in case you use the one method for more than one columns).

The return value from this event is ignored - instead, you should return the column data (and optionally, sorting and grouping information) by setting the appropriate values in the **[ScriptColumnData](../scripting_objects/scriptcolumndata.md)** object.
</td></tr></tbody>
</table>

