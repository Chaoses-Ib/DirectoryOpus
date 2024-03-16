# Dialog

The **Dialog** object allows you to display dialogs that prompt the user for confirmation, allow them to input text strings or passwords, and select checkbox options or choose from a drop-down list. You can also use this object to display a popup menu on screen.

You can create a **Dialog** object from the **[DOpus](dopus.md).Dlg**, **[Lister](lister.md).Dlg**, **[Tab](tab.md).Dlg**, **[Func](func.md).Dlg** and **[Command](command.md).Dlg** methods.

See the [Example Scripts](/Manual/scripting/example_scripts/RAEDME.md) section for an example of its use.

There are two different ways to use the **Dialog** object. You can either:

- Use the one-shot methods (**Folder**, **GetString**, **Multi**, **Open**, **Request** or **Save**) to display a simple dialog of various types, or
- Configure the dialog first by setting the values of the various properties, and then call the **Show** function to display it. This method also lets you create and use [script dialogs](/Manual/scripting/script_dialogs/RAEDME.md).

The one-shot methods accept several parameters but are generally not as flexible as building up the dialog and then calling **Show**.

| Property Name | Return Type | Description |
| --- | --- | --- |
| buttons | *string* | Specifies the buttons that are displayed at the bottom of the dialog. These buttons are used to close the dialog. The **Show** method returns a value indicating which button was chosen (and this value is also available in the **result** property).<br /><br />Multiple button strings must be separated with vertical bar characters (\|). If a button has more than one button then by definition the last one is the "cancel" button. For example:<br /><br />    dlg.buttons = "OK|Retry|Cancel"<br /><br />To specify *accelerators* for the buttons prefix the desired key with an ampersand (&) character. For example:<br /><br />    dlg.buttons = "&OK|&Retry|&Cancel"<br /><br />Buttons can also have drop-down menus attached to them, by separating the drop-down items with plus signs (+). For example:<br /><br />    dlg.buttons = "OK|Retry+Retry All|Cancel"<br /><br />Within drop-down menus, you can specify that certain menu items can be accessed directly from the main button by holding <kbd>Shift</kbd>, <kbd>Ctrl</kbd> or <kbd>Shift+Ctrl</kbd>. This is done by adding an equals sign and then the label the button should display when the key is held down (usually an abbreviated version of the menu item label, or a repetition of the label itself if it is already short enough). The keys are automatically assigned and you can only do this for at most three items. For example:<br /><br />\<WRAP prewrap\><br /><br />    dlg.buttons = "OK|Retry+Retry All=Retry All|Skip+Skip if same modified time=Skip Same Time|Cancel"<br /><br />\</WRAP\> |
| choices | *object:***[Vector](vector.md)***(string)*  <br />or *array(string)* | This property uses either a **[Vector](vector.md)** or an array of strings to provide a list of multiple options that can be shown to the user. The list can be presented in one of three ways:<br /><br />- **Drop-down list**: By default, the dialog will display a drop-down list allowing the user to select one option. The index of the chosen selection is available via the **selection** property when the **Show** method returns.<br />- **Checkbox list**: If the **list** property is also given the dialog will display a scrolling list of items, each with a checkbox allowing it to be turned on or off.<br />- **Popup menu**: If the **menu** property is also given, a popup menu will be displayed at the current mouse coordinates. Use a single hyphen ("-") as a menu label to insert a separator.<br /><br />When shown as a checkbox list the dialog is resizable; you can set the initial size using the **cx** and **cy** properties (and retrieve them afterwards if you want to save the size). |
| confirm | *bool* | In a text entry dialog (i.e. the **max** property has been specified) setting **confirm** to **True** will require that the user types the entered text again (in a second text field) to confirm it (e.g. for a password). |
| cx | *int* | For [script dialogs](/Manual/scripting/script_dialogs/RAEDME.md) marked as resizable, this property lets you override the width of the dialog defined in the resource - although note you can't resize a dialog smaller than its initial size. |
| cy | *int* | For [script dialogs](/Manual/scripting/script_dialogs/RAEDME.md) marked as resizable, this property lets you override the height of the dialog defined in the resource - although note you can't resize a dialog smaller than its initial size. |
| defvalue | *string* | In a text entry dialog (i.e. the **max** property has been specified) this property allows you to initialize the text field with a default value.<br /><br />(Old scripts may use "default" instead of "defvalue"; this is deprecated because it does not work in JScript where "default" is a reserved keyword.) |
| defid | *int* | Allows you to change the default button (i.e. the action that will occur if the user hits enter) in the dialog. Normally the first button is the default - this has a **defid** of 1. The second button would have a **defid** of 2, and so on. If a dialog has more than one button then by definition the very last button is the "cancel" button, and this has a **defid** of 0. |
| detach | *bool* | Set to **True** if you want a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md) to run in “detached” mode, where your script provides its [message loop](/Manual/scripting/script_dialogs/the_dialog_message_loop/RAEDME.md). |
| disable_window | *object:***[Lister](lister.md)**  <br />or *object:***[Tab](tab.md)**   <br />*or object:***Dialog\\** or *int* | Use this to cause the dialog to automatically disable another window when it's displayed. The user will be unable to click or type in the disabled window until the dialog is closed. Normally if you use this you would set this to the same value as the **window** property.<br /><br />You can provide either a **[Lister](lister.md)** or a **[Tab](tab.md)** object, or another **Dialog**. If you are showing this dialog in response to the **[OnAboutScript](../scripting_events/onaboutscript.md)** event, you can also pass the value of the **[AboutData](aboutdata.md).window** property. |
| icon | *string* or  <br />*object:***[Image](image.md)** | Displays one of several standard icons in the top-left corner of the dialog, which can be used, for example, to indicate the severity of an error condition. The valid values for this property are *warning*, *error*, *info* and *question*.<br /><br />When used with a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md) this property lets you control the icon shown in the dialog's title bar. In this instance, instead of a string you can also provide an **[Image](image.md)** object that you obtained from the **[DOpus](dopus.md).LoadImage** or **[Script](script.md).LoadImage** methods. Note that the image must have been loaded from a **.ico** file. |
| input | *string* | In a text entry dialog, this property returns the text string that the user entered (i.e. once the **Show** method has returned). |
| language | *string* | Set this property to create a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md) in a particular language (if one or more [language overlays](/Manual/scripting/script_editor/editors/dialog_editor/language_overlays.md) have been provided), rather than the currently selected language. |
| list | *object:***[Vector](vector.md)***(bool)*  <br />or *array(bool)\\* or// int// | In conjunction with the **choices** property, this will cause the choices to be presented as a checkbox list. You can initialize this **Vector** or array with the same number of items as the choices property, and set each one to **True** or **False** to control the default state of each checkbox. Or, simply set this value to\*\* 0\*\* to activate the checkbox list without having to initialize the state of each checkbox.<br /><br />When the **Show** method returns, this property will return a **[Vector](vector.md)** of *bools* that provide the state of each checkbox as set by the user. |
| max | *int* | This property enables text entry in the dialog - a text field will be displayed allowing the user to enter a string. Set this property to the maximum length of the string you want the user to be able to enter (or **0** to have no limit).<br /><br />When the **Show** method returns the text the user entered will be available in the **input** property. |
| menu | *object:***[Vector](vector.md)***(int)*  <br />or *array(int)*  <br />or *int* | In conjunction with the **choices** property, this will cause the choices to be presented as a popup menu rather than in a dialog. The menu will be displayed at the current mouse coordinates.<br /><br />You can initialize this **Vector** or array with the same number of items as the choices property, and set each one to a value representing various flags that control the appearance of the menu item. The available flags are as follows - their values must be added together if you need to specify more than one flag per item.<br /><br />|       |                                                         |<br />|-------|---------------------------------------------------------|<br />| **1** | bold (indicates the default item)                       |<br />| **2** | checked (a checkmark will appear next to the item)      |<br />| **4** | radio (a radio button will appear next to the item)     |<br />| **8** | disabled (the user will not be able to select the item) |<br /><br />You can also simply set this value to **0** or **1** to activate the popup menu without having to provide flags for each item (if set to **1**, the top item in the menu will appear bolded).<br /><br />The **Show** method returns the index of the menu item the user chose (with **1** being the first item), or **0** if the menu was cancelled. |
| message | *string* | Specifies the message text displayed in the dialog. |
| opacity | *int* | For [script dialogs](/Manual/scripting/script_dialogs/RAEDME.md) this property retrieves or sets the current dialog opacity level, from **0** (totally transparent) to **255** (totally opaque). |
| options | *collection:***[DialogOption](dialogoption.md)** | This is a collection of five options that will be displayed as checkboxes in the dialog. Unlike the **choices** / **list** scrolling checkbox list, these options are displayed as physical checkbox controls. By default the five checkboxes are uninitialized and won't be displayed, but if you assign a label to any of them they will be shown to the user.<br /><br />When the **Show** method returns you can obtain the state of the checkboxes using the **state** property of each **[DialogOption](dialogoption.md)** object. |
| password | *bool* | In a text entry dialog, set this property to **True** to make the text entry field a password field. In a password field the characters the user enters are not displayed. |
| position | *string* | When used with a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md) this property lets you control the dialog's position on screen. Accepted values are:<br /><br />|              |                                                                   |<br />|--------------|-------------------------------------------------------------------|<br />| **center**   | center the dialog over the parent window (the default)            |<br />| **absolute** | specify an absolute position using the **x** and **y** properties |<br />| **parent**   | position relative to the parent window (using **x** and **y**)    |<br />| **monitor**  | position relative to the current monitor (using **x** and **y**)  |<br /><br />Except when set to "center" the **x** and **y** properties can be used to adjust the dialog's position. |
| position_fix | *bool* | By default, Opus checks the size and position of your dialog just before it opens and fixing them if they would place any of the dialog off-screen. Positioning a dialog off-screen is usually an accident caused by saving window positions on one system and restoring them on another with different monitor resolutions or arrangements. In the rare cases where you want your dialog to open off-screen, where the user cannot see some of all of it, set this property to **False**. |
| result | *int* | This property returns the index of the button chosen by the user to close the dialog. The left-most button is index **1**, the next button is index **2**, and so on. If a dialog has more than one button then by definition the last (right-most) button is the "cancel" button and so this will return index **0**.<br /><br />If any buttons have associated drop-down menus then the contents of the menus also contribute to the index value. For example, if button index 2 has an additional item in a drop-down menu, then that item would be index 3, and the next button would be index 4. |
| select | *bool* | In a text entry dialog, set this property to **True** to automatically select the contents of the input field (as specified by the **defvalue** property) when the dialog opens. |
| selection | *int* | In a drop-down list dialog (one with the **choices** property set without either **list** or **menu**), this property returns the index of the item chosen from the drop-down list after the **Show** method returns. |
| sort | *bool* | Set this property to **True** if the list of choices given by the **choices** property should be sorted alphabetically. |
| template | *string* | Lets you create a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md). The **template** property can be set to the name of the script dialog to display (as defined in your script resources), or a string that contains raw XML defining the dialog. |
| title | *string* | Specifies the title text of the dialog. |
| top | bool | Set this property to **True** to make the dialog "top level", or **False** to allow it to go behind other non-top level windows. |
| want_close | *bool* | Set this property to **True** if you want the script dialog to generate close events in your message loop when the user clicks the window close button. You'll need to close the dialog yourself using the **EndDlg** method. |
| want_resize | *bool* | Set this property to **True** if you want the script dialog to generate **resize** events in your message loop when the user resizes the dialog. |
| window | *object:***[Lister](lister.md)**  <br />or *object:***[Tab](tab.md)**  <br />or *object:***Dialog**  <br />or *int* | Use this to specify the parent window of the dialog. The dialog will appear centered over the top of the specified window. You can provide either a **[Lister](lister.md)** or a **[Tab](tab.md)** object, or another **Dialog**. If you are showing this dialog in response to the **[OnAboutScript](../scripting_events/onaboutscript.md)** event, you can also pass the value of the **[AboutData](aboutdata.md).window** property.<br /><br />You only need to set this property if you obtain the **Dialog** option from the **[DOpus](dopus.md).Dlg** method. If the **Dialog** object comes from one of the other objects (e.g. **[Tab](tab.md).Dlg**) then its parent window will already be set to the window which launched the action your script is responding to. |
| x | *int* | Specifies the x-position of a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md). Use the **position** property to control how the position is interpreted. After the dialog has been displayed you can change this property to move the dialog around on-screen. |
| y | *int* | Specifies the y-position of a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md). Use the **position** property to control how the position is interpreted. After the dialog has been displayed you can change this property to move the dialog around on-screen. |

