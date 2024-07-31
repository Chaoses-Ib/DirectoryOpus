# Viewers

The **Viewers** object is a collection of all currently open standalone [image viewers](/Manual/additional_functionality/viewing_images/README.md). It can be obtained via the **[DOpus](dopus.md).viewers** property.

  

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*collection:***[Viewer](viewer.md)**</td><td>
Lets you enumerate the currently open viewers.
</td></tr><tr><td>
lastactive</td><td>

*object:***[Viewer](viewer.md)**</td><td>

Returns a **[Viewer](viewer.md)** object representing the most recently active viewer window.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

The first time a script accesses the **DOpus.viewers** property, a snapshot is taken of all currently open viewers. If anything opens or closes viewers after this, these changes will not be reflected by snapshot unless you re-synchronize it by calling the **Update** method.
</td></tr></tbody>
</table>

