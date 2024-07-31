# FiletypeGroups

**FileTypeGroups** 对象代表一个 **[FiletypeGroup](filetypegroup.zh.md)** 对象集合。该对象可以被枚举以检索它所代表的组。

您可以从 **[DOpus](dopus.zh.md).filetypegroups** 属性获取一个表示所有已配置 [文件类型组](/Manual/file_types/file_type_groups.zh.md) 的对象。 **[Item](item.zh.md).groupsobject** 属性返回一个 **FiletypeGroups** 对象，该对象仅限于 **[Item](item.zh.md)** 是其成员的组。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*collection:***[FiletypeGroup](filetypegroup.zh.md)**</td><td>
允许您枚举此对象所代表的文件类型组。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
GetGroup</td><td>

\<string:group\></td><td>

*object:***[FiletypeGroup](filetypegroup.zh.md)**  
或  
*bool (***False***)*</td><td>

在文件类型组集合中搜索指定名称的组。  
如果 Opus 未在英文环境中运行，则首先比较翻译后的名称；如果未找到，它将搜索内置组的原生英文名称。  
返回一个 **[FiletypeGroup](filetypegroup.zh.md)** 对象，如果未找到则返回 **False**。
</td></tr><tr><td>
MatchExt</td><td>

\<string:filename\></td><td>

*object:***FiletypeGroups**</td><td>

返回一个新的 **FiletypeGroups** 对象，该对象包含指定文件名（或文件扩展名）所属的组的子集。您通常只在由 **[DOpus](dopus.zh.md).filetypegroups** 属性返回的对象上调用此方法。
</td></tr><tr><td>
Translate</td><td>

\<string:group\></td><td>

*string*</td><td>

返回指定内置文件类型组的翻译后的名称。  
如果未找到或不存在翻译，则返回输入字符串。

例如，在法语环境中运行时，使用 "Movies" 作为输入字符串调用此方法将返回 "Vidéos"。
</td></tr></tbody>
</table>