# SystemSettingChangeData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnSystemSettingChange](../scripting_events/onsystemsettingchange.md)** event, the method receives a **SystemSettingChangeData** object when various system settings change.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
type</td><td>

*string*</td><td>

Returns a string indicating the setting that changed. Settings are:

|                         |                                                                                                                                                                                                                                                               |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **theme**               | The Windows theme (visual style) has changed                                                                                                                                                                                                                  |
| **colorset**            | Opus has changed from light to dark mode or vice versa                                                                                                                                                                                                        |
| **environment**         | System environment variables have been changed                                                                                                                                                                                                                |
| **dwmcomposition**      | Indicates that Windows DWM composition has been turned on or off.                                                                                                                                                                                             |
| **dwmcolorization**     | Indicates that Windows DWM colorization has been changed.                                                                                                                                                                                                     |
| **intl**                | The system locale has changed.                                                                                                                                                                                                                                |
| **userinteractionmode** | The system input method has changed (from mouse to touch or vice versa). The current method can be queried via the **[SysInfo](sysinfo.md).TouchInput** method.                                                                                                  |
| **spacingscheme**       | Indicates that the [UI spacing scheme has changed](/Manual/preferences/preferences_categories/user_interface/spacing.md). The new scheme name is available in the **name** property. You can also query the scheme using the **[DOpus](dopus.md).spacingscheme** property. |
| **windowmetrics**       | System window metrics have changed (e.g. font size).                                                                                                                                                                                                          |
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Returns a name string for supported settings.
</td></tr></tbody>
</table>