\<commandtable columns="4" id="cmdtable_2"\> \$\$ Method Name \$\$ **Arguments** \$\$ Return Type \$\$ Description \$\$ AddHotkey \$\$ \<string:name\>  
\<string:key\> \$\$ *none* \$\$ Creates a hotkey (or keyboard accelerator) for the specified key combination. When the user presses this key combination in your dialog, a **hotkey** event will be triggered.

The name parameter is a name you assign that lets you identify the hotkey. The key parameter specified the actual key combination; this can optionally combine the qualifiers **ctrl**, **shift** and **alt** with a character or name of a special key. For example, **ctrl+t** or **alt+shift+F7**. \$\$ AutoSize \$\$ *none* \$\$ *none* \$\$ If a dialog has auto-sizing controls that depend on the sizes of other controls, and you make changes to their sizes at runtime, you can call this method to force the dialog to recalculate all relative control sizes once you've made the required changes. \$\$ CancelWatchDir \$\$ \<string:id\> \$\$ *none* \$\$ Cancels folder or file change monitoring previously established by a call to the **WatchDir** method. The **id** parameter is the ID you assigned to your watcher when it was created. \$\$ Create \$\$ *none* \$\$ *none* \$\$ When creating a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md), calling this method creates the underlying dialog but does not display it. This lets you create the dialog and then initialize its controls before it is shown to the user.

