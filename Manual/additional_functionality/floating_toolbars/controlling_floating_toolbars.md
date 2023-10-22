# Controlling Floating Toolbars

You can change a number of settings that affect the appearance and behavior of a floating toolbar.

When you are in [Customize](/Manual/customize/RAEDME.md) mode, moving the mouse cursor over a floating toolbar displays a small icon (![](/Manual/images/media/dock-edit.png)) will appear to the top-right of the toolbar. Clicking this icon displays the following context menu.

![](/Manual/images/media/floater_edit.png)

If you're not in Customize mode, you can also display this menu by right-clicking an empty part of the toolbar itself (although this may not be that easy, if for example the border has been turned off).

- **Customize**: Provides a quick way to get back to the Customize dialog.
- **Appearance**: This sub-menu has a number of options affecting the appearance of the floating toolbar.  
  \* **Frame**: The toolbar will have a solid background and a frame (optionally with rounded corners).  
  ![](/Manual/images/media/floater_-_frame.png)

      * **No Frame**: The toolbar will have a solid background but no frame - buttons will be hard against the edge.\\

![](/Manual/images/media/floater_-_no_frame.png)

      * **Transparent**: The toolbar will have no background at all - it will appear as if the buttons on it are floating on the desktop. Because transparent toolbars are harder to manipulate the toolbar won't actually appear transparent until you leave Customize mode - instead it will be rendered with a checkerboard pattern. Out of Customize mode the toolbar will display its normal frame if you hold the **Shift** key down as you move the mouse over it, which lets you reposition transparent toolbars.\\

![](/Manual/images/media/floater_-_transparent.png)

      * **Glass**: The toolbar will be rendered with a translucent glass background on Vista and Windows 7. Microsoft went off the idea of translucency in Windows 8 so from Windows 8 onwards you get the system "tint" colour without any translucency.\\

![](/Manual/images/media/floater_-_glass.png)

      * **Taskbar**: The toolbar will be rendered in the same style as the Windows taskbar (and so obviously looks different in every version of Windows).\\

![](/Manual/images/media/floater_-_taskbar.png)

      * **Rounded Edges**: When the toolbar is set to a type that has a frame, it will have rounded corners (as in the images above) rather than square ones. 
      * **Same-sized Buttons**: Make all buttons in the floating toolbar the same size. When this is on all toolbar buttons will be the same size as the largest button. 
      * **Vertical**: The floating toolbar will have a vertical orientation rather than horizontal. \\
    * **Auto-Hide**: This option is only available when the toolbar is docked to the side of the screen. If this is turned on the toolbar will hide out of view unless the mouse moves over it. 
    * **Enable Hotkeys:** When a toolbar is floating its hotkeys become system global - that is, they work anywhere in Windows without Opus or the toolbar having to be active. This is very useful but also potentially confusing, as the hotkeys will override the use of the same key press in other programs. For example, if a toolbar button had Ctrl-C defined as a hotkey and it was made global, you would no longer be able to press Ctrl-C to copy to the clipboard in any other program! Therefore, by default hotkeys defined for toolbar buttons are disabled when the toolbar is floating. You can enable them with this option. 
    * **Keep on top**: The toolbar will appear on top of other windows. 
    * **Lock position**: Lock the position of the toolbar on-screen so it can't be dragged or resized. 
    * **New**: Create a new toolbar button. 
    * **Close**: Close the floating toolbar. 

You can float multiple copies of the same toolbar if desired, and Opus will remember the settings for each one individually.
