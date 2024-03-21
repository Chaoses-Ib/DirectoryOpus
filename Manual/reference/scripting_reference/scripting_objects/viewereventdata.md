# ViewerEventData

If a script implements the **[OnViewerEvent](../scripting_events/onviewerevent.md)** event, it receives a **ViewerEventData** object whenever certain events occur in a standalone [image viewer](/Manual/additional_functionality/viewing_images/README.md).

  

| Property Name | Return Type | Description |
| --- | --- | --- |
| event | *string* | Returns a string indicating the event that occurred. The events currently defined are:<br /><br />- **create**: A new viewer has been created.<br />- **destroy**: A viewer window has been destroyed.<br />- **load**: A new image has been loaded in a viewer. The **item** property can be used to find out which file was loaded.<br />- **setfocus**: The viewer window has received focus (gone active).<br />- **killfocus**: The viewer window has lost focus (gone inactive).<br />- **click**: The left button was clicked on the image (requires mouse buttons to be set to trigger *Script event* in **Preferences / Viewer / Mouse Buttons**).<br />- **dblclk**: The left button was double-clicked on the image.<br />- **mclick**: The middle button was clicked on the image. |
| item | *object:***[Item](item.md)** | For the **load** event, returns an **[Item](item.md)** object representing the newly loaded image. |
| viewer | *object:***[Viewer](viewer.md)** | Returns a **[Viewer](viewer.md)** object representing the viewer the event occurred in. |
| x | *int* | For the click events, returns the x coordinate within the viewer window that the click occurred. |
| y | *int* | For the click events, returns the y coordinate within the viewer window that the click occurred. |
| w | *int* | For the click events, returns the width of the viewer window. |
| h | *int* | For the click events, returns the height of the viewer window. |

