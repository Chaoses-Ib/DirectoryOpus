# 过滤器

**Filter** 对象允许您创建与 **查找** 工具和 **复制** 等命令使用的类型一样的 [文本过滤器](/Manual/file_operations/filtered_operations/textual_filters.zh.md)，以控制递归操作。

使用 **[dopusfactory](dopusfactory.zh.md).Filter** 方法创建新的过滤器对象。获得 **Filter** 对象后，您可：

- 使用 **[item](item.zh.md).MatchFilter** 方法查看某个文件或文件夹是否匹配过滤器。
- 通过 **[command](command.zh.md).SetFilter** 方法将过滤器应用于命令。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
lasterror</td><td>

*对象:***[filterparseerror](filterparseerror.zh.md)**</td><td>

如果 *valid* 返回 **False**，您可以使用此属性了解有关错误的信息。
</td></tr><tr><td>
valid</td><td>

*bool*</td><td>

如果过滤器已成功创建（即解析过滤器文本时未遇到错误），则返回 **True**。
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

将一条子句添加到过滤器。如果子句以字符串的形式提供，则会解析该子句，并且如果解析成功，则方法返回 **True**。如果解析失败，请使用 **lasterror** 属性进行原因查找。或者，您可以添加另一个 **Filter** 对象。

*clause* 字符串必须是格式完整的 [文本过滤器](/Manual/file_operations/filtered_operations/textual_filters.zh.md) 子句。例如，`size match > 2 mb`

可选的 *conjunction* 字符串允许您选择是否通过 **and** 或 **or** 来连接子句。如果未指定，则默认为 **and**。
</td></tr><tr><td>
Clear</td><td>

*无*</td><td>

*无*</td><td>
清除过滤器内容。
</td></tr><tr><td>
Set</td><td>

\<string:clause\>  
或 \<object:**Filter**\></td><td>

*bool*</td><td>

使用字符串或现有 **Filter** 对象的内容初始化过滤器。如果子句以字符串的形式提供，则会解析该子句，并且如果解析成功，则方法返回 **True**。如果解析失败，请使用 **lasterror** 属性进行原因查找。
</td></tr></tbody>
</table>