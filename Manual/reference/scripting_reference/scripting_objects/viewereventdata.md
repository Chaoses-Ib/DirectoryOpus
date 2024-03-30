# ViewerEventData

If a script implements the **[OnViewerEvent](../scripting_events/onviewerevent.md)** event, it receives a **ViewerEventData** object whenever certain events occur in a standalone [image viewer](/Manual/additional_functionality/viewing_images/README.md).

  

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
event</td><td>

*string*</td><td>

Returns a string indicating the event that occurred. The events currently defined are:

- **create**: A new viewer has been created.
- **destroy**: A viewer window has been destroyed.
- **load**: A new image has been loaded in a viewer. The **item** property can be used to find out which file was loaded.
- **setfocus**: The viewer window has received focus (gone active).
- **killfocus**: The viewer window has lost focus (gone inactive).
- **click**: The left button was clicked on the image (requires mouse buttons to be set to trigger *Script event* in **Preferences / Viewer / Mouse Buttons**).
- **dblclk**: The left button was double-clicked on the image.
- **mclick**: The middle button was clicked on the image.
</td></tr><tr><td>
item</td><td>

*object:***[Item](item.md)**</td><td>

For the **load** event, returns an **[Item](item.md)** object representing the newly loaded image.
</td></tr><tr><td>
viewer</td><td>

*object:***[Viewer](viewer.md)**</td><td>

Returns a **[Viewer](viewer.md)** object representing the viewer the event occurred in.
</td></tr><tr><td>
x</td><td>

*int*</td><td>
For the click events, returns the x coordinate within the viewer window that the click occurred.
</td></tr><tr><td>
y</td><td>

*int*</td><td>
For the click events, returns the y coordinate within the viewer window that the click occurred.
</td></tr><tr><td>
w</td><td>

*int*</td><td>
For the click events, returns the width of the viewer window.
</td></tr><tr><td>
h</td><td>

*int*</td><td>
For the click events, returns the height of the viewer window.
</td></tr></tbody>
</table>

