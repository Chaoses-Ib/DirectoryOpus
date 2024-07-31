# Image

**Image** 对象代表一个将在 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中显示的图片文件或图标。你可以使用 **[DOpus](dopus.zh.md).LoadImage** 或 **[Script](script.zh.md).LoadImage** 方法加载图片或图标。它可以通过静态控件显示，或作为对话框的图标使用。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
bitcount</td><td>

*int*</td><td>
返回加载图片的位数。
</td></tr><tr><td>
height</td><td>

*int*</td><td>
返回加载图片的高度。
</td></tr><tr><td>
type</td><td>

*string*</td><td>
返回图片加载或创建自的文件类型（如果已知）。
</td></tr><tr><td>
width</td><td>

*int*</td><td>
返回加载图片的宽度。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
SetClip</td><td>

*无*</td><td>

*bool*</td><td>
将图片的位图数据复制到 Windows 剪贴板。返回布尔值成功。
</td></tr></tbody>
</table>