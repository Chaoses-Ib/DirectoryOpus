**FileTypeGroups** 对象表示一系列 **[FiletypeGroup](filetypegroup.zh.md)** 对象。该对象可以进行枚举以获取它表示的组。

您可以从 **[DOpus](dopus.zh.md).filetypegroups** 属性获取表示所有已配置的 [文件类型组](/Manual/file_types/file_type_groups.zh.md) 的一个对象。**[Item](item.zh.md).groupsobject** 属性返回一个仅限于 **[Item](item.zh.md)** 成员所在的组的 **FiletypeGroups** 对象。

<table>
<thead>
<tr>
<th>
属性名称</th>
<th>
返回类型</th>
<th>
说明
</th>
</tr>
</thead>
<tbody>
<tr>
<td>
*\<默认值\>*</td>
<td>
*集合:***[FiletypeGroup](filetypegroup.zh.md)**</td>
<td>
让您枚举此对象表示的文件类型组。
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th>
方法名称</th>
<th>
**参数**</th>
<th>
返回类型</th>
<th>
说明
</th>
</tr>
</thead>
<tbody>
<tr>
<td>
GetGroup</td>
<td>
\<string:group\></td>
<td>
*对象:***[FiletypeGroup](filetypegroup.zh.md)**  
或  
*bool (***False***)*</td>
<td>
在文件类型组集合中搜索指定名称的组。  
如果 Opus 未在英语环境运行，则首先比较翻译后的名称；如果未找到，则搜索内置组的本机英语名称。  
返回一个 **[FiletypeGroup](filetypegroup.zh.md)** 对象或在未找到时返回 **False**。
</td>
</tr>
<tr>
<td>
MatchExt</td>
<td>
\<string:filename\></td>
<td>
*对象:***FiletypeGroups**</td>
<td>
返回一个新的 **FiletypeGroups **对象，其中包含指定的文件名（或文件扩展名）所属的组的子集。您通常只会在 **[DOpus](dopus.zh.md).filetypegroups** 属性返回的对象上调用此方法。
</td>
</tr>
<tr>
<td>
Translate</td>
<td>
\<string:group\></td>
<td>
*string*</td>
<td>
返回指定名称的内置文件类型组的翻译名称。  
如果未找到或没有翻译，则返回输入字符串。

例如，在法语环境下运行时，使用 "Movies" 作为输入字符串调用此方法将返回 "Vidéos"。
</td>
</tr>
</tbody>
</table>