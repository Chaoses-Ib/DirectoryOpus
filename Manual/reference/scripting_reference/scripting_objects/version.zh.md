# Version

**版本** 对象是从 **[DOpus](dopus.zh.md).version** 属性中获取的。它提供有关 Directory Opus 当前版本的信息。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>

完整版本字符串（如 *关于* 对话框中所示）。
</td></tr><tr><td>
build</td><td>

*int*</td><td>
当前构建号。
</td></tr><tr><td>
module</td><td>

*字符串*</td><td>

当前模块版本（**dopus.exe** 本身的版本）。您也可以将其枚举或索引为 *集合:int* 以检索模块版本的各个四位数字。
</td></tr><tr><td>
product</td><td>

*字符串*</td><td>

当前产品版本（Directory Opus 整体的发布版本）。您也可以将其枚举或索引为 *集合:int* 以检索产品版本的各个四位数字。
</td></tr><tr><td>
winver</td><td>

*对象*:**[WinVer](winver.zh.md)**</td><td>

返回一个 **[WinVer](winver.zh.md)** 对象，该对象提供有关当前 Windows 版本的信息。
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

\<字符串:版本\></td><td>

*bool*</td><td>

如果当前版本的 Opus 是指定版本或更高版本，则返回 **True**。您可以仅指定主版本（例如 *"11"*）、主版本和次版本（例如 *"11.3"*）或特定测试版（例如 *"11.3.1"*）。
</td></tr></tbody>
</table>