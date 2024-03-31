# 图像

**Image** 对象表示在 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中显示的图像文件或图标。您可以使用 **[DOpus](dopus.zh.md).LoadImage** 或 **[Script](script.zh.md).LoadImage** 方法加载图像或图标。可以使用静态控件显示它，或将其分配为对话框的图标。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
bitcount</td><td>

*int*</td><td>
返回加载图像的比特计数。
</td></tr><tr><td>
height</td><td>

*int*</td><td>
返回加载图像的高度。
</td></tr><tr><td>
width</td><td>

*int*</td><td>
返回加载图像的宽度。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
SetClip</td><td>

*none*</td><td>

*bool*</td><td>
将图像的位图数据复制到 Windows 剪贴板。返回布尔成功值。
</td></tr></tbody>
</table>