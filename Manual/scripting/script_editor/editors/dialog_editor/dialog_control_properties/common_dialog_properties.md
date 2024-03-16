# Common Dialog Properties

There are several properties that all (or some) controls have in common.

- **Name**: All controls and dialogs have a name. This name will be used by your script to refer to the control, for example to read or change its value. Control names must be unique within the one dialog. When you add a control a default name will be assigned to it but you will probably want to change this to make it easier to identify the control in your script.
- **Title**: Many controls have a title, which is a string displayed in the user interface. The dialog itself has a title string which is displayed in the title bar at the top of the dialog window. For some controls (e.g. the edit control) the title string lets you provide the default value of the control.  
    
  Use an ampersand (**&**) in the title to give a control a mnemonic (keyboard accelerator). For example, a *Check Box* control with the label **A&utomatic** would appear as **A<u>u</u>tomatic** and allow the user to press **Alt + U** to activate the control. For controls like the *Edit control* (that don’t display a title) you can assign a mnemonic using a separate *Static text* control as a label. If you want an actual ampersand to appear in the title you need to double it (e.g. **This && That**).
- **Visible**: Set to **True** if the control should initially be visible in the dialog. If set to **False**, the control won’t appear until you make it visible in your script.
- **Enable**: Set to **True** if the control should initially be enabled (able to receive user input). If set to **False** the control will be disabled until you enable it in your script.
- **Resize**: Controls how the control handles resizing (if the parent dialog is set to allow resizing). The options available are:
  - **X**: The control will move relative to the width of the dialog.
  - **Y**: The control will move relative to the height of the dialog.
  - **W**: The control will grow horizontally (in width) relative to the width of the dialog.
  - **H**: The control will grow vertically (in height) relative to the height of the dialog.
  - **Shared Width**: Two or more controls can share the width of the dialog. When the dialog is resized each control will grow or shrink by an equal amount.
  - **Shared Height**: Two or more controls can share the height of the dialog. When the dialog is resized each control will grow or shrink by an equal amount.
  - **Text**: For markup text and static controls. When combined with width resizing, this causes the control to automatically adjust its height as necessary to show the whole text, and controls below it will automatically move up or down.
- **Case**: Some controls (like the edit control) have a **Case** property which lets you force the value of the control to be all upper- or all lower-case.
- **Align Text**: Some controls (like the edit control) have this property, which lets you change the text alignment from the default (left) to center or right.
- **Vertical Align**: Controls vertical alignment of the control contents (top, middle, bottom). Currently only supported by the *Static text* control.
