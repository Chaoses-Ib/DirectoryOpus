**Script即时查找CommandData** 对象会传递给任何 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 的脚本定义的入口点，这些加载项 [扩展了即时查找字段](/Manual/scripting/example_scripts/extending_the_fayt.zh.md)。这些事件的方法名称由脚本本身定义，但通常被称为 **[onscriptfaytcommand](../scripting_events/onscriptfaytcommand.zh.md)**。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
cmdline</td><td>

*string*</td><td>
提供用户在即时查找字段中键入的文本。
</td></tr><tr><td>
fayt</td><td>

*string*  
或 *bool*</td><td>

要调用的即时查找扩展命令的名称。这允许您使用相同的入口点按需执行多个即时查找扩展。如果值是 **False**，则这根本不是即时查找扩展，而是常规 [脚本命令](scriptcommanddata.zh.md)。
</td></tr><tr><td>
flags</td><td>

*int*</td><td>

提供用户为即时查找扩展启用所有标记之和。这些标记来自您通过 **[scriptfaytcommand](scriptfaytcommand.zh.md)** 对象初始化扩展时指定的 **flags** 属性。

脚本可以使用 **[Script](script.zh.md).Update即时查找Flags** 方法更新用户配置中的标记。
</td></tr><tr><td>
key</td><td>

*string*</td><td>

如果用户按下回车键触发了即时查找扩展，这将等于字符串 **"return"**。
</td></tr><tr><td>
suggest</td><td>

*bool*</td><td>

如果设置为 **True**，这是一个提示，说明您应通过 **[tab](tab.zh.md).Update即时查找Suggestions** 方法更新建议列表。
</td></tr><tr><td>
quickkey</td><td>

*string*</td><td>
提供在该模式中最初触发即时查找的键。
</td></tr><tr><td>
tab</td><td>

*object:***[tab](tab.zh.md)**</td><td>
表示与即时查找进行交互的标签页。
</td></tr></tbody>
</table>