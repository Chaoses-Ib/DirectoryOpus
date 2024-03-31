# 函数中的求值子句

**@eval** 和 **@evalalways** [命令修饰符](/Manual/reference/command_reference/command_modifier_reference.zh.md) 让你可以在函数中内联地运行求值表达式。

其主要目的是设置变量，稍后可由其他修饰符（如 **@if**、**@icon**、**@label** 等）在函数中使用。

- 使用 **@eval** 设置的变量仅能被其他修饰符看到。它们在 Opus 执行工具栏动态更新时（例如，更新标签或图标）执行，但不会在函数实际运行时执行。
- 使用 **@evalalways** 设置的变量也可以在函数本身运行时看到。这意味着它们也可以通过 [求值插入代码](insertion_code.zh.md) 或生成的 [命令行](commands.zh.md) 进行访问。

例如，你可能想要一个在普通文件系统文件夹和其他位置中表现不同的按钮。你可以使用 **@eval** 子句一次计算文件夹类型，然后在后续行中引用它。

    @eval:=type = pathtype(source); fIsFileSystem = (type == "shell" || type == "filesys")
    @enableif:=fIsFileSystem
    @label:=fIsFileSystem ? ("在资源管理器中打开 " + filepart(displayname(source))) : ("已禁用 (" + type + ")")
    explorer.exe "{sourcepath}"

![](page>standard_variables&nodate&nouser&nofooter)

求值表达式的返回值将被用于确定条件的结果。如果应该执行修饰符后面的行，则返回 **true**；如果要跳到下一个 **@if** / **@ifset** 修饰符，则返回 **false**。