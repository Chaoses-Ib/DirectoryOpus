# 求值器按钮图标

在工具栏或菜单按钮中，可以使用 **@icon**、**@iconp** 和 **@icon!** 修饰符，使用求值器动态设置按钮图标。

注意，这些修饰符也可以 [在没有求值器的情况下](/Manual/reference/command_reference/command_modifier_reference.zh.md#@icon) 使用，因此要使用求值器，必须在表达式开头使用 `=` 字符。

![](page>standard_variables&nodate&nouser&nofooter)

求值表达式的返回值将用作按钮图标。图标可以用多种方式指定：

- 来自内部 [图标集](/Manual/reference/icon_sets/README.zh.md) 的图标，例如 `"largeicons"`
- 从 EXE 或 DLL 提取图标的路径，例如 `"C:\Windows\System32\imgres.dll,40"`
- 外部图像文件的名称，例如 `"C:\Images\MyButton.png"`