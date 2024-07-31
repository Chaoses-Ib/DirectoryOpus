# OnGetNewName

**OnGetNewName** 事件是[重命名脚本](/Manual/scripting/rename_scripts/README.zh.md)的三种可选入口点之一。另外两个事件 - **Rename_GetNewName** 和 **Rename_GetNewName2** 已经过时，只应用于与 Opus 10 的向后兼容。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnGetNewName
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[GetNewNameData](../scripting_objects/getnewnamedata.zh.md)**
</td></tr><tr><td>

**返回类型:**</td><td>

*bool* 或 *string*
</td></tr><tr><td>

**描述:**</td><td>

使用重命名脚本时，**OnGetNewName** 事件会针对每个选定的文件和文件夹调用，让脚本有机会修改名称。  
**GetNewNameData.item** 属性标识正在重命名的项目。您可以使用各种 **[Item](../scripting_objects/item.zh.md)** 属性访问项目的元数据和其它信息。  
**oldname** 属性返回用户在[重命名对话框](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)中输入的“旧名称”模式。**newname** 属性返回项目的建议新名称。它代表重命名对话框中所有其它非脚本选项（大写、自动编号等）的结果。

您可以从该事件返回两种不同类型：

- *bool*: 如果您返回 **True**，则不会重命名项目。如果您返回 **False**（这是默认值），则将项目重命名为建议的新名称（**newname** 属性）。
- *string*: 您可以返回一个 *string* 来指定项目的新的名称。
</td></tr></tbody>
</table>