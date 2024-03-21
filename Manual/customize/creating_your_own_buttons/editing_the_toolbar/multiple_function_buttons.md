# Multiple Function Buttons

A multiple-function button is a button that has up to three distinct functions attached to it (it's therefore also called a "three-button button").

- The first, or primary, function is executed by **left**-clicking the button as normal
- The second function is executed by **right**-clicking the button
- The third function is executed by **middle**-clicking the button. If you don't have a middle mouse button, the **Simulate middle mouse click with control + left-click** option on the **[Toolbars / Options](/Manual/preferences/preferences_categories/toolbars/toolbar_options.md)** page in Preferences can help you make full use of this function.

To make a multiple-function button, you must start with a regular, single-function button. See the [Editing the Toolbar]() page for information on how to create a new button if desired. In Customize mode, right-click the button and select the **Three Buttons** option from its context menu. This immediately turns the single button into a multiple-function button, and the button's original function becomes the new *primary* function.

![](/Manual/images/media/three_button_1.png) 

  
In Customize mode, a multiple-function button behaves very much like a [drop-down menu](drop-down_buttons_and_menus.md) (other than that the number of functions in the menu is limited to three). The image above shows what you would see initially if you turn the **Dual Display** button on the standard toolbar into a multiple-function button. Effectively, the original button becomes a drop-down menu, and the original function is duplicated and becomes the first button in the new menu.

You can now add one or two additional buttons to the drop-down menu, using the techniques described on the [Editing the Toolbar]() page.

![](/Manual/images/media/three_button_2.png) 

Here we have dragged the **Folder Tree **button from the Customize dialog and dropped it in the menu - it has become the button's second function. Similarly, the **Metadata Pane** button has been added as the button's third function. The multiple-function button is now "full" - attempts to add additional functions to the menu will fail.

When you leave Customize mode, the toolbar button will appear the same as it did before - and indeed, left-clicking it will perform the same action as before (to turn [dual display](/Manual/basic_concepts/the_lister/dual_display/README.md) mode on or off). It's only when you hover the mouse over the button to reveal the tooltip that the difference becomes apparent.

![](/Manual/images/media/three_button_3.png) 

The tooltip makes it obvious that this button has multiple functions attached to it. The button associated with each function is indicated by the **LMB** (left mouse button), **RMB** (right mouse button) and **MMB** (middle mouse button) prefixes. So in this example, a left-click on the button will turn dual display on or off, a right-click on the button will turn the folder tree on or off, and a middle-click on the button will turn the metadata pane on or off.
