你可以将求值器与各种 **@if** 和 **@ifset** [命令修饰符](/Manual/reference/command_reference/command_modifier_reference.zh.md) 结合使用，以便在函数中引入简单的条件行为。

请注意，这些修饰符[不使用求值器](/Manual/reference/command_reference/command_modifier_reference.zh.md#@icon) 也可以使用，因此要使用求值器，您必须以 `=` 字符开头。

![](page>standard_variables&nodate&nouser&nofooter)

从求值表达式返回的值将用于确定条件的结果。如果应执行修饰符后面的行，请返回 **true**，若要跳到下一个 **@if** / **@ifset** 修饰符，请返回 **false**。