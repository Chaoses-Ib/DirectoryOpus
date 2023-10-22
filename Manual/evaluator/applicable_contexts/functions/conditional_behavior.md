# Evaluator Conditional Button Behavior

You can use the evaluator with the various **@if** and **@ifset** [command modifiers](/Manual/reference/command_reference/command_modifier_reference.md) to introduce simple conditional behavior in functions.

Note that these modifiers can also be used [without the evaluator](/Manual/reference/command_reference/command_modifier_reference.md#@icon), so to use the evaluator you must begin the expression with a \`=\` character.

![](page>standard_variables&nodate&nouser&nofooter)

The return value from the evaluation expression will be used to determine the result of the condition. Return **true** if the lines following the modifier should be executed, or **false** to skip to the next **@if** / **@ifset** modifier.
