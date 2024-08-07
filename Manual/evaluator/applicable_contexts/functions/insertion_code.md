# Evaluation Insertion Code

You can insert the result of an evaluation expression into a command line using the `{= ... =}` insertion code.

The expression can insert the value of a variable - for example, `{=source=}` or perform a complicated calculation and return the value.

![](page>standard_variables&nodate&nouser&nofooter)

In this context, the evaluator can also access the values of the various [external control codes](/Manual/reference/command_reference/external_control_codes/README.md) as variables within the expression. For example, the current file path is available as the variable `filepath`.

Quotation marks are stripped by default from values supplied to the evaluator (e.g. `allfilepath` will not put quotes around any of the file paths). To enable quotes to be added, append `#q` to the variable name (e.g. `allfilepath#q`).

The return value from the evaluation expression will be inserted in the command line.
