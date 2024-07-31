# Vars

**Vars** 对象表示用户和脚本定义变量的集合。存在许多不同的变量集，它们具有不同的作用域。一些集合支持持久性变量，这些变量会在不同会话之间保存和重新加载。

<table>
<thead><tr><th>
作用域</th><th>
访问方式</th><th>

**支持持久性**</th><th>
描述
</th></tr></thead><tbody><tr><td>
全局</td><td>

**[DOpus](dopus.zh.md).vars**</td><td>
是</td><td>
可在整个 Opus 中使用的变量。任何函数或脚本都可以访问它们。
</td></tr><tr><td>
文件窗口</td><td>

**[Lister](lister.zh.md).vars**</td><td>
是</td><td>
特定于文件窗口的变量。持久性变量会根据文件窗口基础在文件窗口布局中保存。
</td></tr><tr><td>
标签页</td><td>

**[Tab](tab.zh.md).vars**</td><td>
是</td><td>
特定于特定标签页的变量。持久性变量会根据标签页基础在文件窗口布局中保存。
</td></tr><tr><td>
脚本</td><td>

**[Script](script.zh.md).vars  
[ScriptInitData](scriptinitdata.zh.md).vars**</td><td>
是</td><td>
特定于特定脚本加载项的变量。
</td></tr><tr><td>
对话框</td><td>

**[Dialog](dialog.zh.md).Vars**</td><td>
是</td><td>

特定于特定 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 的变量。
</td></tr><tr><td>
命令</td><td>

**[Command](command.zh.md).vars**</td><td>
否</td><td>
特定于特定函数的变量。它们不会从一个函数调用保存到另一个函数调用，也不支持持久性。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合:***[Var](var.zh.md)**</td><td>

返回集合中的变量集合。您可以枚举 **[Var](var.zh.md)** 元素，也可以通过其索引或名称引用特定元素。关于如何执行此操作的示例在下面的 **Set** 文档中。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
删除</td><td>

\<字符串:名称\></td><td>

*无*</td><td>

从集合中删除指定名称的变量。您还可以指定 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md) 来删除多个变量（或 \* 表示所有）。
</td></tr><tr><td>
存在</td><td>

\<字符串:名称\></td><td>

*布尔值*</td><td>

如果指定名称的变量存在于集合中，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
获取</td><td>

\<字符串:名称\></td><td>

*变体*</td><td>

返回指定名称的变量的值。  
您可以将此方法用作索引集合的替代方法。需要注意的一个区别是，此方法直接返回存储在变量中的 *值*。如果您需要包含值的 **[Var](var.zh.md)** 对象（例如，要调用 **var.Delete** 或更改 **var.persist**），则应改为索引集合。关于如何执行此操作的示例在下面的 **Set** 文档中。
</td></tr><tr><td>
设置</td><td>

\<字符串:名称\>  
\<变体:值\></td><td>

*无*</td><td>

将指定名称的值设置为指定值。您可以将此方法用作索引集合的替代方法。

您可以在 **Vars** 集合中存储任何类型的变量，但并非所有类型都可保存到磁盘。如果您希望变量具有持久性，则应仅使用 *布尔值*、*整数*、*字符串*、*日期*、*货币* 或这些类型的 **[Vector](vector.zh.md)**。  
变量在默认情况下不是持久性的。如果您需要它们在重启后保存，则需要明确请求。以下是在 VBScript 中的一个示例：  
`Dim varName, varValue1, varValue2
 varName = "MyVariableName"

 if (DOpus.Vars.Exists(varName)) then
 varValue1 = DOpus.Vars.Get(varName)
 DOpus.Output varName & " = " & varValue1
 else
 DOpus.Output varName & " does not exist yet."
 end if

 varValue2 = "My Variable Value"

 DOpus.Vars.Set varName, varValue2
 DOpus.Vars(varName).persist = True`

以下是在 JScript 中的相同示例：  
`var varName = "MyVariableName";

 if (DOpus.Vars.Exists(varName)) {
 var varValue1 = DOpus.Vars.Get(varName);
 DOpus.Output(varName + " = " + varValue1);
 } else {
 DOpus.Output(varName + " does not exist yet.");
 }

 var varValue2 = "My Variable Value";

 DOpus.Vars.Set(varName, varValue2);
 DOpus.Vars(varName).persist = true;`

在第一次运行时，示例代码将显示变量不存在，并将该变量设置为一个值，并在之后开启持久性。如果再次运行，它将报告该变量的值，并且该值将在重启后保持持久性。
</td></tr></tbody>
</table>