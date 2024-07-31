# ScriptConfig

**ScriptConfig** 对象可以通过 **[ScriptInitData](scriptinitdata.zh.md).config** 和 **[Script](script.zh.md).config** 属性访问。**[ScriptInitData](scriptinitdata.zh.md).config** 属性允许脚本（在其 **[OnInit](../scripting_events/oninit.zh.md)** 方法中）指定它支持哪些配置属性，并为它们提供默认值。在 **[OnInit](../scripting_events/oninit.zh.md)** 中分配的属性将在 Preferences 中供用户编辑，然后其它脚本方法可以使用 **[Script](script.zh.md).config** 访问用户编辑的配置。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

\<configuration property\></td><td>

*variant*</td><td>

**ScriptConfig** 对象的属性完全由脚本本身决定。

在 **OnInit** 方法中，将您希望为此对象分配的任何配置属性的默认值分配给它。每个默认值的类型控制属性的类型。

Preferences 页面只支持编辑某些类型的变量，因此您只能分配兼容类型的属性。Preferences 支持：

- 布尔选项（**True** 或 **False**） - 变量类型必须为 *bool*
- 数字选项 - 变量类型必须为 *int*
- 字符串选项 - 变量类型必须为 *string*
- 多行字符串选项 - 变量类型必须为 string 并且必须包含至少一对 *CR/LF*。请注意，尾随的 *CR/LF* 将从默认值中删除。
- 多个字符串选项 - 变量类型必须为 *字符串* 的 **[Vector](vector.zh.md)**
- 下拉列表 - 变量类型必须为 **[Vector](vector.zh.md)**，第一个元素为 *int*（指定默认选择），其余元素为字符串。
</td></tr></tbody>
</table>