# ConfigChangeData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnScriptConfigChange](../scripting_events/onscriptconfigchange.md)**event, the method receives a **ConfigChangeData** object whenever the user modifies the script's configuration via the Preferences editor.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
changed</td><td>

**[Vector](vector.md)**:*string*</td><td>

Returns a **[Vector](vector.md)** containing the names of the configuration items that were modified.
</td></tr></tbody>
</table>

