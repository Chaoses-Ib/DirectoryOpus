# Image

The **Image** object represents an image file or icon to be displayed in a [script dialog](/Manual/scripting/script_dialogs/README.md). You can load an image or icon using the **[DOpus](dopus.md).LoadImage** or **[Script](script.md).LoadImage **methods. It can be displayed using a static control, or assigned as the dialog's icon.  

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
bitcount</td><td>

*int*</td><td>
Returns the bit count of the loaded image.
</td></tr><tr><td>
height</td><td>

*int*</td><td>
Returns the height of the loaded image.
</td></tr><tr><td>
width</td><td>

*int*</td><td>
Returns the width of the loaded image.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
SetClip</td><td>

*none*</td><td>

*bool*</td><td>
Copies the image's bitmap data into the Windows clipboard. Returns boolean success.
</td></tr></tbody>
</table>

