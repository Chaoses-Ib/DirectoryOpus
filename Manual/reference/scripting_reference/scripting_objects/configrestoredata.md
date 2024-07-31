# ConfigRestoreData

If a [script add-in](/Manual/scripting/script_add-ins/README.md) implements the **[OnConfigRestore](../scripting_events/onconfigrestore.md)** event, the method receives a **ConfigRestoreData** object when the configuration is restored from a backup.

This method will be called twice; once before the restore begins, and once after Opus has restarted with the new configuration. The `step` property tells you which invocation this is.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
location</td><td>

*object*:**[Path](path.md)**</td><td>

Returns the path of the staging area that backed up Opus configuration has been extracted to. Any changes your script makes to files in the staging folder will be imported into the Opus configuration. Note that this property is only provided if `step` equals "before".
</td></tr><tr><td>
step</td><td>

*string*</td><td>
Returns either "before" or "after", to indicate which invocation of the event this is.
</td></tr></tbody>
</table>

