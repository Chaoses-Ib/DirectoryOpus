# FiletypeGroup

**FiletypeGroup** 对象表示一个文件类型组（如在 [文件类型编辑器](/Manual/file_types/README.zh.md) 的 [文件类型组](/Manual/file_types/file_type_groups.zh.md) 部分中配置的那样）。您可以通过查询 **[Item](item.zh.md)**.groups 属性或使用 **[FiletypeGroups](filetypegroups.zh.md)** 对象来查找文件属于哪些组。

注意：如果您正在寻找有关文件列表如何根据显示列之一对项目进行分组的信息，而不是文件属于哪个 *文件类型组*，请参阅 [FileGroup](filegroup.zh.md) 对象。

此对象可以枚举以检索它所代表的文件扩展名。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*string*</td><td>

返回此组的内部名称。
内部名称在所有语言中始终相同。
您安装 Opus 时预定义的组具有像 *"Archives"* 和 *"Music"* 这样的内部名称（它们也是它们的英文显示名称）。
用户定义的组具有唯一的自动生成的 GUID 字符串，例如 *"{C4B716ED-2A9C-43C6-B325-7DADDEEFADA9}"* 作为内部名称。
</td></tr><tr><td>
display_name</td><td>

*string*</td><td>

返回此组的显示名称。
显示名称是您在文件类型编辑器中看到的名称。显示名称在不同的语言中可能会有不同的翻译。
</td></tr><tr><td>
tiles</td><td>

*string*</td><td>
返回此组的平铺模式定义字符串。
</td></tr><tr><td>
tooltip</td><td>

*string*</td><td>
返回此组的工具提示定义字符串。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
MatchExt</td><td>

\<string:filename\></td><td>

*bool*</td><td>

测试文件名（或扩展名）是否属于此组。如果文件是该组的成员，则返回 **True**，否则返回 **False**。
</td></tr></tbody>
</table>