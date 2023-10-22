# FontMeta

The **FontMeta** object is retrieved from the **[Metadata](metadata.md).font** property. It provides access to metadata relating to font files. The fields in this object correspond to those in the Windows SDK **LOGFONT** structure; further information about their meaning can be found on the [MSDN website](http://msdn.microsoft.com/en-us/library/windows/desktop/dd145037(v=vs.85).aspx).

| Property Name | Return Type | Description |
| --- | --- | --- |
| charset | *int* | The character set. |
| clipprecision | *int* | The clipping precision. |
| escapement | *int* | The angle, in tenths of degrees, between the escapement vector and the x-axis of the device. |
| fontname | *string* | The typeface name of the font. |
| height | *int* | The height, in logical units, of the font's character cell or character. |
| italic | *bool* | An italic font if set to **True**. |
| orientation | *int* | The angle, in tenths of degrees, between each character's base line and the x-axis of the device. |
| outprecision | *int* | The output precision. |
| pitchandfamily | *int* | The pitch and family of the font. |
| quality | *int* | The output quality. |
| strikeout | *bool* | A strikeout font if set to **True**. |
| underline | *bool* | An underlined font if set to **True**. |
| weight | *int* | The weight of the font in the range 0 through 1000. |
| width | *int* | The average width, in logical units, of characters in the font. |

