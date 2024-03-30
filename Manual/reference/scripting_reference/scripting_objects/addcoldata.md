# AddColData

The **AddColData** object is passed to the **OnAddColumns** event in a [script add-in](/Manual/scripting/script_add-ins/README.md). The script can use this to [add columns](/Manual/scripting/example_scripts/adding_a_new_column.md) using the **AddColumn** method.

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddColumn</td><td>

*none*</td><td>

*object:***[ScriptColumn](scriptcolumn.md)**</td><td>

Adds a new information column to Opus. The returned **[ScriptColumn](scriptcolumn.md)** object must be properly initialized. A script add-in can add as many columns as it likes, and these will be available in file displays, infotips and the **[Advanced Find](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.md)** function.
</td></tr></tbody>
</table>

