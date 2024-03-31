# GetHelpContentData

如果脚本实现 **[OnGetHelpContent](../scripting_events/ongethelpcontent.zh.md)** 事件，它将在调用该方法时接收一个 **GetHelpContentData** 对象。你可以使用这个对象的函数将你的帮助内容添加到 Directory Opus 的 F1 帮助系统中。

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

添加一个 PNG 或 JPG 图片，可以供你的帮助页面使用。你可以为你的图片使用任何你喜欢的名称，但它们必须带有 **.png** 或者 **.jpg** 的后缀。你的帮助内容可以使用名称来引用图片，例如，如果你添加了一张图片并将其命名为 **myimage.jpg**，那么你的 html 内容可以使用下列方式显示它：  
`<img src="myimage.jpg">
`
如果你的脚本打包为 [脚本包](/Manual/scripting/script_add-ins/script_package.zh.md)，则可以在名为 **help** 的包目录的子目录中包括图片文件，然后使用 **[Script](script.zh.md).LoadHelpImage** 方法轻松加载它们。
</td></tr><tr><td>
AddHelpPage</td><td>

\<string:name\>  
\<string:title\>  
\<string:body\></td><td>

*无*</td><td>

为你的脚本向 F1 帮助文件添加一页帮助内容。你可以根据需要多次调用该方法。如果你添加了多页帮助内容，第一页将成为主题标题，所有后续页面都将出现在索引中该标题的下方。  
**name** 参数是可选的；如果未提供，将自动向你添加的每页分配一个默认名称。你可以使用 **[Script](script.zh.md).ShowHelp** 方法按名称触发显示一页特定的帮助内容。  
**title** 参数指定页面的标题；该标题显示在帮助索引中，并且应该具有足够的描述性，以使用户能够识别它指的是你的脚本。body 参数指定帮助页面的实际 HTML 内容。它应该是 HTML 页面中通常 *在** **\<body\>...\<//body\>** 标签之间的所有内容。  
如果你的脚本打包为 [脚本包](/Manual/scripting/script_add-ins/script_package.zh.md)，则可以在名为 **help** 的包目录的子目录中包括 HTML 文件，然后使用 **[Script](script.zh.md).LoadHelpFile** 方法轻松加载它们。
</td></tr></tbody>
</table>