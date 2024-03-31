**FiletypeGroup** 对象表示文件类型组（在 [文件类型组](/Manual/file_types/file_type_groups.zh.md) 部分的 [文件类型编辑器](/Manual/file_types/README.zh.md) 中进行配置）。你可以通过查询 **[项](item.zh.md)**.groups 属性或使用 **[FiletypeGroups](filetypegroups.zh.md)** 对象来查找文件所属的组。  

注意：如果你正在查找有关文件列表如何根据一个显示的列对项目进行分组的信息，而不是文件属于哪一个 *文件类型组*，请参阅 **[FileGroup](filegroup.zh.md)** 对象。  
  
可以枚举此对象以获取它表示的文件扩展名。  

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
在你安装 Opus 时预定义的组具有内部名称，例如 *"Archives"* 和 *"Music"*（它们也是英文显示名称）。  
用户定义的组具有唯一的内部名称，自动生成的 GUID 字符串，例如 *"{C4B716ED-2A9C-43C6-B325-7DADDEEFADA9}"*。
</td></tr><tr><td>
display_name</td><td>

*string*</td><td>

返回此组的显示名称。  
显示名称是你将在文件类型编辑器中看到的内容。显示名称在不同语言中可能会被不同地翻译。
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

测试文件名（或扩展名）是否属于此组。如果文件属于此组，则返回 **True**，如果不属于则返回 **False**。
</td></tr></tbody>
</table>