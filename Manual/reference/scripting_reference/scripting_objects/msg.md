# Msg

The **Msg** object represents a [script dialog](/Manual/scripting/script_dialogs/README.md) input event message. It’s returned by the **[Dialog](dialog.md).GetMsg** method which you call when running the message loop for a [detached dialog](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.md).

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*bool*</td><td>

Returns **True** if the message is valid, or **False** if the dialog has been closed (which means you should exit your message loop).
</td></tr><tr><td>
buttons</td><td>

*string*</td><td>

Returns a string indicating which mouse button was pressed when the message was generated. Possible values are **left**, **right** and **middle**.
</td></tr><tr><td>
checked</td><td>

*int*</td><td>

If the event type is **checked**, this indicates the check state of the item. If checkboxes are used in automatic mode, this will be the **new** check state of the item. In manual mode, this will indicate the **existing** state and it's up to you to change the state if desired.

Check states are:

|       |                        |
|-------|------------------------|
| **0** | unchecked              |
| **1** | checked                |
| **2** | indeterminate          |
| **3** | unchecked/disabled     |
| **4** | checked/disabled       |
| **5** | indeterminate/disabled |
</td></tr><tr><td>
control</td><td>

*string*</td><td>

Returns the name of the control involved in the event. You can get a **[Control](control.md)** object representing the control by passing this string to the **[Dialog](dialog.md).Control** method.

