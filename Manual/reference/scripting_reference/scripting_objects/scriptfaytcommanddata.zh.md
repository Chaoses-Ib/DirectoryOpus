# ScriptFAYTCommandData

**ScriptFAYTCommandData** 对象传递给任何 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 的脚本定义入口点，这些插件 [扩展了即时查找字段](/Manual/scripting/example_scripts/extending_the_fayt.zh.md)。这些事件的方法名称由脚本本身定义，但通常称为 **[onScriptFAYTCommand](../scripting_events/onscriptfaytcommand.zh.md)**。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
cmdline</td><td>

*string*</td><td>
提供用户在即时查找字段中输入的文本。
</td></tr><tr><td>
fayt</td><td>

*string*  
或 *bool*</td><td>

正在调用的即时查找扩展命令的名称。这允许您使用相同的入口点来实现多个即时查找扩展（如果需要）。如果值为 **False**，则这根本不是即时查找扩展，而是 [脚本命令](scriptcommanddata.zh.md)。
</td></tr><tr><td>
flags</td><td>

*int*</td><td>

提供用户为您的即时查找扩展启用的所有标志的总和。这些来自您在使用 **[ScriptFAYTCommand](scriptfaytcommand.zh.md)** 对象初始化扩展时指定的 **flags** 属性。

您的脚本可以使用 **[Script](script.zh.md).Update即时查找Flags** 方法更新用户配置中的标志。
</td></tr><tr><td>
key</td><td>

*string*</td><td>

如果用户按下回车键以触发您的即时查找扩展，则这将等于字符串 **"return"**。
</td></tr><tr><td>
suggest</td><td>

*bool*</td><td>

如果设置为 **True**，则表示您应该使用 **[tab](tab.zh.md).UpdateFAYTSuggestions** 方法更新建议列表。
</td></tr><tr><td>
quickkey</td><td>

*string*</td><td>
提供最初触发此模式下即时查找的键。
</td></tr><tr><td>
tab</td><td>

*object:***[tab](tab.zh.md)**</td><td>
表示与即时查找交互的标签。
</td></tr></tbody>
</table>