# ListerResizeData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnListerResize](../scripting_events/onlisterresize.md)** event, the method receives a **ListerResizeData** object whenever a Lister window is resized.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
action</td><td>

*string*</td><td>

Returns a *string* indicating the resize action that occurred. This will be one of the following strings: *resize*, *minimize*, *maximize*, *restore.*
</td></tr><tr><td>
width</td><td>
int</td><td>
Returns the new width of the Lister in pixels.
</td></tr><tr><td>
height</td><td>
int</td><td>
Returns the new height of the Lister in pixels.
</td></tr><tr><td>
lister</td><td>

*object:***[Lister](lister.md)**</td><td>

Returns a **[Lister](lister.md)** object representing the Lister that was resized.
</td></tr></tbody>
</table>

