# OnAboutScript

The **OnAboutScript** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) to display an "about" dialog to the user. It is triggered when the user clicks the *About* button for a script on the **[Toolbars / Scripts](/Manual/preferences/preferences_categories/toolbars/scripts.md)** page in Preferences.

| **Method Name:** | OnAboutScript |
| --- | --- |
| **Argument Type:** | **[AboutData](../scripting_objects/aboutdata.md) ** |
| **Return Type:** | *none* |
| **Description:** | The usual implementation for this event would use the **AboutData.window** parameter to display a dialog using the **[Dialog](../scripting_objects/dialog.md)** object. |

