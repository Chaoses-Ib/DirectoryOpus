# OnGetHelpContent

**OnGetHelpContent** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以向 Directory Opus 本地 F1 帮助添加其自身的帮助内容。您可以添加单个帮助页面，或多个页面（在这种情况下，第一个页面将成为“主题标题”，所有后续页面将出现在索引中的下方）。您还可以添加图像，这些图像可以在帮助内容中显示。请注意，只有在用户启用了本地 http 帮助（默认情况下）的情况下，脚本添加的帮助才有效 - 如果用户选择使用旧的 *HtmlHelp* 界面，则您的内容将不会出现。 

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnGetHelpContent
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[GetHelpContentData](../scripting_objects/gethelpcontentdata.zh.md)**
</td></tr><tr><td>

**返回类型:**</td><td>
无。
</td></tr><tr><td>

**描述:**</td><td>

使用 **AddHelpPage** 和 **AddHelpImage** 方法添加您的帮助内容。
</td></tr></tbody>
</table>