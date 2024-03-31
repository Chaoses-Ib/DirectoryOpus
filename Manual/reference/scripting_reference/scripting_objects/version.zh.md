# 版本**

**版本**对象从 **[DOpus](dopus.zh.md).version **属性中检索。它提供了有关 Directory Opus 当前版本的信息。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>

完整版本字符串（如在 *关于* 对话框中所示）。
</td></tr><tr><td>
build</td><td>

*int*</td><td>
当前版本号。
</td></tr><tr><td>
module</td><td>

*字符串*</td><td>

当前模块版本（**dopus.exe** 自身的版本）。您还可以将其作为 *集合：int* 来枚举或索引，以检索模块版本的四个单独数字。
</td></tr><tr><td>
product</td><td>

*字符串*</td><td>

当前产品版本（Directory Opus 作为一个整体的发布版本）。您还可以将其作为 *集合：int* 来枚举或索引，以检索产品版本的四个单独数字。
</td></tr><tr><td>
winver</td><td>

*对象*:**[WinVer](winver.zh.md)**</td><td>

返回一个 **[WinVer](winver.zh.md)** 对象，它提供了有关当前 Windows 版本的信息。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AtLeast</td><td>

\<字符串：版本\></td><td>

*布尔*</td><td>

如果 Opus 当前版本为指定版本或更高版本，则返回 **True**。您可以仅指定主版本（例如 *"11"*）、主版本和次版本（例如 *"11.3"*）或特定 beta 版本（例如 *"11.3.1"*）。
</td></tr></tbody>
</table>