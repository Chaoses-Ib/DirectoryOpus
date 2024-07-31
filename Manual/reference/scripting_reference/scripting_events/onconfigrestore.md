# OnConfigRestore

The **OnConfigRestore** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when the Opus configuration is being restored from a backup.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnConfigRestore
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[ConfigRestoreData](../scripting_objects/configrestoredata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The **ConfigRestoreData.location** property identifies the staging folder that the Opus configuration is being restored from. You can make changes to files in this folder before returning, and any modifications you make will be imported into the current configuration.
</td></tr></tbody>
</table>

