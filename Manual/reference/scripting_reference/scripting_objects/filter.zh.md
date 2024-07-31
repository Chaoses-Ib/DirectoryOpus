# Filter

**Filter** 对象允许您创建 [文本过滤器](/Manual/file_operations/filtered_operations/textual_filters.zh.md)，其类型与 **查找** 工具以及 **复制** 等命令中使用的类型相同，以控制递归操作。

使用 **[dopusfactory](dopusfactory.zh.md).Filter** 方法创建新的过滤器对象。拥有 **Filter** 对象后，您可以：

- 使用 **[item](item.zh.md).MatchFilter** 方法查看文件或文件夹是否与过滤器匹配。
- 使用 **[command](command.zh.md).SetFilter** 方法将过滤器应用于命令。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
lasterror</td><td>

*object:***[filterparseerror](filterparseerror.zh.md)**</td><td>

如果 *valid* 返回 **False**，则可以使用此属性发现有关错误的信息。
</td></tr><tr><td>
valid</td><td>

*bool*</td><td>

如果过滤器创建成功（即解析过滤器文本时未遇到错误），则返回 **True**。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<string:clause\>  
或 \<object:**Filter**\>  
\[\<string:conjunction\>\]</td><td>

*bool*</td><td>

将子句添加到过滤器。如果以字符串形式提供，则将解析该子句，如果解析成功，则该方法返回 **True**。如果解析失败，请使用 **lasterror** 属性找出原因。或者，您可以添加另一个 **Filter** 对象。

*clause* 字符串必须是完全形成的 [文本过滤器](/Manual/file_operations/filtered_operations/textual_filters.zh.md) 子句。例如，`size match > 2 mb`

可选的 *conjunction* 字符串允许您选择是通过 **and** 还是 **or** 连接子句。如果未指定，则默认为 **and**。
</td></tr><tr><td>
Clear</td><td>

*none*</td><td>

*none*</td><td>
清除过滤的内容。
</td></tr><tr><td>
Set</td><td>

\<string:clause\>  
或 \<object:**Filter**\></td><td>

*bool*</td><td>

使用字符串或现有 **Filter** 对象的内容初始化过滤器。如果以字符串形式提供，则将解析该子句，如果解析成功，则该方法返回 **True**。如果解析失败，请使用 **lasterror** 属性找出原因。
</td></tr></tbody>
</table>