# Evaluator Button Icons

In a toolbar or menu button, you can use the **@icon**, **@iconp** and **@icon!** modifiers to set button icons dynamically using the evaluator.

Note that these modifiers can also be used [without the evaluator](/Manual/reference/command_reference/command_modifier_reference.md#@icon), so to use the evaluator you must begin the expression with a \`=\` character.

![](page>standard_variables&nodate&nouser&nofooter)

The return value from the evaluation expression will be used as the icon for the button. The icon can be specified in a number of ways:

- An icon from one of the internal [icon sets](/Manual/reference/icon_sets/RAEDME.md), e.g. \`"largeicons"\`
- A path to an EXE or DLL to extract an icon, e.g. \`"C:\Windows\System32\imgres.dll,40"\`
- The name of an external image file, e.g. \`"C:\Images\MyButton.png"\`
