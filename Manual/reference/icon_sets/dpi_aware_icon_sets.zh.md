**DPI** 感知图标集

Directory Opus 透明地处理不同的系统 **DPI** 设置，并且根据需要缩放图标。但是，你可能希望在你的图标集中提供多个基本图标图像来处理不同的 **DPI** 设置。缩放通常会导致模糊且不令人满意的图像 - 在用户在高 **DPI** 系统上运行时，以多种分辨率提供相同的图标可以产生更好的美学效果。

对于 XML 文件中的每个 `<set>` 条目，你可以提供一个可选的 `<dpi>` 键，它为不同的 **DPI** 设置指定备用图像，并且还可以在图像可以使用时设置限制。例如，如果某个图像缩放后看起来不佳，则可以设置其可用的最大比例系数。

`<dpi>` 键具有以下属性：

<table>
<tbody>
<tr class="odd">
<td>&lt;ib:inline-code&gt;<code>&lt;set blah...&gt;</code>&lt;/ib:inline-code&gt;</td>
<td></td>
</tr>
<tr class="even">
<td>&lt;tab&gt;&lt;ib:inline-code&gt;<code>&lt;dpi base="x"&gt;</code>&lt;/ib:inline-code&gt;</td>
<td>指定图像的基本缩放在数 (例：“100”)</td>
</tr>
<tr class="odd">
<td>&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>&lt;scale factor="x"</code>&lt;/ib:inline-code&gt;</td>
<td>指定此备用图像的缩放系数 (例：“200”)</td>
</tr>
<tr class="even">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>min="x"</code>&lt;/ib:inline-code&gt;</td>
<td>应使用此功能的最小缩放系数 (可选，例：“200”)<br />
</td>
</tr>
<tr class="odd">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>max="x"</code>&lt;/ib:inline-code&gt;</td>
<td>应使用此功能的最大缩放系数 (可选，例：“400”)</td>
</tr>
<tr class="even">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>no_scale_min="x"</code>&lt;/ib:inline-code&gt;</td>
<td>此图像不进行任何缩放应使用的最小缩放系数 (可选)<br />
</td>
</tr>
<tr class="odd">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>no_scale_max="x"</code>&lt;/ib:inline-code&gt;</td>
<td>上述缩放的最大值 (可选)。将 -1 用于无限值。<br />
</td>
</tr>
<tr class="even">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>filename="x"</code>&lt;/ib:inline-code&gt;</td>
<td>备用图像的文件名</td>
</tr>
<tr class="odd">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>width="x"</code>&lt;/ib:inline-code&gt;</td>
<td>备用图像中图标的宽度 (可选，如果未提供，则会计算此值)<br />
</td>
</tr>
<tr class="even">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>height="x" /&gt;</code>&lt;/ib:inline-code&gt;</td>
<td>备用图像中图标的高度 (可选，如果未提供，则会计算此值)<br />
</td>
</tr>
<tr class="odd">
<td>&lt;tab&gt;&lt;ib:inline-code&gt;<code>&lt;/dpi&gt;</code>&lt;/ib:inline-code&gt;</td>
<td></td>
</tr>
<tr class="even">
<td>&lt;ib:inline-code&gt;<code>&lt;/set&gt;</code>&lt;/ib:inline-code&gt;</td>
<td></td>
</tr>
</tbody>
</table>

可以根据需要提供尽可能多的 `<scale>` 条目。如果 **DPI** 键完全缺失，则假设基本缩放系数为 100%。如果需要，你也可以将基本图像包含在 **DPI** 列表中 (例如，如果你想为其指定 `no_scale_min` 和 `no_scale_max` 值)。

`no_scale_xxx` 范围可用于捕捉到各种大小，同时避免模糊。通常只需要在较小的尺寸上使用此功能 (因为一旦图标变大，缩放就会效果更好)。范围包含其 `min` 和 `max` 值，不得相互重叠，并且为 `factor` 指定的值应在范围之内。

默认图标集中的一个实际示例：

    <set filename="DEFAULT_ICONS_22.PNG" size="small" width="22" height="22">
        <dpi base="100">
            <scale factor="100" filename="DEFAULT_ICONS_22.PNG" width="22" height="22" no_scale_min="0" no_scale_max="125" />
            <scale factor="150" filename="DEFAULT_ICONS_32.PNG" width="32" height="32" no_scale_min="126" no_scale_max="175" />
            <scale factor="200" filename="DEFAULT_ICONS_48.PNG" width="48" height="48" />
            <scale factor="300" filename="DEFAULT_ICONS_64.PNG" width="64" height="64" />
        </dpi>
        <icon col="1" name="empty" row="1" />
        <icon col="2" name="spacer" row="1" />
        ...
    </set>
    <set filename="DEFAULT_ICONS_32.PNG" size="large" width="32" height="32">
        <dpi base="100">
            <scale factor="100" filename="DEFAULT_ICONS_32.PNG" width="32" height="32" no_scale_min="0" no_scale_max="125" />
            <scale factor="150" filename="DEFAULT_ICONS_48.PNG" width="48" height="48" no_scale_min="126" no_scale_max="175" />
            <scale factor="200" filename="DEFAULT_ICONS_64.PNG" width="64" height="64" />
        </dpi>
        <icon col="1" name="empty" row="1" />
        <icon col="2" name="spacer" row="1" />
        ...
    </set>