Using **Create** implies a [detached dialog](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.md); the **detach** property will be set **True** automatically. However, you can call **RunDlg** afterwards if you don't need a custom message loop and just want to set up some controls before displaying the dialog.

Once the dialog has been created and its controls initialized, you should call **Show** or **RunDlg** to make it visible to the user. It will also go visible at the first **GetMsg** call if it hasn't already been shown. \$\$ CreateFont \$\$ \<string:name\>  
\[\<int:size\>\]  
\[\<string:styles\>\] \$\$ *int* \$\$ Creates a font object that can be given to dialog controls to make them use a non-standard font. The *name* parameter specifies the name of the font (e.g. "Arial") - you can also use "\*" which means the default dialog font. The *size* parameter specifies the desired point size (use 0 to get the default dialog font size). The *styles* string can consist of one or more characters indicating the desired font style - "b" for bold, "i" for italic, "u" for underline.

The return value can be used with the **[Control](control.md).SetFont** method.

Fonts you create are automatically destroyed when the dialog closes but if you want to delete them manually to free up resources, use the **DestroyFont** method. \$\$ Control \$\$ \<string:name\>  
\[\<string:dialog\>\]  
\[\<string:tab\>\] \$\$ *object:***[Control](control.md)**  \$\$ Returns a **[Control](control.md)** object corresponding to one of the controls on a script dialog. The control is identified by its *name*, as defined in the script dialog resource.

