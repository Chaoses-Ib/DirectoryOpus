# Image

The **Image** object represents an image file or icon to be displayed in a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md). You can load an image or icon using the **[DOpus](dopus.md).LoadImage** or **[Script](script.md).LoadImage **methods. It can be displayed using a static control, or assigned as the dialog's icon.  

| Property Name | Return Type | Description |
| --- | --- | --- |
| bitcount | *int* | Returns the bit count of the loaded image. |
| height | *int* | Returns the height of the loaded image. |
| width | *int* | Returns the width of the loaded image. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| SetClip | *none* | *bool* | Copies the image's bitmap data into the Windows clipboard. Returns boolean success. |

