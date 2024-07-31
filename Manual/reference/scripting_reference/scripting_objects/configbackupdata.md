# ConfigBackupData

If a [script add-in](/Manual/scripting/script_add-ins/README.md) implements the **[OnConfigBackup](../scripting_events/onconfigbackup.md)** event, the method receives a **ConfigBackupData** object when the Opus configuration is backed up.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
location</td><td>

*object*:**[Path](path.md)**</td><td>
Returns the path of the staging area that the Opus configuration has been written to. The configuration backup file will be created from the files in this folder. Any changes your script makes to files in the staging folder will be included in the backup.
</td></tr><tr><td>
output_dir</td><td>

*object*:**[Path](path.md)**</td><td>
Returns the path that the configuration backup is being saved to.
</td></tr><tr><td>
output_name</td><td>

*string*</td><td>
Returns the name the configuration backup is being saved as.
</td></tr></tbody>
</table>

