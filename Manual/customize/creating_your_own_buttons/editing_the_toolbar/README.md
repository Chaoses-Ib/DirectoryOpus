# Editing the Toolbar

The first step to editing the toolbar and making your own buttons (or modifying existing ones) is to go into [Customize](/Manual/customize/README.md) mode. The easiest way to do this is to select the **Customize Toolbars** command from the **Settings** menu.

![](/Manual/images/media/customize_toolbar_item.png) 

*A useful tip to remember*: if you ever find that you can't get to the **Customize Toolbars** command (because you have deleted it from the menu, or turned off that toolbar) you can always get to it from the Lister's window menu (click on the icon in the top-left corner).

![](/Manual/images/media/customise_window_menu.png)

Another way to get to Customize mode, particularly if you want to edit a specific button, is to turn on the <kbd>Alt</kbd>**-Click to edit Toolbar buttons** option on the **[Toolbars / Options](/Manual/preferences/preferences_categories/toolbars/toolbar_options.md)** page in Preferences. With this option on, holding the <kbd>Alt</kbd> key and left-clicking a toolbar button will set Opus into Customize mode and display the command editor for the button you clicked on.

However you get into Customize mode, once you are there all toolbars become editable. *Another useful tip to remember*: you can still run a toolbar button from Customize mode, by <kbd>Shift</kbd>-clicking it.

![](/Manual/images/media/toolbars_in_customize.png) 

The above image shows the default toolbars in Customize mode. The only visible change you'll notice when you go into Customize mode is that the various fields have been replaced by place-holders. In the example above, the **Search** field is resizable (indicated by the grip symbols on its right edge) - you can click and drag it by the right edge to resize it. The **Location** and **Spacer** fields do not have resizing grips, which indicates they are set to *full width* mode. See the [Field Buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/README.md) page for more information about field buttons.

You'll also notice that, in Customize mode, the buttons on the bottom toolbar don't quite fit in the space available. This is because a previously hidden button - the **Toolbar Marker** button in this case - becomes visible in Customize mode. See the [Dynamic Buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md) page for more information about this type of button.

When buttons don't fit in the available space in Customize mode, two small arrows appear on the right edge of the toolbar. You can use these arrows to scroll the toolbar and access the items that are out-of-view.

Toolbar editing is largely mouse-based. All buttons (and the toolbars themselves) have a [context menu](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/toolbar_context_menus.md) that you can access by right-clicking when in Customize mode.

##### Edit an existing button

To edit an existing button, double-click it. Alternatively, right-click it and choose **Edit** from the context menu. In either case, the [Command Editor](command_editor/README.md) dialog will open to let you make changes to the appearance and function of the button.

To edit a function in a drop-down menu, left-click the menu to open it, and then edit the button within it as normal. In Customize mode, a drop-down menu will remain open until you click it again to close it (or until another drop-down menu on the same toolbar is opened).

##### Add a new pre-defined button

To add a pre-defined button (one with a command already assigned to it), locate the desired command on the **Commands** tab of the Customize dialog, then drag and drop it to the toolbar. The button will be added at the location you drop it. You can also add the button to a drop-down menu by dragging over the menu - after a short period of time the menu will pop open, and you can then drop the button into it.

##### Add a new, empty button

To add a brand new button (one with no function defined) to a toolbar, do any of the following:

- From the Customize dialog's **Commands** tab, expand the **New** category, then drag **New Button** out of the list and drop it on the toolbar. This will add the button at the location you dropped it.
- Right-click the empty space at the end of a toolbar and choose **New \> New Button** from the context menu. This will add the button to the end of the toolbar.
- Right-click an existing button and choose **Insert New \> New Button** to insert the new button immediately after the one you clicked on.

Once the new button is added, you can edit it (by double-click or right-click as described above).

##### Add a button that runs an external program

To add a button that launches an external program, you can simply drag the program's icon (or a shortcut to the program) and drop it on the toolbar. For example, you could drag a shortcut from the Windows Start menu, or a program icon from the C:\Program Files directory.

The **[Launch Options](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/launch_options.md)** dialog will appear when you drop a program on the toolbar, allowing you to choose how the program is run. For example, you may want to run the program on its own, or to pass seleted files to it. If the **Launch Options** dialog has been configured to always use particular settings without re-appearing, you can force it to appear by holding the <kbd>Ctrl</kbd> key as you drop a program on the toolbar.

