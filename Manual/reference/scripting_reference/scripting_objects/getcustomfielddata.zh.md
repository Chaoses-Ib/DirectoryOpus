# GetCustomFieldData

如果一个 [重命名脚本](/Manual/file_operations/renaming_files/advanced_rename/rename_scripts.zh.md) 实现了 **[OnGetCustomFields](../scripting_events/ongetcustomfields.zh.md)** 事件，该方法会在重命名对话框运行脚本时收到一个 **GetCustomFieldData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
fields</td><td>

*object:***[CustomFieldData](customfielddata.zh.md)**</td><td>

返回一个 **[CustomFieldData](customfielddata.zh.md)** 对象，脚本可以使用它将自定义字段添加到 *重命名* 对话框。添加到该对象中的每个属性都将在对话框中创建一个新字段，允许用户向重命名脚本提供更多信息。
</td></tr><tr><td>
field_labels</td><td>

*object:***[Map](map.zh.md)**</td><td>

这允许你为脚本的自定义字段分配标签，这些标签会显示在 *重命名* 对话框中。为此，将此属性设置为一个通过 **[DOpusFactory](dopusfactory.zh.md).Map** 方法创建的 **[Map](map.zh.md)**，其中包含名称/标签字符串对。
</td></tr><tr><td>
field_tips</td><td>

*object:***[Map](map.zh.md)**</td><td>

这允许你为脚本创建的任何编辑字段分配 "提示信息"。提示信息会显示在空的编辑字段中，提示用户该字段需要什么类型的数据。要使用它，请将此属性设置为一个通过 **[DOpusFactory](dopusfactory.zh.md).Map** 方法创建的 **[Map](map.zh.md)**，其中包含名称/提示信息字符串对。
</td></tr><tr><td>
focus</td><td>

*string*</td><td>

你可以使用此字段指定当你的字段第一次出现时哪个控件默认获得输入焦点。将其设置为所需控件的名称。你还可以指定 **!oldname** 或 **!newname** 将焦点分配给标准的旧名称和新名称字段。
</td></tr></tbody>
</table>