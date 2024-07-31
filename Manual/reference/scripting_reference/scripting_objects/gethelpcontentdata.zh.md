# GetHelpContentData

如果脚本实现了 **[OnGetHelpContent](../scripting_events/ongethelpcontent.zh.md)** 事件，当该方法被调用时，它会收到一个 **GetHelpContentData** 对象。您可以使用此对象的方法将您的帮助内容添加到 Directory Opus F1 帮助系统中。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddHelpImage</td><td>

\<string:name\>  
\<**[Blob](blob.zh.md)**:image\></td><td>

*无*</td><td>

添加 PNG 或 JPG 图像并使其可用于您的帮助页面。您可以为您的图像使用任何您喜欢的名称，尽管它们必须具有 **.png** 或 **.jpg** 后缀。您的帮助内容然后可以按名称引用图像，例如，如果您添加一个图像并将其命名为 **myimage.jpg**，您的 html 内容可以使用以下方式显示它：  
`<img src="myimage.jpg">
` 如果您的脚本被捆绑为一个 [脚本包](/Manual/scripting/script_add-ins/script_package.zh.md)，您可以在包的子目录中包含图像文件，该目录名为 **help**，然后可以使用 **[Script](script.zh.md).LoadHelpImage** 方法轻松加载它们。
</td></tr><tr><td>
AddHelpPage</td><td>

\<string:name\>  
\<string:title\>  
\<string:body\></td><td>

*无*</td><td>

为您的脚本添加一个帮助内容页面到 F1 帮助文件。您可以根据需要多次调用此方法。如果您添加了多个帮助页面，第一个页面将成为主题标题，所有后续页面将在索引中显示在其下方。  
**name** 参数是可选的；如果未提供，将为添加的每个页面自动分配一个默认名称。您可以使用 **[Script](script.zh.md).ShowHelp** 方法按名称触发特定帮助页面的显示。  
**title** 参数指定页面标题；这将显示在帮助索引中，应该具有足够的描述性，以便用户可以识别它与您的脚本相关。body 参数指定帮助页面的实际 HTML 内容。这应该是您通常在 HTML 页面中的 **\<body\>...\</body\>** 标签之间找到的所有内容。  
如果您的脚本被捆绑为一个 [脚本包](/Manual/scripting/script_add-ins/script_package.zh.md)，您可以在包的子目录中包含 HTML 文件，该目录名为 **help**，然后可以使用 **[Script](script.zh.md).LoadHelpFile** 方法轻松加载它们。
</td></tr></tbody>
</table>