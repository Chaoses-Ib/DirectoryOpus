# Toolbars

**Toolbars** 对象允许您枚举 Directory Opus 配置中定义的所有工具栏（无论当前是否已启用）。它可以通过 **[DOpus](dopus.zh.md).Toolbars** 方法获取。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合:***[Toolbar](toolbar.zh.md)**</td><td>

返回一个 **[Toolbar](toolbar.zh.md)** 对象的集合，您可以枚举它们。
</td></tr><tr><td>
fdb</td><td>

*字符串*  
或  
**[Vector](vector.zh.md):***字符串*</td><td>

返回当前选定文件列表工具栏的名称。  
如果 FDB 工具栏已禁用，则返回字符串 **!static** 以指示静态标题。  
如果只配置了一个 FDB 工具栏（通常情况下），则它将作为简单字符串返回。  
如果配置了多个 FDB 工具栏，则返回一个 **[Vector](vector.zh.md)** 字符串。  
您可以使用 **DOpus.toolbars.fdb(0)** 在 JScript 和 VBScript 中，如果您只想获取第一个工具栏的名称，而不必担心其它工具栏的数量（如果有）。 否则，在 VBScript 中使用 **TypeName(...)** 以及在 JScript 中使用 **typeof** 来确定返回类型。
</td></tr><tr><td>
查看器</td><td>

*字符串*</td><td>
返回当前选定查看器工具栏的名称。
</td></tr></tbody>
</table>