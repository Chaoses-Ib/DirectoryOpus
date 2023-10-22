# Evaluator-generated Command Lines

The evaluator can be used to generate entire command lines. There are two types of command lines it can generate.

##### Executable commands

When the function is run, the return value from the evaluation expression will be executed as if it had always been part of the function.

To use this, simply begin the line with a \`=\` character, followed by the expression.

If the expression doesn't return a string to run as a command, the line is simply skipped over and execution moves on to the next line in the function. This lets you have functions that are composed of multiple evaluator command lines with a final command returned at the end.

##### Dynamic commands

In this mode, it can generate commands that are used to generate dynamic lists of buttons. For example, \`Go DRIVEBUTTONS\` is a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/RAEDME.md) that generates a list of drive buttons.

This mode is accessed using the **@ctx:** modifier. The command returned by the expression will be used to generate dynamic buttons.

##### Variables

![](page>standard_variables&nodate&nouser&nofooter)

When generating executable commands, the evaluator can also access the values of the various [external control codes](/Manual/reference/command_reference/external_control_codes/RAEDME.md) as variables within the expression. For example, the current file path is available as the variable \`filepath\`.

The return value from the evaluation expression should be a *str*.

- For executable commands, it will be executed as if it were a line of the function.
- For dynamic commands, any dynmaic buttons it generates will appear on the toolbar.
