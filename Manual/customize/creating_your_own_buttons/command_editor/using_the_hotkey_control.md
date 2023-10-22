# Using the Hotkey Control

The [Command Editor](/Manual/customize/creating_your_own_buttons/command_editor/RAEDME.md) and the Keys page in the [Customize](/Manual/customize/RAEDME.md) dialog both use a special field, the *Hotkey Control*, to make entering hotkey sequences easier.

![](/Manual/images/media/hotkey_control_0.png)

To assign a simple key press, simply click in it to activate it like a normal string field, and then press the desired key combination. For example, to assign **Alt + D** to a function, click in the field and press the **Alt** and **D** keys together.

If you click the drop-down arrow with the mouse, a menu is displayed with several commands relating to the hotkey.

![](/Manual/images/media/hotkey_control_2.png)

- **Left** / **Right**: In a button located in the [File Display Toolbar](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/file_display_toolbar.md) (as shown above), the **Left** and **Right** items let you assign a key that applies only to the left or right file display. See below for an example of how to use this.
- **Enter** /\*\* Escape\*\* /\*\* Tab\*\*: Allows you to assign a hotkey to those keys.
- **Original** / **Previous**: If you have changed the key, these two commands let you revert to the previous setting, and the original key assigned when the dialog first opened.
- **Add Alternative**: This command lets you add an alternative key sequence to the same command. For example, the default [location field](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.md) can be activated by pressing either **Alt + D** or the **F4** key. See below for an example of how to use this.
- **Add To Sequence**: This command lets you add an additional key to the current key sequence. You can use this to create hotkeys where you have to press two or more keys in sequence (rather than at the same time) to activate the function.
- **Remove**: This removes (clears out) the hotkey from the control.

When editing a hotkey function (as opposed to a toolbar button's hotkey), the drop-down will also let you select from a sub-menu of *Media keys*.

![](/Manual/images/media/hotkey_control_14.png)

These are special input events that aren't associated with the traditional keys on the keyboard. For example, you could use this to assign a function to the *Play* button on your keyboard, or the *Back* button on your mouse.

# Using the Hotkey Control

In the above screenshot, **Alt + D** is the only current key assignment. Selecting the **Add Alternative** command displays a **+** sign indicating that the next key press will add an alternative sequence.

![](/Manual/images/media/hotkey_control_3.png)

If you then press another key, it is added as the beginning of an alternative sequence. For example, if you press **F4**:

![](/Manual/images/media/hotkey_control_4.png)

Pressing either **Alt + D** or **F4** would now activate the function. You can add as many alternate key sequences as you like. When a control with alternate key sequences is active, it displays a separate drop-down listing each alternate sequence separately.

![](/Manual/images/media/hotkey_control_6.png)

The sequence shown in the main edit field (**F4** in the above image) is the *current sequence*, and is the only one that can be edited. For example, if you pressed **F3** at this point, **F4** would be replaced by **F3** but the **Alt + D** sequence would be unaffected. If you want to edit a sequence other than the current one you can remove it by clicking its ***Remove*** link and add it back again.

# Using the Hotkey Control

Depending on how much you use hotkeys, you may find yourself running out of keys on the keyboard to assign functions to. Multiple key sequences can let you create additional hotkeys that require two or more keys to be pressed in sequence to activate the function, which can dramatically increase the number of hotkey functions you can define.

The procedure for adding a key to the sequence is similar to adding an alternative. Select the **Add To Sequence** command, which will display a **&** sign indicating that the next key press will add to the current sequence.

![](/Manual/images/media/hotkey_control_5.png)

  
Press the key you want to add to the sequence, and the control will update to show the new assignment. For example, if you press **1** at this point:

  
![](/Manual/images/media/hotkey_control_7.png)

To activate this hotkey you would now need to press **Alt + D** followed by **1**. Different hotkeys can use the same keys up until the last one in the sequence. For example, you could therefore create multiple hotkeys that all start with **Alt + D**, followed by a different number (e.g. **Alt + D** followed by **1** could run one function, whereas **Alt + D** followed by **2** could run another). You can add as many keys as you like to a sequence. In the Lister, when you press a key that matches the start of a multi-key sequence, Opus displays a small popup in the bottom-left corner as a visual cue that you need to press another key to run a function.

  
![](/Manual/images/media/hotkey_control_8.png)

# Using the Hotkey Control

The [File Display Toolbar](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/file_display_toolbar.md) is handled slightly differently to all other toolbars, because in [dual-display mode](/Manual/basic_concepts/the_lister/dual_display/RAEDME.md) there are two copies of it. Normally, pressing a hotkey bound to a button in the file display toolbar will activate the function in the source file display. However, you can assign hotkeys that will specifically activate the function in the left (or top) or the right (or bottom) file display, irrespective of which is the source. For example, you could activate the left file display's location field by pressing **Shift + F4**, and the right file display's location field by pressing **Ctrl + F4**.

Start with the first key sequence that you want to assign:

![](/Manual/images/media/hotkey_control_11.png)

Then from the drop-down menu select the **Left** command. This will bind that key sequence to the left file display.

![](/Manual/images/media/hotkey_control_9.png)

Then, follow the steps above to add an alternative key sequence for the right file display. Select the **Add Alternative** command from the drop-down:

![](/Manual/images/media/hotkey_control_10.png)

And press the key for the right file display:

![](/Manual/images/media/hotkey_control_12.png)

Finally, select the **Right** command from the drop-down menu to bind the new sequence to the right file display.

![](/Manual/images/media/hotkey_control_13.png)
