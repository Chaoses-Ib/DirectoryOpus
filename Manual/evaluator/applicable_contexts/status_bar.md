# Status Bar

You can use the evaluator in the [status bar](/Manual/preferences/preferences_categories/file_displays/status_bar.md) to insert text returned by the evaluation.

Use the `{= ... =}` code to insert an evaluation expression. The expression between the `{=` and the `=}` markers can span multiple lines if needed. The return value of the expression is inserted into the status bar.

In this evaluation context, the following variables are available:

\<commandtable columns="3"\> \$\$ Variable \$\$ Type \$\$ Description \$\$ \<nobr\>*status code*\</nobr\> \$\$ *varies* \$\$ All the [status bar codes](/Manual/reference/status_bar_codes/README.md) are available as variables in this evaluation context (other than those that generate images or graphs).

Note that some keywords may use characters like a `:` that aren't valid in variable names - to access them, use the [val](/Manual/reference/evaluator/val.md) function. \$\$ path \$\$ *path* \$\$ Returns the current path the status bar is displaying information for. \</commandtable\>

The return value should be a *str* that will be inserted into the status bar.