##### Add a button that takes you to a folder

Drag a folder (or a shortcut to a folder) and drop it on the toolbar to create a button that will navigate to that folder.

##### Duplicate an existing button

To make a copy of an existing toolbar button, you can either:

- Drag the button, and while holding the <kbd>Ctrl</kbd> key down, drop it in the new location.
- Right-click the button and choose **Copy** from the context menu, and then right-click either the empty space on the toolbar or an existing button, and choose **Paste** from the context menu. If you right-click an existing button then the copy will be inserted immediately after it. If you right-click the toolbar's empty space then the copy will be added to the end of the toolbar.

You can copy an existing button to the same toolbar or to another toolbar. You can copy a button into a drop-down menu by dragging the button over the menu and hovering there for a short time - the menu will pop open, letting you drag the button into it. Make sure you keep the <kbd>Ctrl</kbd> key held down until the mouse button is released.

##### Move an existing button

To move a toolbar button from one location to another (on the same toolbar or a different toolbar), you can either:

- Drag the button and drop it in the new location.
- Right-click the button and choose **Cut** from the context menu, and then right-click either the empty space on the toolbar or an existing button, and choose **Paste** from the context menu. If you right-click an existing button then the cut button will be moved to the location immediately after it. If you right-click the toolbar's empty space then the cut button will be moved to the end of the toolbar.

You can move a toolbar button into a drop-down menu by dragging the button over the menu and hovering there for a short time - the menu will pop open, letting you drag the button into it.  You can also move into or out of a drop-down menu using copy and paste - just click the menu to open it, and then right-click the button within it as normal.

##### Delete a button

To delete a toolbar button you can either:

- Drag the button from the toolbar and drop it on the Customize dialog.
- Right-click the button and choose **Delete** from the context menu.

##### Add a new, empty sub-menu (or menu button)

To add a brand new sub-menu (within which you can then add further items) to a toolbar, do any of the following:

- From the Customize dialog's **Commands** tab, expand the **New** category, then drag **New Menu** (or **New Menu Button**) out of the list and drop it on the toolbar. This will add the menu at the location you dropped it.
- Right-click the empty space at the end of a toolbar and choose **New \> New Menu** (or **New Menu Button**) from the context menu. This will add the button to the end of the toolbar.
- Right-click an existing button or menu and choose **Insert New \> New Button** (or **New Menu Button**) to insert the new menu immediately after the one you clicked on.

Once the new menu is added, you can edit it (by double-click or right-click as described above), and if you open it with a left-click you can add items inside of it in the same way as the top-level toolbar.

See [Drop-down Buttons and Menus](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/drop-down_buttons_and_menus.md) to learn about the different sub-menu types.

##### Insert a separator

To insert a separator between two buttons you can either:

- Drag the button a small distance (a few pixels) to the right. If you drag the button too far you will move it - you only need to drag it a very small distance to insert a separator.
- Right-click the button and turn on the **Begin a Group** option in the context menu.

In either case, the separator will be added between the button you dragged or right-clicked on, and the one immediately before it (to the left).

##### Remove a separator

To remove a separator from between two buttons you can either:

- Drag the button (the one to the right of the separator) a few pixels to the left.
- Right-click the button and turn off the **Begin a Group** option in the context menu.

##### Put a gap between buttons

You can use the **Spacer** field to put a gap between buttons (or to right-align one or more buttons).

      * On the [[..:the_customize_dialog:commands|Commands]] tab of the Customize dialog, locate **Spacer** underneath the **New** category, and drag it to your toolbar. Alternatively, right-click an existing button and choose **Insert New > Spacer**, or right-click the toolbar's empty space and choose **New > Spacer**.
      * You can adjust the size of the spacer manually, or right-click it and turn on the Full-width option to make it automatically right-justify any subsequent toolbar buttons. See the section on [[~field_buttons|Field Buttons]] for more information.

More:

[Launch Options](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/launch_options.md)  
[Toolbar Context Menus](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/toolbar_context_menus.md)  
[Multiple Function Buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/multiple_function_buttons.md)  
[Drop-down Buttons and Menus](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/drop-down_buttons_and_menus.md)  
[Dynamic Buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)  
[Field Buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/README.md)  
[Sharing functions with others](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/sharing_functions_with_others.md)  
