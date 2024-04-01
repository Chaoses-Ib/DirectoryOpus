# 工具栏

**Toolbars** 对象使您能够枚举 Directory Opus 配置中定义的所有工具栏（无论当前是否已启用）。它使用 **[DOpus](dopus.zh.md).Toolbars** 方法检索。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合：***[Toolbar](toolbar.zh.md)**</td><td>

返回可枚举的 **[Toolbar](toolbar.zh.md)** 对象集合。
</td></tr><tr><td>
fdb</td><td>

*字符串*  
或  
**[Vector](vector.zh.md):***字符串*</td><td>

返回当前选中的文件列表工具栏的名称。  
如果 FDB 工具栏已禁用，则返回字符串 **!static** 以指示静态标头。  
如果只配置了一个 FDB 工具栏（通常情况），则它将被作为一个简单字符串返回。  
如果配置了多个 FDB 工具栏，则将返回一个字符串 **[Vector](vector.zh.md)**。  
如果只需要第一个工具栏的名称而无需担心其它工具栏的数量（如果有），可以在 JScript 和 VBScript 中使用 **DOpus.toolbars.fdb(0)**。否则，在 VBScript 中使用 **TypeName(...)**，在 JScript 中使用 **typeof** 确定返回类型。
</td></tr><tr><td>
viewer</td><td>

*string*</td><td>
返回当前选中的查看器工具栏的名称。
</td></tr></tbody>
</table>