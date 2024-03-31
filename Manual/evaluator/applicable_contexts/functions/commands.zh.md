# 求值器生成的命令行

求值器可用于生成整个命令行。它可以生成两种类型的命令行。

### 可执行命令

运行该函数时，求值表达式的返回值将被执行，就像它一直是函数的一部分一样。

要使用它，只需以 `=` 字符开头，后跟表达式。

如果表达式未返回要作为命令运行的字符串，则会跳过该行，并且执行将移至函数中的下一行。这使你可以使用由多个求值器命令行组成的函数，并在最后返回最终命令。

### 动态命令

在此模式下，它可以生成用于产生动态按钮列表的命令。例如，`Go DRIVEBUTTONS` 是一个 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)，它会生成一个驱动器按钮列表。

使用 **@ctx:** 修饰符访问此模式。表达式返回的命令将用于生成动态按钮。

### 变量

![](page>standard_variables&nodate&nouser&nofooter)

生成可执行命令时，求值器还可变数的形式访问表达式中的各种 [外部控制代码](/Manual/reference/command_reference/external_control_codes/README.zh.md) 的值。例如，当前文件路径可用作 `filepath` 变量。

求值表达式的返回值应为 *str*。

- 对于可执行命令，它将被执行，就像它是函数的一行。
- 对于动态命令，它生成的任何动态按钮都会出现在工具栏上。