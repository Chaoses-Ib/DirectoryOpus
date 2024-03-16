# DPI aware Icon Sets

Directory Opus handles different system DPI settings transparently, and will scale icons as needed. However, you may want to provide multiple base icon images in your icon sets to handle different DPI settings. Scaling often results in blurry and unsatisfactory images - providing the same icons in multiple resolutions can result in a better aesthetic result when the user is running on a high-DPI system.

For each \<ib:inline-code\>`<set>`\</ib:inline-code\> entry in the XML file you can provide an optional \<ib:inline-code\>`<dpi>`\</ib:inline-code\> key which specifies alternate images for different DPI settings, and can also optionally set limits on when the image can be used. For example, if an image doesn’t look good scaled up you can set a maximum scale factor it can be used for.

The \<ib:inline-code\>`<dpi>`\</ib:inline-code\> key has the following attributes:

<table>
<tbody>
<tr class="odd">
<td>&lt;ib:inline-code&gt;<code>&lt;set blah...&gt;</code>&lt;/ib:inline-code&gt;</td>
<td></td>
</tr>
<tr class="even">
<td>&lt;tab&gt;&lt;ib:inline-code&gt;<code>&lt;dpi base="x"&gt;</code>&lt;/ib:inline-code&gt;</td>
<td>specifies the base scale factor of the image (e.g. "100")</td>
</tr>
<tr class="odd">
<td>&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>&lt;scale factor="x"</code>&lt;/ib:inline-code&gt;</td>
<td>specifies the scale factor of this alternate image (e.g. "200")</td>
</tr>
<tr class="even">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>min="x"</code>&lt;/ib:inline-code&gt;</td>
<td>minimum scale factor this should be used for (optional, e.g. "200")<br />
</td>
</tr>
<tr class="odd">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>max="x"</code>&lt;/ib:inline-code&gt;</td>
<td>maximum scale factor this should be used for (optional, e.g. "400")</td>
</tr>
<tr class="even">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>no_scale_min="x"</code>&lt;/ib:inline-code&gt;</td>
<td>minimum scale factor this image should be used without any scaling (optional)<br />
</td>
</tr>
<tr class="odd">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>no_scale_max="x"</code>&lt;/ib:inline-code&gt;</td>
<td>maximum of above (optional). Use -1 for infinite.<br />
</td>
</tr>
<tr class="even">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>filename="x"</code>&lt;/ib:inline-code&gt;</td>
<td>filename of the alternate image</td>
</tr>
<tr class="odd">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>width="x"</code>&lt;/ib:inline-code&gt;</td>
<td>width of icons in the alternate image (optional, will be calculated if not provided)<br />
</td>
</tr>
<tr class="even">
<td>&lt;tab&gt;&lt;tab&gt;&lt;tab&gt;&lt;ib:inline-code&gt;<code>height="x" /&gt;</code>&lt;/ib:inline-code&gt;</td>
<td>height of icons in the alternate image (optional, will be calculated if not provided)<br />
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

As many \<ib:inline-code\>`<scale>`\</ib:inline-code\> entries can be provided as needed. If the \<ib:inline-code\>`<dpi>`\</ib:inline-code\> key is missing altogether a base scaling factor of 100% is assumed. If needed, you can include the base image in the DPI list as well (for example, if you want to specify \<ib:inline-code\>`no_scale_min`\</ib:inline-code\> and \<ib:inline-code\>`no_scale_max`\</ib:inline-code\> values for it).

The \<ib:inline-code\>`no_scale_xxx`\</ib:inline-code\> range can be used to snap to various sizes while avoiding blurring. This is usually only needed at small sizes (since once icons get larger, the scaling works better). Ranges are inclusive of their \<ib:inline-code\>`min`\</ib:inline-code\> and \<ib:inline-code\>`max`\</ib:inline-code\> values, should not overlap with each other, and the value specified for \<ib:inline-code\>`factor`\</ib:inline-code\> should fall within the range.

A real example from the default icon set:

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
