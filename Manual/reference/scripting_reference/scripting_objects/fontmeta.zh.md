# FontMeta

**FontMeta** 对象是从 **[Metadata](metadata.zh.md).font** 属性中获取的。它提供对与字体文件相关的元数据的访问。此对象中的字段对应于 Windows SDK **LOGFONT** 结构中的字段；有关其含义的更多信息，请参阅 [MSDN 网站](http://msdn.microsoft.com/en-us/library/windows/desktop/dd145037(v=vs.85).aspx)。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
charset</td><td>

*int*</td><td>
字符集。
</td></tr><tr><td>
clipprecision</td><td>

*int*</td><td>
裁剪精度。
</td></tr><tr><td>
escapement</td><td>

*int*</td><td>
转义向量与设备 x 轴之间的角度（以十分之一度为单位）。
</td></tr><tr><td>
fontname</td><td>

*string*</td><td>
字体的字型名称。
</td></tr><tr><td>
height</td><td>

*int*</td><td>
字体字符单元格或字符的高度（以逻辑单位为单位）。
</td></tr><tr><td>
italic</td><td>

*bool*</td><td>

如果设置为 **True**，则为斜体字体。
</td></tr><tr><td>
orientation</td><td>

*int*</td><td>
每个字符的基线与设备 x 轴之间的角度（以十分之一度为单位）。
</td></tr><tr><td>
outprecision</td><td>

*int*</td><td>
输出精度。
</td></tr><tr><td>
pitchandfamily</td><td>

*int*</td><td>
字体的间距和族。
</td></tr><tr><td>
quality</td><td>

*int*</td><td>
输出质量。
</td></tr><tr><td>
strikeout</td><td>

*bool*</td><td>

如果设置为 **True**，则为删除线字体。
</td></tr><tr><td>
underline</td><td>

*bool*</td><td>

如果设置为 **True**，则为下划线字体。
</td></tr><tr><td>
weight</td><td>

*int*</td><td>
字体的粗细，范围为 0 到 1000。
</td></tr><tr><td>
width</td><td>

*int*</td><td>
字体中字符的平均宽度（以逻辑单位为单位）。
</td></tr></tbody>
</table>