# Button Properties

The specific properties applicable to the *Button* control are:

- **Default Button**: Set to **True** to make this button the “default button” for the control. The default button is the one which is triggered when the user pushes the Return key. If you have the automatic **OK** button enabled in the dialog properties, normally that button would be the default.
- **Right Button**: If set to **True** the control will respond to right mouse button clicks as well as left.
- **Close Dialog**: Set to **True** to make this button close the dialog when it’s clicked. If set to **False**, nothing will happen automatically when the user clicks the button, but your script will be notified.
- **Return Value**: If **Close Dialog** is set to **True**, this lets you specify the value that the dialog returns when it closes. For example, you might have a three buttons that all close the dialog – specifying a different return value lets you tell which one the user clicked after the dialog closes.
- **Border**: If **True** the button will display a border. If set to **False** the button appears flat, without a border, except when the mouse is over it.
- **Image**: Displays an image on the button. You can specify an external filename or the name of an internal icon (e.g. `#about` for the internal About icon). At runtime you can change this with the `Control.image` property.
- **Label**: If set to true, when showing an image the button will also show a label.