The optional second and third parameters are only used when the control is in a *tab control* (that is, when it's in a dialog that's a child of another dialog). The *dialog* parameter specifies the name of its parent dialog. The *tab* parameter specifies the name of the tab control hosting the child dialog. You would only need to specify the name of the tab if you have multiple tab controls and the same dialog is hosted inside more than one of them (this would be quite a rare occurrence).

Note that none of the controls will exist until **Create** has been called. \$\$ DelHotkey \$\$ \<string:name\> \$\$ *none* \$\$ Deletes a hotkey you previously created with the **AddHotkey** method. \$\$ Drag \$\$ *object:***[Items](items.md)**  
\<string:actions\> \$\$ *string* \$\$ Allows the user to drag and drop one or more files from your dialog (and drop them in another window or application).

You would usually call this in response to a **drag** event you receive from a **static** or list view control.

The first parameter is an **[Items](items.md)** object representing the files to be dragged. (You can also pass a **[Vector](vector.md)** of **[Item](item.md)** or **[Path](path.md)** objects, or full path strings, instead of an **[Items](items.md)** object. Or a **[StringSet](stringset.md)** or **[UnorderedSet](unorderedset.md)** of full path strings.)

The optional second parameter lets you control which actions are available. This should be a string containing one or more of **copy**, **move**, **link**. The default action can be indicated by prefixing it with a \* (e.g. **copy,\*move,link**). If you don't specify this parameter the default is to only allow **copy**.

