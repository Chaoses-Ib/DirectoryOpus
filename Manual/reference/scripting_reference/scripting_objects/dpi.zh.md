# DPI

**DPI** 对象是一个帮助对象，它提供一系列有关系统 DPI 设置的方法和属性。例如，你可以使用它将像素宽度转换为针对当前系统 DPI 进行缩放的宽度。**DPI** 对象通过 **[DOpus](dopus.cn.zh.md).DPI** 属性返回。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
dpi</td><td>

*int*</td><td>
将系统 DPI 设置作为“dpi 值”返回（例如 96、192）。
</td></tr><tr><td>
factor</td><td>

*int*</td><td>
将 DPI 设置作为“缩放因子”返回（例如 100、125、200）。
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

将所提供的尺寸按照系统 DPI 进行划分；例如，如果系统 DPI 设置为 150%，那么 **DPI.Divide(60)** 将返回 **40。**
</td></tr><tr><td>
Scale</td><td>

\<int:value\></td><td>

*int*</td><td>

按照系统 DPI 缩放所提供的尺寸；例如，如果系统 DPI 设置为 200%，那么 **DPI.Scale(75)** 将返回 **150。**
</td></tr></tbody>
</table>