- For a **timer** event this returns the name of the timer that was triggered.
- For a **hotkey** event this returns the name of the hotkey.
- For a **drop** event this returns the name of the control that the files were dropped on.
- For a **tab** event this tells you which monitored tab the event occurred in (either the ID you assigned in the **[Dialog](dialog.md).WatchTab** method, or the numeric handle of the tab if you didn't assign an ID).
- For a **dirchange** event this tells you which watcher detected a file or folder change (the ID you assigned via the **[Dialog](dialog.md).WatchDir** method).
- If you have added an icon to the taskbar via the **[Dialog](dialog.md).NotifyIcon** method, **notifyicon** indicates an event associated with that icon.
</td></tr><tr><td>
cx</td><td>

*int*</td><td>

For **resize** events, this property returns the new width of the dialog.
</td></tr><tr><td>
cy</td><td>

*int*</td><td>

For **resize** events, this property returns the new height of the dialog.
</td></tr><tr><td>
data</td><td>

*int* or// bool//</td><td>

If the event type is **focus**, indicates the new focus state of the control - **True** if the control has gained the focus, or **False** if it's lost it.

For a *combo box* or *list box* control: If the event type is **selchange** or **dblclk**, returns the data value associated with the selected item.

For a two-state *check box* control or *radio button*: If the event type is **click**, returns a *bool* indicating the current check state.

For a three-state *check box*: If the event type is **click**, returns an *int* representing the current state.

If the event type is **timer**, this value indicates the number of milliseconds that have elapsed since the last time this timer was triggered.

If the event type is **tab**, and the **value** property is set to **filechange**, this indicates which file change events occurred in the monitored tab. **1** = add, **2** = delete, **4** = change. The values will be added together (so e.g. **6** indicates at least one item was changed and at least one was deleted).
</td></tr><tr><td>
dialog</td><td>

*string*</td><td>
Returns the name of the parent dialog.
</td></tr><tr><td>
event</td><td>

*string*</td><td>

Returns a string indicating the event that occurred. Currently defined events are:

|                |                                                                                                                                                                                                                                                                                                                                           |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **invalid**    | The dialog has been closed                                                                                                                                                                                                                                                                                                                |
| **checked**    | For a listview control with the ***Checkboxes*** property enabled, indicates that the checkbox of a list item has been clicked.                                                                                                                                                                                                           |
| **click**      | The control was clicked (e.g. a button, check box, radio button, markup text or static control with ***Notify Clicks*** property enabled).                                                                                                                                                                                                |
| **close**      | The user clicked the dialog's close button. Only generated if the **[Dialog](dialog.md).want_close** property has been set to **True**. You'll need to close the dialog manually using the **[Dialog](dialog.md).EndDlg** method.                                                                                                               |
| **dblclk**     | An item in the list was double-clicked (list box, combo box or list view) or the control was double-clicked (static control with ***Notify Clicks** *property enabled).                                                                                                                                                                   |
| **dirchange**  | A file or folder that you established monitoring of via the **[Dialog](dialog.md).WatchChanges** method has changed. The **control** property tells you which watcher was triggered.                                                                                                                                                         |
| **drag**       | The user has initiated a drag and drop from a static or list view control. You can respond by calling the **[Dialog](dialog.md).Drag** method. The ***Drag Source*** property must be enabled on the control for this event to be generated.                                                                                                 |
| **drop**       | Files were dropped onto your dialog. The dialog template must have its ***Accept Drops*** property set to **True** to enable drag & drop support.                                                                                                                                                                                         |
| **editchange** | The contents of an edit field were modified. For a list view this event indicates that the label of a list item was edited.                                                                                                                                                                                                               |
| **focus**      | The control gained or lost focus.                                                                                                                                                                                                                                                                                                         |
| **hotkey**     | A key combination added as a hotkey with the **[Dialog](dialog.md).AddHotkey** method has been pressed.                                                                                                                                                                                                                                      |
| **resize**     | The dialog was resized by the user. Only generated if the **[Dialog](dialog.md).want_resize** property has been set to **True**. Don't mix manual and automatic resizing with the same control: If you move or resize a control in response to this event, the control should not have any of the **resize** flags set in the dialog editor. |
| **rclick**     | An item in the list was right-clicked (list box, list view) or the control was right-clicked (static control with ***Notify Clicks** *property enabled).                                                                                                                                                                                  |
| **selchange**  | The selection was changed (list box, combo box, list view or tab).                                                                                                                                                                                                                                                                        |
| **timer**      | A periodic timer created with the **[Dialog](dialog.md).SetTimer** method has elapsed.                                                                                                                                                                                                                                                       |
| **tab**        | An event has occurred in a tab monitored using the **[Dialog](dialog.md).WatchTab** method.                                                                                                                                                                                                                                                  |
</td></tr><tr><td>
focus</td><td>

*bool*</td><td>

Returns **True** if the control had focus when the message was generated.
</td></tr><tr><td>
index</td><td>

*int*</td><td>

Returns the current selection index for a *combo box*, *list box* or *tab control*.
</td></tr><tr><td>
mousex</td><td>

*int*</td><td>
Returns the horizontal position of the mouse cursor when the message was generated.
</td></tr><tr><td>
mousey</td><td>

*int*</td><td>
Returns the vertical position of the mouse cursor when the message was generated.
</td></tr><tr><td>
object</td><td>

*variant*</td><td>

For a **drop** event, this property returns a **[Vector](vector.md)** of **[Item](item.md)** objects, representing the files that were dropped onto your dialog.
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating the qualifier keys (if any) that were held down when the message was generated.

The string can contain any or all of the following: *shift,* *ctrl*, *alt*, *lwin*, *rwin*

If no qualifiers were down, the string will be: *none*
</td></tr><tr><td>
result</td><td>

*bool*</td><td>

Returns **True** if the message is valid, or **False** if the dialog has been closed.
</td></tr><tr><td>
tab</td><td>

*string*</td><td>

For a dialog tab control, returns the name of the parent tab (if the control is on a dialog that's inside a tab control).

If the event type is **tab**, this returns a **[Tab](tab.md)** object representing the monitored tab that the event occurred in. Calling this repeatedly may be inefficient.
</td></tr><tr><td>
value</td><td>

*string*</td><td>

For the **dblclk**, **editchange** and **selchange** events, returns the current contents of the edit field (or selected item label).

For the **tab** event, indicates which event occurred in the monitored tab. Possible values are **select**, **navigate**, **filechange**, **activate**, **srcdst**, **view**, **flat**, and **close** (sent if the tab is closed while you are monitoring it).

For the **drag** event, this indicates which button is being used to drag (**left** or **right**).

For a **click** event from a markup text control, this indicates the ID of the clicked link.
</td></tr></tbody>
</table>