The string this method returns indicates the result of the drag. For a left button drag, this will be "copy", "move", "link" or "drop". For a right-button drag it will always be "drop". If the drag is cancelled it will return "cancel". \$\$ DestroyFont \$\$ \<int:id\> \$\$ *none* \$\$ Destroys the specified font using the ID that was returned by the **CreateFont** method. \$\$ EndDlg \$\$ \<int:result\> \$\$ *none* \$\$ Ends a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md) running in detached mode. Normally dialogs end automatically when the user clicks the close button or another button that has its **Close Dialog** property set to **True**. This method lets you end a dialog under script control. The optional parameter specifies the result code that the **Dialog.result** property will return. \$\$ Folder \$\$ \<string:title\>  
\<string:default\>  
\<bool:expand\>  
\<object:window\> \$\$ *object:***[Path](path.md)**  \$\$ Displays a "Browse for Folder" dialog letting the user select a folder. The optional parameters are:

- *title* - specify title of the dialog
- *default* - specify the default path selected in the dialog
- *expand* - specify **True** to automatically expand the initial path
- *window* - specify parent window for the dialog (a **[Lister](lister.md)** or a **[Tab](tab.md)**). If not specified, the **Dialog** object's **window** property will be used.

A **[Path](path.md)** object is returned to indicate the folder chosen by the user. This object will have an additional **result** property that will be **False** if the user cancelled the dialog - the other normal **Path** properties will only be valid if **result** is **True**. \$\$ GetMsg \$\$ *none* \$\$ *object:***[Msg](msg.md)**  \$\$ Returns a **[Msg](msg.md)** object representing the most recent input event in a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md) (only used in [detached mode](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.md)).

The return value will evaluate to **False** when the dialog is closed, which is when you should exit your [message loop](/Manual/scripting/script_dialogs/the_dialog_message_loop/RAEDME.md).

If the dialog is not already visible (because **Show** has not been called) then it will become visible when you first call **GetMsg**. \$\$ GetString \$\$ \<string:message\>  
\<string:default\>  
\<string:max\>  
\<string:buttons\>  
\<string:title\>  
\<object:window\>  
\<byref string:result\> \$\$ *string* \$\$ Displays a text entry dialog allowing the user to enter a string. The optional parameters are:

- *message* - specify message string in the dialog
- *default* - specify default string value
- *max* - specify maximum string length
- *buttons* - specify button labels (in the same format as the **buttons** property described above)
- *title* - specify dialog window title
- *window* - specify parent window for the dialog (a **[Lister](lister.md)** or a **[Tab](tab.md)**). If not specified, the **Dialog** object's **window** property will be used.
- *result* - for scripting languages that support *ByRef* parameters, this can specify a variable to receive the string the user enters.

The return value is the entered string, or an empty value if the dialog was cancelled. The index of the button selected by the user will be available via the **result** property once this method returns. The left-most button is index **1**, the next button is index **2**, and so on. If a dialog has more than one button then by definition the last (right-most) button is the "cancel" button and so this will return index **0**. \$\$ KillTimer \$\$ \<string:name\> \$\$ *none* \$\$ Stops the specified timer. The timer must previously have been created by a call to the **SetTimer** method. \$\$ LoadPosition \$\$ \<string:id\>  
\<string:type\> \$\$ *none* \$\$ Restores the previously saved position of a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md). The position must have previously been saved by a call to the **SavePosition** method.

The **id** string is a string that Opus can use to identify your dialog or the script it comes from. The template name of the dialog will be automatically appended to this. For example, you might specify **id** as *"kundal"* - Opus would then internally save the position of a dialog called *"dialog1"* as *"kundal!dialog1"*. Make sure you pick a string that other script authors are unlikely to use as Opus has no other way of telling the saved positions apart.

The optional type parameter lets you control which position elements are restored - specify *"pos"* to only restore the position, *"size"* to only restore the size, or *"pos,size"* to restore both (this is also the default, so you can also omit the argument all together). \$\$ Multi \$\$ \<string:title\>  
\<string:default\>  
\<object:window\> \$\$ *object:***[Items](items.md)**  \$\$ Displays a "Browse to Open File" dialog that lets the user select one or more files. The optional parameters are:

- *title* - specify title of the dialog
- *default* - specify the default file selected in the dialog (if a folder is specified this specifies the default location but no file will be selected)
- *window* - specify parent window for the dialog (a **[Lister](lister.md)** or a **[Tab](tab.md)**). If not specified, the **Dialog** object's **window** property will be used.

