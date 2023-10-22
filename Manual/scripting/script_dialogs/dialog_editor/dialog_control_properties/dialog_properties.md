# Dialog Properties To edit the properties of the dialog, click on it outside of any control. The specific properties applicable to the dialog are:

- **Base Language**: Specifies the “base language” of the dialog, that is the native language you’re designing it in. You can use the language overlay feature (described later) to provide additional translations of your dialog.
- **Font Face**: Use this to override the default font that the dialog uses.
- **Font Size**: Lets you control the font size used in the dialog. Dialog controls are positioned and sized using “dialog units” which are scaled with the size of the font, so you can change font size without having to re-lay out your dialog.
- **Opacity**: Sets the initial opacity of the dialog, from **255** (totally opaque) to\*\* 0\*\* (totally transparent). The opacity can be modified after the dialog has been created using the **Dialog.opacity** property.
- **OK Button**: Set to **True** to get a default **OK** button in the bottom-right of the dialog. If the user clicks the **OK** button or pushes the **Return** key your dialog will close. This option lets you get this standard Windows UI behaviour without having to add the button and code it yourself.
- **Cancel Button**: Set to **True** to get a default **Cancel** button. If the user clicks the **Cancel** button or pushes the **Escape** key your dialog will close.
- **Resizable**: Set to **True** to allow your dialog to be resizable. If you make your dialog resizable you also need to configure the **Resize** property for any controls that you want to respond to resize events.
- **Accept Drops**: Set to **True** to allow users to drag and drop files to your dialog. Your script will receive a **drop** event along with information about the dropped files.
