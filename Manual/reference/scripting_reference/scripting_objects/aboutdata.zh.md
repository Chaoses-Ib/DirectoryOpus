# 关于 AboutData**

如果 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 提供 **[OnAboutScript](../scripting_events/onaboutscript.zh.md)** 方法，当用户通过点击配置中的“关于”按钮调用该方法时，将传递一个 **AboutData** 对象。

<table><thead><tr><th>属性名称</th><th>返回类型</th><th>说明</th></tr></thead><tbody><tr><td>window</td><td>*int*</td><td>这是脚本显示对话框时应使用的父窗口的句柄，通过 **[Dialog](dialog.zh.md)** 对象显示。尽管这不是 **[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**，但仍可将其分配给 **Dialog.window** 属性以设置对话框的父窗口。</td></tr></table>