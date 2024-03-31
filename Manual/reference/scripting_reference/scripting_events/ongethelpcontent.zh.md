**OnGetHelpContent** 事件可以由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以将自己的帮助内容添加到 Directory Opus 本地 F1 帮助中。你可以添加一个帮助页面，或添加多个页面（在这种情况下，第一个页面将成为“主题标题”，所有后续页面都显示在索引的下方）。你还可以添加可显示在帮助内容中的图片。请注意，只有当用户启用了本地 HTTP 帮助时，才能添加脚本帮助（这是默认设置）- 如果用户选择使用旧的 *HtmlHelp* 界面，则你的内容不会显示。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnGetHelpContent
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[GetHelpContentData](../scripting_objects/gethelpcontentdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>
无。
</td></tr><tr><td>

**描述：**</td><td>

使用 **AddHelpPage** 和 **AddHelpImage** 方法添加帮助内容。
</td></tr></tbody>
</table>