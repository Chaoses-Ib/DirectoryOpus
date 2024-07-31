# OnConfigBackup

The **OnConfigBackup** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when the Opus configuration is being backed up.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnConfigBackup
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[ConfigBackupData](../scripting_objects/configbackupdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The **ConfigBackupData.location** property identifies the staging folder that the Opus configuration has been written to. You can make changes to files in this folder before returning, and any modifications you make will be included in the configuration backup.
</td></tr></tbody>
</table>

