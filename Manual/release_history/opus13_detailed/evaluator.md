##### Directory Opus 13 - Detailed release notes

# Evaluator

- The "Evaluator" is a new type of simple scripting. It allows things like conditional logic and string manipulation in places where full scripting wouldn't be suitable.
- The Evaluator does not replace the old scripting and commands. Rather, it is somewhere between the two and works in conjunction with them. It is less powerful than full-blown scripting, but also has lower overheads and is guaranteed not to get stuck in loops (since it has no loops!). This allows it to be used in places where calling a normal script could cause problems.
- For example, Evaluator code can be used to make a toolbar button change its icon and label based on some criteria.
- Supports conditional logic, simple boolean, math and string operations, and functions and variables for getting various information from Opus.
- Tools \> Opus CLI / Ad-Hoc Script Editor now has an Evaluator mode which lets you experiment with it.
  - Start typing, or push Ctrl+Space, for popup suggestions listing Evaluator functions.
  - In the pop-up list, hover over a function for detailed information.
- *Command:* \<ib:inline-code\>`Set EVALUATORDISABLE=Toggle`\</ib:inline-code\> lets you disable the evaluator if something goes wrong. It will be re-enabled on the next restart, or via running the command again.
- Use of the Evaluator is discussed more in other sections, since it can be used in various ways.

------------------------------------------------------------------------

Next: [Lister Defaults](/Manual/release_history/opus13_detailed/lister_defaults.md)
