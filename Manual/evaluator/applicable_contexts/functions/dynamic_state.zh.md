可以通过影响工具栏按钮状态的各种 [命令修饰符](/Manual/reference/command_reference/command_modifier_reference.zh.md) 将求值器和它们一起使用：

- **@hideif** / **@showif** - 动态隐藏或显示按钮
- **@disableif** / **@enableif** - 动态禁用或启用按钮
- **@toggle** - 控制按钮显示为已选中/选中或未选中/未选中

请注意，这些修饰符也可以 [在没有求值器的情况下](/Manual/reference/command_reference/command_modifier_reference.zh.md#@icon) 使用，因此要使用求值器时你必须使用字符“=`”开头。

![](page>standard_variables&nodate&nouser&nofooter)

来自求值表达式的返回值将用于确定状态。其含义取决于相关修饰符：

- **@hideif** - 返回 **true** 以隐藏按钮，**false** 以显示按钮
- **@showif** - 返回 **true** 以显示按钮，**false** 以隐藏按钮
- **@disableif** - 返回 **true** 以禁用按钮，**false** 以启用按钮
- **@enableif** - 返回 **true** 以启用按钮，**false** 以禁用按钮
- **@toggle** - 返回 **true** 则表明按钮应被选中/选择，**false** 则表明按钮不应该被选中/选择