An **[Items](items.md)** object is returned to indicate the files selected by the user. The returned object will have a **result** property that you should check first - the collection of items is only valid if **result** returns **True**. If it returns **False** it means the user cancelled the dialog. \$\$ NotifyIcon \$\$ \<string:method\>  
*arguments...* \$\$ *none* \$\$ Allows a script to add an icon to the system taskbar notification area.

The *method* argument specifies one of four actions, each of which has its own set of arguments.

<table>
<thead>
<tr class="header">
<th>method</th>
<th>Arguments</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>add</strong></td>
<td>&lt;icon&gt;,<br />
&lt;tooltip&gt;</td>
<td>Add icon to the toolbar.</td>
</tr>
<tr class="even">
<td><strong>update</strong></td>
<td>&lt;icon&gt;,<br />
&lt;tooltip&gt;</td>
<td>Updates icon or tooltip.</td>
</tr>
<tr class="odd">
<td><strong>remove</strong></td>
<td><em>none</em></td>
<td>Removes the icon.</td>
</tr>
<tr class="even">
<td><strong>notify</strong></td>
<td>&lt;title&gt;,<br />
&lt;message&gt;,<br />
&lt;flags&gt;</td>
<td>Displays a system notification message (or bubble tooltip in Windows 7).</td>
</tr>
</tbody>
</table>

For the **add** and **update** methods, the *icon* argument can be a string or **[Image](image.md)** object - see the documentation for the **icon** property above for more details. If the dialog has been assigned an icon via this property then that icon will be used automatically if none is provided.

The *tooltip* argument provides a tooltip string that the system will display when the user moves the mouse over the icon. If the dialog's **title** property has been set then the title will be used if no explicit tooltip is given.

The **notify** method lets you show a system notification associated with your dialog. This method is similar to the **[DOpus](dopus.md).Notify** method - see the description of that method for more information on the arguments.

Once your script has added an icon, the user can interact with it using the mouse. Mouse activity will generate **click**, **dblclk** and **rclick** events in your dialog's message loop. The **[Msg](msg.md).control** property will be set to **notifyicon**.

The icon is automatically removed when your dialog closes. It's also restored automatically if Explorer restarts after the icon has been added.

Please note that only one icon per dialog is supported. \$\$ Open \$\$ \<string:title\>  
\<string:default\>  
\<object:window\> \$\$ *object:***[Item](item.md)**  \$\$ Displays a "Browse to Open File" dialog that lets the user select a single file. The optional parameters are:

- *title* - specify title of the dialog
- *default* - specify the default file selected in the dialog (if a folder is specified this specifies the default location but no file will be selected)
- *window* - specify parent window for the dialog (a **[Lister](lister.md)** or a **[Tab](tab.md)**). If not specified, the **Dialog** object's **window** property will be used.

A single **[Item](item.md)** object is returned to indicate the file selected by the user. This object will have an additional **result** property that will be **False** if the user cancelled the dialog - the other normal **Item** properties will only be valid if **result** is **True**. \$\$ Request \$\$ \<string:message\>  
\<string:buttons\>  
\<string:title\>  
\<object:window\> \$\$ *int* \$\$ Displays a dialog with one or more buttons. The optional parameters are:

- *message* - specify message string in the dialog
- *buttons* - specify button labels (in the same format as the **buttons** property described above)
- *title* - specify dialog window title
- *window* - specify parent window for the dialog (a **[Lister](lister.md)** or a **[Tab](tab.md)**). If not specified, the **Dialog** object's **window** property will be used.

The return value is the index of the button selected by the user, and this is also available in the **result** property once the method returns. The left-most button is index **1**, the next button is index **2**, and so on. If a dialog has more than one button then by definition the last (right-most) button is the "cancel" button and so this will return index **0**. \$\$ RunDlg \$\$ *none* \$\$ *int* \$\$ Turns a previously [detached dialog](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.md) into a non-detached one, by taking over and running the default message loop. The **RunDlg** method won't return until the dialog has closed. You might use this if you created a dialog using **Create**, in order to initialize its controls, but don't actually want to run an interactive message loop.

The return value is the same as the object's **result** property, and represents the index of the close button selected by the user.

