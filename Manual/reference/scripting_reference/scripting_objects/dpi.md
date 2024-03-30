# DPI

The **DPI** object is a helper object that provides a number of methods and properties relating to the system DPI setting. For example, you can use it to convert a pixel width into one scaled for the current system DPI. The **DPI** object is returned via the **[DOpus](dopus.md).DPI** property.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
dpi</td><td>

*int*</td><td>
Returns the system DPI setting as a “dpi value” (e.g. 96, 192).
</td></tr><tr><td>
factor</td><td>

*int*</td><td>
Returns the DPI settings as a “scale factor” (e.g. 100, 125, 200).
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Divide</td><td>

\<int:value\></td><td>

*int*</td><td>

Divides the provided size by the system DPI; e.g. if the system DPI was set to 150%, **DPI.Divide(60)** would return **40.**
</td></tr><tr><td>
Scale</td><td>

\<int:value\></td><td>

*int*</td><td>

Scales the provided size by the system DPI; e.g. if the system DPI was set to 200%, **DPI.Scale(75)** would return **150**.
</td></tr></tbody>
</table>

