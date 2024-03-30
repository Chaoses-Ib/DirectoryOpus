# OnStartup

The **OnStartup** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when Opus starts up.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnStartup
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[StartupData](../scripting_objects/startupdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

This event is only triggered when Opus starts up, therefore only script add-ins that are already installed will receive it. If a script is installed when Opus is already running it won't receive **OnStartup** until the next time Opus is started.
</td></tr></tbody>
</table>

