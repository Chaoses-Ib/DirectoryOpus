# Evaluator Dynamic Button State

You can use the evaluator with the various [command modifiers](/Manual/reference/command_reference/command_modifier_reference.md) that affect the state of toolbar buttons:

- **@hideif** / **@showif** - dynamically hide or show the button
- **@disableif** / **@enableif** - dynamically disable or enable the button
- **@toggle** - control whether the button appears checked/selected or unchecked/unselected

Note that these modifiers can also be used [without the evaluator](/Manual/reference/command_reference/command_modifier_reference.md#@icon), so to use the evaluator you must begin the expression with a \`=\` character.

![](page>standard_variables&nodate&nouser&nofooter)

The return value from the evaluation expression will be used to determine the state. The meaning depends on the modifier in question:

- **@hideif** - return **true** to hide the button, **false** to show it
- **@showif** - return **true** to show the button, **false** to hide it
- **@disableif** - return **true** to disable the button, **false** to enable it
- **@enableif** - return **true** to enable the button, **false** to disable it
- **@toggle** - return **true** if the button should be checked/selected, **false** otherwise
