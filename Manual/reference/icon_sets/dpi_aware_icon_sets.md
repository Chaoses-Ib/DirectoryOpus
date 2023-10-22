# DPI aware Icon Sets

Directory Opus handles different system DPI settings transparently, and will scale icons as needed. However, you may want to provide multiple base icon images in your icon sets to handle different DPI settings. Scaling often results in blurry and unsatisfactory images - providing the same icons in multiple resolutions can result in a better aesthetic result when the user is running on a high-DPI system.

For each **\<set\>** entry in the XML file you can provide an optional **\<dpi\>** key which specifies alternate images for different DPI settings, and can also optionally set limits on when the image can be used. For example, if an image doesn’t look good scaled up you can set a maximum scale factor it can be used for.

The **\<dpi\>** key has the following attributes:

\|`<set blah...>`

|     |
|-----|
|     |

\|`<dpi base="x">`

|                                                           |
|-----------------------------------------------------------|
| specifies the base scale factor of the image (e.g. "100") |

\|`<scale factor="x"`

|                                                                 |
|-----------------------------------------------------------------|
| specifies the scale factor of this alternate image (e.g. "200") |

\|`min="x"`

<table>
<tbody>
<tr class="odd">
<td>minimum scale factor this should be used for (optional, e.g. "200")<br />
</td>
</tr>
</tbody>
</table>

\|`max="x"`

|                                                                     |
|---------------------------------------------------------------------|
| maximum scale factor this should be used for (optional, e.g. "400") |

\|`no_scale_min="x"`

<table>
<tbody>
<tr class="odd">
<td>minimum scale factor this image should be used without any scaling (optional)<br />
</td>
</tr>
</tbody>
</table>

\|`no_scale_max="x"`

<table>
<tbody>
<tr class="odd">
<td>maximum of above (optional). Use -1 for infinite.<br />
</td>
</tr>
</tbody>
</table>

\|`filename="x"`

|                                 |
|---------------------------------|
| filename of the alternate image |

\|`width="x"`

<table>
<tbody>
<tr class="odd">
<td>width of icons in the alternate image (optional, will be calculated if not provided)<br />
</td>
</tr>
</tbody>
</table>

\|`height="x" `

<table>
<tbody>
<tr class="odd">
<td>height of icons in the alternate image (optional, will be calculated if not provided)<br />
</td>
</tr>
</tbody>
</table>

\|`/>`

|     |
|-----|
|     |

\|`</dpi>`

|     |
|-----|
|     |

As many **\<scale\>** entries can be provided as needed. If the **\<dpi\>** key is missing altogether a base scaling factor of 100% is assumed. If needed, you can include the base image in the DPI list as well (for example, if you want to specify **no_scale_min** and **no_scale_max** values for it).

The **no_scale_xxx** range can be used to snap to various sizes while avoiding blurring. This is usually only needed at small sizes (since once icons get larger, the scaling works better). Ranges are inclusive of their **min** and **max** values, should not overlap with each other, and the value specified for **factor** should fall within the range.

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
