# Toolbar Context Menus

When in Customize mode, all toolbar buttons have a context menu that you can access by right-clicking them. The commands on this context menu will vary based on the type of button.

For a "regular" button, the context menu looks like this:

\<WRAP c1borderless\>

<table>
<tbody>
<tr class="odd">
<td>![](/Manual/images/media/button_context_menu_1.png) </td>
<td></td>
<td><strong>Cut</strong>: Cut the button to the clipboard - when pasted to another location on the toolbar, the button will be moved.<br />
<strong>Copy</strong>: Copy the button to the clipboard - you can paste a copy of it to the same or another toolbar.<br />
<strong>Paste</strong>: Paste the button from the clipboard - inserts the button to the left of the button you right-clicked on.<br />
<strong>Delete</strong>: Delete the button.<br />
<strong>Edit</strong>: Edit the button.<br />
<strong>Three Buttons</strong>: Turn a simple button into a <a href="multiple_function_buttons">multiple-function button</a> (a "three button button").<br />
<strong>Begin a Group</strong>: Insert a separator to the left of this button.<br />
<strong>Insert New</strong>: Insert a new button, drop-down menu or spacer to the left of this button.<br />
</td>
</tr>
</tbody>
</table>

\</WRAP\>\<wrap clear/\>

The context menu for a *drop-down menu* looks almost the same.

\<WRAP c1borderless\>

<table>
<tbody>
<tr class="odd">
<td>![](/Manual/images/media/button_context_menu_2.png) </td>
<td></td>
<td>The <strong>Three Buttons</strong> option is unavailable (a drop-down menu can't be converted to a multiple-function button), and there is a new command:<br />
<br />
<strong>Convert to Menu Button</strong>: This command turns a drop-down menu (a button whose sole purpose is to drop-down a menu of other buttons) into a drop-down menu button. A menu button combines a regular button, that you can assign a function to, with a drop-down menu. The main part of the button runs the assigned command, and a smaller button to the right that displays an arrow glyph is used to pop open the menu.<br />
![](/Manual/images/media/menu_button.png) <br />
See the <a href="drop-down_buttons_and_menus">Drop-down Buttons and Menus</a> topic for more details.</td>
</tr>
</tbody>
</table>

\</WRAP\>\<wrap clear/\>

Again, the context menu for a *drop-down menu button* is very similar, with only one additional command.

\<WRAP c1borderless\>

<table>
<tbody>
<tr class="odd">
<td>![](/Manual/images/media/button_context_menu_3.png) </td>
<td></td>
<td><strong>Always Enable Drop-down</strong>: This option makes the drop-down part of a menu button always available, even if the "button part" is disabled.<br />
<strong>Hold or Right-Click to Drop Down</strong>: This option removes the visible drop-down arrow. The drop-down menu can be accessed either by right-clicking on the button, or by left-clicking and holding the mouse button down until the menu appears.<br />
<br />
The <strong>Go Up</strong> button (![](/Manual/images/media/always_enable_menu_button.png)) in the default File Display toolbar makes use of both of these options. The <strong>Go Up</strong> button is disabled when you are at the Desktop level (because you can't go up any further from there). Without the <strong>Always enable drop-down</strong> option turned on, this would make it impossible for you to access the commands in the drop-down menu attached to the <strong>Up</strong> button.<br />
</td>
</tr>
</tbody>
</table>

\</WRAP\>\<wrap clear/\>

The context menu for a *field button* looks like this:

\<WRAP c1borderless\>

<table>
<tbody>
<tr class="odd">
<td>![](/Manual/images/media/field_context_menu.png) </td>
<td></td>
<td><strong>Field Type</strong>: Lets you change the type of the field button. Field buttons can only be created by dragging the appropriate item from the Commands tab of the Customize dialog (or by duplicating an existing field), but once the button exists you can change it between any of the available types from the context menu.<br />
<strong>Full Width</strong>: Sets the field to <em>full width</em> mode. In this mode, it will expand (when Opus isn't in Customize mode) to occupy all the available space in the toolbar. If a field isn't in full width mode you can resize it to any size you like.<br />
<strong>Restore Focus</strong>: If this option is enabled, pressing the <strong>Enter</strong> key in the field will return focus automatically to the file display.<br />
<br />
See the <a href="field_buttons">Field Buttons</a> topic for more information about field buttons.<br />
</td>
</tr>
</tbody>
</table>

\</WRAP\>\<wrap clear/\>

Finally, the context menu for the *toolbar* itself (displayed when you right-click an empty area of the toolbar) looks like this:

\<WRAP c1borderless\>

<table>
<tbody>
<tr class="odd">
<td>![](/Manual/images/media/toolbar_context_menu.png) </td>
<td></td>
<td><strong>Customize</strong>: Brings the <strong>Customize</strong> dialog to the front if it has been hidden behind another window.<br />
<strong>Factory Reset this Toolbar</strong>: Only available on the <a href="/basic_concepts/the_lister/toolbars/the_default_toolbars">default toolbars</a>, this resets the toolbar to its initial settings. Any changes you have made to that toolbar will be lost.<br />
<strong>New</strong>: Add a new button, menu, menu button or spacer to the toolbar. The new button appears at the end of the toolbar.<br />
<strong>Paste</strong>: When you have copied or cut a button to the clipboard, this command lets you paste it to the end of the toolbar.<br />
<strong>Toolbars</strong>: This sub-menu displays a list of all your toolbars, letting you turn them on or off. This sub-menu also contains a <strong>Factory Reset Toolbars</strong> command - selecting this will reset <strong>all</strong> of the <a href="/basic_concepts/the_lister/toolbars/the_default_toolbars">default toolbars</a>to their initial settings. Any changes you have made to the default toolbars will be lost. Any toolbars you have created yourself will be turned off, but otherwise won't be affected.<br />
<strong>Lock the Toolbars</strong>: Removes the dragging grips from the edge of the toolbars, preventing you from moving them around.<br />
<strong>Close</strong>: Close the toolbar.<br />
</td>
</tr>
</tbody>
</table>

\</WRAP\>\<wrap clear/\>
