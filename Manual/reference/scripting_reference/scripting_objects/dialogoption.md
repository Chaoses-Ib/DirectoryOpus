# DialogOption

The **DialogOption** object is used with the options property of the **[Dialog](dialog.md)** object. A collection of five of these is provided, and any you initialize will be displayed to the user as physical checkbox controls.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
label</td><td>

*string*</td><td>
Set this to the desired label of the checkbox.
</td></tr><tr><td>
state</td><td>

*bool*</td><td>

Set this to the desired initial state of the checkbox. When the **Dialog.Show** method returns, you can read this property to find out the state the user chose.
</td></tr></tbody>
</table>

