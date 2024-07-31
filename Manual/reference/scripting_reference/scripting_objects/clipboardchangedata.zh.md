# ClipboardChangeData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnClipboardChange](../scripting_events/onclipboardchange.zh.md)** 事件，该方法会在系统剪贴板内容发生更改时收到一个 **ClipboardChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>
返回一个计数器，每次剪贴板内容发生变化（当 Opus 运行时）时递增。
</td></tr><tr><td>
has_files</td><td>

*bool*</td><td>

如果剪贴板现在包含文件，则返回 **True**。
</td></tr></tbody>
</table>