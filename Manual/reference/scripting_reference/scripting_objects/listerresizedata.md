# ListerResizeData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnListerResize](../scripting_events/onlisterresize.md)** event, the method receives a **ListerResizeData** object whenever a Lister window is resized.

| Property Name | Return Type | Description |
| --- | --- | --- |
| action | *string* | Returns a *string* indicating the resize action that occurred. This will be one of the following strings: *resize*, *minimize*, *maximize*, *restore.* |
| width | int | Returns the new width of the Lister in pixels. |
| height | int | Returns the new height of the Lister in pixels. |
| lister | *object:***[Lister](lister.md)** | Returns a **[Lister](lister.md)** object representing the Lister that was resized. |