If the dialog is not already visible (because neither **Show** nor **GetMsg** were called) then it will become visible when you call **RunDlg**. (Compatibility note: Prior to Opus 12.22, scripts needed to call **Show** explicitly.) \$\$ Save \$\$ \<string:title\>  
\<string:default\>  
\<object:window\>  
\<string:type\> \$\$ *object:***[Path](path.md)**  \$\$ Displays a "Browse to Save File" dialog that lets the user select a single file or enter a new filename to save. The optional parameters are:

- *title* - The dialog's title.
- *default* - The default file selected in the dialog. (If a folder is given, it sets the dialog's starting location, but no file will be selected.)
- *window* - The dialog's parent window (a **[Lister](lister.md)** or a **[Tab](tab.md)**). If not specified, the **Dialog** object's **window** property will be used. (Omit the *window* argument entirely if you don't want to use it; the *type* argument, if used, works whether third or fourth.)
- *type* - A list of filetypes to populate the "Save as Type" dropdown in the save dialog. (See below.)

The optional *type* parameter consists of one or more pairs of strings, separated by exclamation marks (**!**). The first string of each pair is the plain text string shown in the drop-down, and the second string of each pair is the actual file extension. You can also specify multiple extensions for the one type by separating them with semicolon. If you want the default "All files" item to be added to the list, add a **\#** character at the start of the string. For example, *\#Text Files!\*.txt!Doc Files!\*.doc.*

A **[Path](path.md)** object is returned to indicate the file chosen by the user. This object will have an additional **result** property that will be **False** if the user cancelled the dialog, and the other normal **Path** properties will only be valid if **result** is **True.** \$\$ SavePosition \$\$ \<string:id\> \$\$ *none* \$\$ Saves the position (and size) of the dialog to your Opus configuration. The position can then be restored later on by a call to **LoadPosition**.

Normally you would call **LoadPosition** before displaying your dialog, and **SavePosition** after the dialog has been closed.

The **id** string is a string that Opus can use to identify your dialog or the script it comes from. The template name of the dialog will be automatically appended to this. For example, you might specify **id** as *"kundal"* - Opus would then internally save the position of a dialog called *"dialog1"* as *"kundal!dialog1"*. Make sure you pick a string that other script authors are unlikely to use as Opus has no other way of telling the saved positions apart. \$\$ SetTimer \$\$ \<int:period\>  
\<string:name\> \$\$ *string* \$\$ Creates a timer that will generate a periodic **timer** event for your script. The **period** must be specified in milliseconds (e.g. 1000 would equal one second).

You can optionally specify a **name** for the timer - if you don't provide a name, one will be generated automatically (and the name of the new timer will be returned). \$\$ Show \$\$ *none* \$\$ *int* \$\$ Displays the dialog that has been pre-configured using the various properties of this object. See the properties section above for a full description of these.

If the **detach** property is **False**, the call will not return until the dialog has been closed. The return value is the index of the button selected by the user, and this is also available in the **result** property once the method returns. The left-most button is index **1**, the next button is index **2**, and so on. If a dialog has more than one button then by definition the last (right-most) button is the "cancel" button and so this will return index **0**.

If the **detach** property is **True**, the call will return immediately and the return value is meaningless. You should then either run a message loop for the “detached” dialog, or call **RunDlg** to run the standard loop. \$\$ SetTaskbarGroup \$\$ \<string:group\> \$\$ *bool* \$\$ Used to change how custom dialogs are grouped with other Opus windows on the taskbar. Specify a group name to move the window into an alternative group, or omit the group argument to reset back to the default group. If one or more windows are moved into the same group, they will be grouped together, separate from other the default group.

This only works on Windows 7 and above, and only when taskbar grouping is enabled. Group names are limited to 103 characters and will be truncated if longer. Spaces and dots in group names are automatically converted to underscores.

Only works with custom script dialogs (i.e. when you are using the **template** property). Must be called after the dialog has been created (i.e. after **Show** has been called -- see the **RunDlg** method if you want to avoid writing your own message loop just for this).  
Returns true on success. \$\$ Vars \$\$ \<string:id\> \$\$ *object:***[Vars](vars.md)**  \$\$ Returns a **[Vars](vars.md)** object that represents the variables that are scoped to this particular dialog. This allows scripts to use variables that persist from one use of the dialog to another.

The **id** string is a string that Opus can use to identify your dialog or the script it comes from. The template name of the dialog will be automatically appended to this. For example, you might specify **id** as *"kundal"* - Opus would then internally save these variables for a dialog called *"dialog1"* as *"kundal!dialog1"*. Make sure you pick a string that other script authors are unlikely to use as Opus has no other way of telling the saved variables apart. \$\$ WatchDir \$\$ \<string:id\>  
\<string:path\>  
\<string:flags\> \$\$ *int* \$\$ Establish monitoring of a folder or file for changes. Returns **0** for success or an error code on failure.

The **id** argument lets you provide an ID for this watcher that's used to identify it when changes occur. **dir** is the full path to a filesystem folder, or a file if the **i** flag is set.

The optional flags are:

|       |                                                                 |
|-------|-----------------------------------------------------------------|
| **f** | monitor for file change in folder (e.g. file created)           |
| **d** | monitor for directory change in folder (e.g. directory created) |
| **r** | recursive - monitor sub-folders                                 |
| **a** | monitor for file attribute changes                              |
| **s** | monitor for file size changes                                   |
| **w** | monitor for last write time changes                             |
| **i** | monitor a single file rather than a folder                      |

When a change occurs to a monitored file or folder, the dialog's message loop receives a **dirchange** event. The **[Msg](msg.md).control** property identifies the watcher's ID.

Use the **CancelWatchDir** method to cancel monitoring. \$\$ WatchTab \$\$ \<object:**[Tab](tab.md)**\>  
\<string:events\>  
\<string:id\>  
\$\$ *bool* \$\$ Allows a [script dialog](/Manual/scripting/script_dialogs/RAEDME.md) to monitor events in a folder tab. You will receive notifications of the requested events through your message loop.

The **tab** parameter specifies the **[Tab](tab.md)** you want to watch. The **events** string is a comma-separated list of events you want to watch for. The **id** string is an optional parameter; it lets you assign your own ID to the tab to make it easier to tell where events are coming from (if you're monitoring multiple tabs, for instance).

These are the events you can watch for are. Note that some are equivalent to the existing script events (e.g. **OnActivateTab**):

|              |                                                         |
|--------------|---------------------------------------------------------|
| **select**   | items in the tab are selected or deselected             |
| **navigate** | the folder is changed in the tab                        |
| **add**      | items are added to the folder                           |
| **delete**   | items are deleted from the folder                       |
| **change**   | items in the folder are changed (size, date, name, etc) |
| **activate** | tab activated or deactivated                            |
| **srcdst**   | source/destination state changed                        |
| **view**     | view mode changed                                       |
| **flat**     | flat view state changed                                 |
| **filter**   | quick filter changed                                    |

Once notification has been established you will be notified of all requested events when they occur. Note that no specific information is sent with notifications - e.g. for the "change" event, you aren't told which items have changed, only that something has.

You will receive notification events in your message loop. The various properties of the **[Msg](msg.md)** object let you determine what happened.

The **[Msg](msg.md).event** property will be set to **tab** for notifications from a watched folder tab.

The **[Msg](msg.md).control** property tells you which tab the change occurred in; if you specified an ID when you called the **WatchTab** function, this will be in the [Msg](msg.md)**.control** property - otherwise, it will be the numeric handle of the tab. Note that it's \*not\* the actual **[Tab](tab.md)** object. You can access the **[Tab](tab.md)** object via the [Msg](msg.md)**.tab** property but this can be inefficient, as it requires a new **[Tab](tab.md)** object to be created every time. If you're only monitoring one tab it's better to store the **[Tab](tab.md)** object in your own variable - and if you're monitoring multiple tabs you could, e.g. use a unique ID for each one and keep the objects in a **[Map](map.md)**.

The **[Msg](msg.md).value** property tells you which notification event occurred. Possible values are **select**, **navigate**, **filechange**, **activate**, **srcdst**, **view**, **flat**, **filter** and **close** (sent if the tab is closed while you are monitoring it).

For the **filechange** event, the **[Msg](msg.md).data** property contains a bit mask indicating which file events occurred. **1** = add, **2** = delete, **4** = change. The values will be added together (so e.g. **6** indicates at least one item was changed and at least one was deleted). It's up to your script to determine exactly what changed.

You can change the events you're monitoring for by calling the **WatchTab** method again with the same tab and new event list.

To stop monitoring an existing tab, call **WatchTab** with the second parameter set to **stop**. Monitoring is automatically cancelled if your dialog closes (and also if the tab closes).

\</commandtable\>
