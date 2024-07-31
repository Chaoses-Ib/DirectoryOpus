# Evaluator Button Colors

In a toolbar or menu button, you can use the **@color** modifier to set the text and background colors of the button dynamically using the evaluator.

As a very basic example, `@color:=text="#000000"; back="#ff0000";` would set the text color to black and the background color to red.

To specify separate colors for light and dark modes, you could use something like this:

`@color:=SysInfo("DarkMode") ? { text="#ff0000"; back="#ffff00"; } : { text="#0000ff"; back="#00ffff"; }`

![](page>standard_variables&nodate&nouser&nofooter)

The [SysInfo](/Manual/reference/evaluator/sysinfo.md) function can also be useful for testing global properties, like whether Opus is in dark or light mode.

The evaluator clause should set the value of the `text` and `back` variables. You can specify either a hex color string ("#RRGGBB") or decimal color string ("RRR,GGG,BBB"). You can also return "default" to get the button's defaults, or "none" to get the toolbar's defaults.
