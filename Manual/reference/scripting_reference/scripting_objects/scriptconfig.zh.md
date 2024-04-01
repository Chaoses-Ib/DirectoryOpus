**ScriptConfig** 对象通过 **[ScriptInitData](scriptinitdata.zh.md).config** 和 **[Script](script.zh.md).config** 属性访问。**[ScriptInitData](scriptinitdata.zh.md).config** 属性允许一个脚本（在其 **[OnInit](../scripting_events/oninit.zh.md)** 方法中）指定其所支持的配置属性，并为它们提供默认值。然后，在 **[OnInit](../scripting_events/oninit.zh.md)** 中分配的属性将可以在配置中供用户编辑，并且用户编辑过的配置然后可以使用 **[Script](script.zh.md).config** 通过其它脚本方法来访问。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

\<配置属性\></td><td>

*变量*</td><td>

**ScriptConfig** 对象的属性完全由脚本本身确定。

在 **OnInit** 方法中，将需要对该对象进行分配的任何配置属性的默认值。每个默认值的数据类型都控制着属性的数据类型。

配置页面仅支持编辑某些类型变量，所以你必须仅分配兼容类型属性。配置支持：

- 布尔选项（**True** 或 **False**） - 类型的变量必须是 *bool*
- 数值选项 - 类型必须是 *int*
- 字符串选项 - 类型必须是 *string*
- 多行字符串选项 - 类型必须是字符串并且至少包含一个 *CR/LF* 对儿。请注意，默认值中跟在后面的 *CR/LF* 将被删除。
- 多个字符串选项 - 类型必须是字符串的 **[Vector](vector.zh.md)**
- 下拉列表 - 类型必须是 **[Vector](vector.zh.md)**，第一个元素是一个 *int*（指定默认选择），其余元素为字符串。
</td></tr></tbody>
</table>