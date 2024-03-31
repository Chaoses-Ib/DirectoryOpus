**FontMeta** 对象从 **[元数据](metadata.zh.md).font** 属性中获取。它提供对与字体文件相关的元数据的访问。此对象中的字段对应于 Windows SDK **LOGFONT** 结构中的字段；可以在 [MSDN 网站](http://msdn.microsoft.com/en-us/library/windows/desktop/dd145037(v=vs.85).aspx) 上找到有关其含义的进一步信息。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
charset</td><td>

*int*</td><td>
字符集。
</td></tr><tr><td>
clipprecision</td><td>

*int*</td><td>
剪切精度。
</td></tr><tr><td>
escapement</td><td>

*int*</td><td>
逸出向量与设备 x 轴之间的角度（十分之一度）。
</td></tr><tr><td>
fontname</td><td>

*string*</td><td>
字体的字体名称。
</td></tr><tr><td>
height</td><td>

*int*</td><td>
字体的字符单元或字符高度（逻辑单位）。
</td></tr><tr><td>
italic</td><td>

*bool*</td><td>

设置为 **True**，表示斜体字体。
</td></tr><tr><td>
orientation</td><td>

*int*</td><td>
每个字符的基线与设备 x 轴之间的角度（十分之一度）。
</td></tr><tr><td>
outprecision</td><td>

*int*</td><td>
输出精度。
</td></tr><tr><td>
pitchandfamily</td><td>

*int*</td><td>
字体的间距和字体族。
</td></tr><tr><td>
quality</td><td>

*int*</td><td>
输出质量。
</td></tr><tr><td>
strikeout</td><td>

*bool*</td><td>

设置为 **True**，表示删除线字体。
</td></tr><tr><td>
underline</td><td>

*bool*</td><td>

设置为 **True**，表示下划线字体。
</td></tr><tr><td>
weight</td><td>

*int*</td><td>
字体粗细（范围 0 至 1000）。
</td></tr><tr><td>
width</td><td>

*int*</td><td>
字体中字符的平均宽度（逻辑单位）。
</td></tr></tbody>
</table>