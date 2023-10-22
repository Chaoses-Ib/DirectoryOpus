# Buttons and Functions

Functions (such as those you add to toolbar buttons or hotkeys) can use the evaluator in a number of ways:

- The [label](/Manual/evaluator/applicable_contexts/functions/labels.md) can be dynamically generated using the **@label** modifier.
- The [icon](/Manual/evaluator/applicable_contexts/functions/icons.md) can be dynamically modified using the **@icon** and related modifiers.
- The button [tooltip](/Manual/evaluator/applicable_contexts/functions/tooltips.md) can be generated using an evaluation expression.
- Button [states](/Manual/evaluator/applicable_contexts/functions/dynamic_state.md) like enabled/disabled, hidden/shown and checked/unchecked can be modified using the evaluator.
- [Conditional behavior](/Manual/evaluator/applicable_contexts/functions/conditional_behavior.md) in buttons using **@if** and **@ifset** can be performed using the evaluator.
- The **[@eval](/Manual/evaluator/applicable_contexts/functions/evaluation_clauses.md)** modifier lets you run a line of evaluator code as part of a function.
- The return value of an evaluator expression can be [inserted](/Manual/evaluator/applicable_contexts/functions/insertion_code.md) into a command line using the \`{= ... =}\` code.
- The evaluator can be used to generate a [command line](/Manual/evaluator/applicable_contexts/functions/commands.md) that's then executed as if it were part of the function.
