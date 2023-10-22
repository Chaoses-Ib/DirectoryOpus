# DialogOption

The **DialogOption** object is used with the options property of the **[Dialog](dialog.md)** object. A collection of five of these is provided, and any you initialize will be displayed to the user as physical checkbox controls.

| Property Name | Return Type | Description |
| --- | --- | --- |
| label | *string* | Set this to the desired label of the checkbox. |
| state | *bool* | Set this to the desired initial state of the checkbox. When the **Dialog.Show** method returns, you can read this property to find out the state the user chose. |

