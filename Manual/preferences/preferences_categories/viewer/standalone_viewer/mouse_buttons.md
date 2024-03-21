# Mouse Buttons

These options affect the [standalone viewer](/Manual/additional_functionality/viewing_images/README.md) - the Opus viewer that opens in a separate window. Options that affect the [Viewer Pane](/Manual/basic_concepts/the_lister/viewer_pane.md) are configured on a [separate page](../viewer_pane.md).

##### Left mouse button

This lets you control what the left mouse button does when you click it in on the image. The options you can choose from the drop-down are:

- **Select clipboard region**: Lets you click and drag to select a region of the image to copy to the clipboard (or to crop to). Holding the <kbd>Shift</kbd> key changes the behavior to *Scroll image*.
- **Scroll image**: Lets you pan around an image that's larger than the viewer window by click and drag. Holding the <kbd>Shift</kbd> key changes the behavior to *Select clipboard region*.
- **Expand/scroll image**: If the image is displayed at a reduced size (e.g. the zoom level is set to *Fit to Page*) then clicking and holding the mouse button will expand the image to full size.
- **Advance to next image**: Advances the viewer to the next image in the picture list.
- **Toggle Full Screen mode**: Clicking the button will toggle full-screen mode on or off.
- **Close Viewer**: Clicking the mouse button will close the viewer window.
- **Toggle Slideshow**: Clicking the button will toggle slideshow mode on or off.
- **Run a command**: Clicking the button will run the specified Opus command in the context of the viewer.
- **Script event**: Clicking the button will trigger any script add-ins that implement the [OnViewerEvent](/Manual/reference/scripting_reference/scripting_events/onviewerevent.md) script event.

Below the drop-down is the following options:

- **Click left/right edges to go to previous/next picture**: Clicking the left and right edges of the window will advance to the next or previous image irrespective of the actual setting for the mouse button. You can control the percentage of the window width that Opus considers to be "the edge" (the default is 20%).

##### Left double-click

This lets you control what the left button does when you **double-click** it on the image; the options are mostly the same as for the **Left mouse button** setting except you can't choose **Select clipboard region** or **Scroll image** for double-click.

##### Middle button

This lets you define what the middle mouse button does when you click it on the image; the options are the same as for the **Left mouse button** setting.

##### Mouse wheel

This lets you control what the mouse wheel does when you turn it over the viewer window. Note that the viewer ignores this setting when viewing some file types. For example, when viewing a text file the wheel always scrolls up and down. The options in the drop-down are:

- **Scroll image**: The mouse wheel will scroll the current image up and down. Hold the <kbd>Alt</kbd> key to scroll left and right instead.
- **Advance to next image**: Scrolling the mouse wheel over the viewer will have the effect of moving forwards and backwards through the current picture list.
- **Zoom**: The mouse wheel will zoom in and out of the image. If one of the other options is selected you can still zoom with the wheel by holding down the <kbd>Ctrl</kbd> key.

Beneath the drop-down is the **Accumulate wheel movements** option, which is enabled when **Advance to next image** is selected. This option causes wheel movements to accumulate and several quick wheel movements can move you several places forward or back in the list of images without loading each image in between. (On mice with 'smooth' wheels, this could make it easy to accidentally skip images by turning the wheel too much).
