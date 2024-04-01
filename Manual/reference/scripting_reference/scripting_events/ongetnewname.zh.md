**OnGetNewName** 事件是 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md) 的三个备用入口点之一。另两个事件 - **Rename_GetNewName** 和 **Rename_GetNewName2**，已弃用，应仅用于与 Opus 10 的向后兼容性。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnGetNewName
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[GetNewNameData](../scripting_objects/getnewnamedata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*布尔值* 或 *字符串*
</td></tr><tr><td>

**说明：**</td><td>

当使用重命名脚本时，**OnGetNewName** 事件会针对每个选定的文件和文件夹进行调用，使脚本有机会修改名称。  
**GetNewNameData.item** 属性会识别正在重命名的项目。你可以通过运用多种 **[Item](../scripting_objects/item.zh.md)** 属性访问项目元数据以及其它信息。  
**oldname** 属性会返回在 [重命名对话框](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md) 中由用户输入的“旧名称”模式。**newname** 属性会返回项目的提议新名称。这是重命名对话框（大写、自动编号等）中所有其它非脚本选项的结果。

你可以从此事件返回两种不同的类型：

- *布尔值*：如果返回 **True**，项目将不会被重命名。如果返回 **False**（这是默认值），项目将被重命名为提议的新名称（**newname** 属性）。
- *字符串*：你可以返回一个 *字符串* 来为项目指定一个新名称。
</td></tr></tbody>
</table>