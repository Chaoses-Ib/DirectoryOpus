# Tab Context Menus

Functions in the [folder tab context menus](/Manual/customize/the_customize_dialog/context_menus.md) can use the evaluator like in any other [toolbar or menu](functions/README.md), however in this evaluation context, the following variables are available which are specific to folder tabs:

<table>
<thead><tr><th>
Variable</th><th>
Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>
Returns the number of tabs.
</td></tr><tr><td>
countdual</td><td>

*int*</td><td>
In a dual-display Lister, returns the number of tabs in the other file display.
</td></tr><tr><td>
dual</td><td>

*bool*</td><td>

Returns **true** if this is a dual-display Lister, or **false** for single-display.
</td></tr><tr><td>
path</td><td>

*path*</td><td>
Returns the path shown in the tab that was right-clicked.
</td></tr><tr><td>
right</td><td>

*bool*</td><td>

Returns **true** if this is the right/bottom file display, **false** if it is the top/left one.
</td></tr><tr><td>
sel</td><td>

*int*</td><td>

Returns the index of the tab that was right-clicked, or `-1` if the click wasn't on a tab.
</td></tr></tbody>
</table>

