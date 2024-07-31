# DPI

**DPI** 对象是一个辅助对象，提供了一些与系统 DPI 设置相关的属性和方法。例如，您可以使用它将像素宽度转换为针对当前系统 DPI 缩放的宽度。**DPI** 对象通过 **[DOpus](dopus.zh.md).DPI** 属性返回。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
dpi</td><td>

*int*</td><td>
返回系统 DPI 设置，作为“dpi 值”（例如 96、192）。
</td></tr><tr><td>
factor</td><td>

*int*</td><td>
返回 DPI 设置，作为“缩放因子”（例如 100、125、200）。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Divide</td><td>

\<int:value\></td><td>

*int*</td><td>

将提供的尺寸除以系统 DPI；例如，如果系统 DPI 设置为 150%，**DPI.Divide(60)** 将返回 **40.**。
</td></tr><tr><td>
Scale</td><td>

\<int:value\></td><td>

*int*</td><td>

将提供的尺寸乘以系统 DPI；例如，如果系统 DPI 设置为 200%，**DPI.Scale(75)** 将返回 **150**。
</td></tr></tbody>
</table>