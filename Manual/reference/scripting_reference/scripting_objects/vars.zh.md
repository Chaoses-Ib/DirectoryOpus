# Vars

**Vars**对象表示用户和脚本定义的变量的集合。有许多不同的变量集，具有不同的范围。有些集支持持久变量，这些变量从一个会话保存并重新加载到另一个会话。

<table>
<thead><tr><th>
范围</th><th>
访问方式</th><th>

**支持持久性**</th><th>
说明
</th></tr></thead><tbody><tr><td>
全局</td><td>

**[DOpus](dopus.zh.md).vars**</td><td>
是</td><td>
Opus 中可用的变量。任何函数或脚本都可以访问它们。
</td></tr><tr><td>
文件窗口</td><td>

**[文件窗口](lister.zh.md).vars**</td><td>
是</td><td>
文件窗口中的局部变量。持久变量在文件窗口布局中以每个文件窗口的方式保存。
</td></tr><tr><td>
标签页</td><td>

**[Tab](tab.zh.md).vars**</td><td>
是</td><td>
特定标签页中的局部变量。持久变量在文件窗口布局中以每个标签页的方式保存。
</td></tr><tr><td>
脚本</td><td>

**[Script](script.zh.md).vars  
[ScriptInitData](scriptinitdata.zh.md).vars**</td><td>
是</td><td>
特定脚本加载项中的局部变量。
</td></tr><tr><td>
对话框</td><td>

**[Dialog](dialog.zh.md).Vars**</td><td>
是</td><td>

与特定 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)绑定的变量。
</td></tr><tr><td>
命令</td><td>

**[Command](command.zh.md).vars**</td><td>
否</td><td>
特定函数中的局部变量。它们不会从函数的一次调用保存到另一次调用，也不支持持久性。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合:***[Var](var.zh.md)**</td><td>

返回集合中的变量集合。你可以枚举 **[Var](var.zh.md)** 元素或通过其索引或名称引用某个特定元素。关于如何进行此操作的示例在 **Set** 文档中（见下文）。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
Delete</td><td>

\<string:name\></td><td>

*无*</td><td>

从集合中删除名为变量。你还可以指定 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md) 以删除多个变量（或对所有变量使用 \*）。
</td></tr><tr><td>
Exists</td><td>

\<string:name\></td><td>

*bool*</td><td>

如果集合中存在名为变量，则返回 **True**，如果不存在，则返回 **False**。
</td></tr><tr><td>
Get</td><td>

\<string:name\></td><td>

*variant*</td><td>

返回名为变量的值。  
你可以使用此方法作为索引集合的替代方法。需要注意的一个区别是，此方法直接返回存储在变量中的 *值*。如果你需要包含该值（例如，要调用 **var.Delete** 或更改 **var.persist**) 的 **[Var](var.zh.md)** 对象，则应该改索引该集合。关于如何进行此操作的示例在 **Set** 文档中（见下文）。
</td></tr><tr><td>
Set</td><td>

\<string:name\>  
\<variant:value\></td><td>

*无*</td><td>

将名为值设置为指定的值。  
你可以使用此方法作为索引集合的替代方法。

你可以在 **Vars** 集合中存储任何类型的变量，但并非所有类型都可以保存到磁盘。如果你希望你的变量具有持久性，则应仅使用 *bool*、*int*、*string*、*date*、*currency* 或者这些类型的 **[Vector](vector.zh.md)**。  
默认情况下，变量不具有持久性。如果你需要在重新启动后保存它们，则需要显式请求。以下是在 VBScript 中的一个示例：  
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

在第一次运行时，示例代码会表示变量不反对并将其设置为某个值，之后再打开持久性。如果再次运行它，它将报告变量的值，并且该值会在重新启动后保持存在。
</td></tr></tbody>
</table>