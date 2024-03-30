# Status Bar

You can use the evaluator in the [status bar](/Manual/preferences/preferences_categories/file_displays/status_bar.md) to insert text returned by the evaluation.

Use the `{= ... =}` code to insert an evaluation expression. The expression between the `{=` and the `=}` markers can span multiple lines if needed. The return value of the expression is inserted into the status bar.

In this evaluation context, the following variables are available:

<table>
<thead><tr><th>
Variable</th><th>
Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

\<nobr\>*status code*\</nobr\></td><td>

*varies*</td><td>

All the [status bar codes](/Manual/reference/status_bar_codes/README.md) are available as variables in this evaluation context (other than those that generate images or graphs).

Note that some keywords may use characters like a `:` that aren't valid in variable names - to access them, use the [val](/Manual/reference/evaluator/val.md) function.
</td></tr><tr><td>
path</td><td>

*path*</td><td>
Returns the current path the status bar is displaying information for.
</td></tr></tbody>
</table>

The return value should be a *str* that will be inserted into the status bar.
