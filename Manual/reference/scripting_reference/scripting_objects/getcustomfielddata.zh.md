如果 [重命名脚本](/Manual/file_operations/renaming_files/advanced_rename/rename_scripts.zh.md) 实现 **[OnGetCustomFields](../scripting_events/ongetcustomfields.zh.md)** 事件，则每当重命名对话框运行脚本时，该方法都将接收到一个 **GetCustomFieldData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
fields</td><td>

*对象:***[CustomFieldData](customfielddata.zh.md)**</td><td>

返回一个 **[CustomFieldData](customfielddata.zh.md)** 对象，脚本可以使用该对象向 *重命名* 对话框添加自定义字段。在此方法中添加到对象的每个属性都将在对话框中创建一个新字段，使用户可以向重命名脚本提供其它信息。
</td></tr><tr><td>
field_labels</td><td>

*对象:***[Map](map.zh.md)**</td><td>

这会让你可以向脚本的自定义字段分配标签，这些标签会显示在 *重命名* 对话框中的用户界面中。若要执行此操作，请将此属性设置为通过 **[DOpusFactory](dopusfactory.zh.md).Map** 方法创建的 **[Map](map.zh.md)**，并填入名称/标签的字符串对。
</td></tr><tr><td>
field_tips</td><td>

*对象:***[Map](map.zh.md)**</td><td>

这让你可以向脚本创建的任何编辑字段分配“提示横幅”。提示横幅显示在空编辑字段内，以便提示用户该字段期望什么样的数据。若要进行设置，请将此属性设置为通过 **[DOpusFactory](dopusfactory.zh.md).Map** 方法创建的 **[Map](map.zh.md)**，并填入名称/横幅的字符串对。
</td></tr><tr><td>
focus</td><td>

*字符串*</td><td>

你可以使用此字段指定在你的字段首次出现时默认获得输入焦点的控件。将其设置为您希望的控件的名称。你还可以指定 **!oldname** 或 **!newname** 为标准的旧和新名称字段分配焦点。
</td></tr></tbody>
</table>