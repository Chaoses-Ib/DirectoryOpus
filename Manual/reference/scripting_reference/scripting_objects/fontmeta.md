# FontMeta

The **FontMeta** object is retrieved from the **[Metadata](metadata.md).font** property. It provides access to metadata relating to font files. The fields in this object correspond to those in the Windows SDK **LOGFONT** structure; further information about their meaning can be found on the [MSDN website](http://msdn.microsoft.com/en-us/library/windows/desktop/dd145037(v=vs.85).aspx).

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
charset</td><td>

*int*</td><td>
The character set.
</td></tr><tr><td>
clipprecision</td><td>

*int*</td><td>
The clipping precision.
</td></tr><tr><td>
escapement</td><td>

*int*</td><td>
The angle, in tenths of degrees, between the escapement vector and the x-axis of the device.
</td></tr><tr><td>
fontname</td><td>

*string*</td><td>
The typeface name of the font.
</td></tr><tr><td>
height</td><td>

*int*</td><td>
The height, in logical units, of the font's character cell or character.
</td></tr><tr><td>
italic</td><td>

*bool*</td><td>

An italic font if set to **True**.
</td></tr><tr><td>
orientation</td><td>

*int*</td><td>
The angle, in tenths of degrees, between each character's base line and the x-axis of the device.
</td></tr><tr><td>
outprecision</td><td>

*int*</td><td>
The output precision.
</td></tr><tr><td>
pitchandfamily</td><td>

*int*</td><td>
The pitch and family of the font.
</td></tr><tr><td>
quality</td><td>

*int*</td><td>
The output quality.
</td></tr><tr><td>
strikeout</td><td>

*bool*</td><td>

A strikeout font if set to **True**.
</td></tr><tr><td>
underline</td><td>

*bool*</td><td>

An underlined font if set to **True**.
</td></tr><tr><td>
weight</td><td>

*int*</td><td>
The weight of the font in the range 0 through 1000.
</td></tr><tr><td>
width</td><td>

*int*</td><td>
The average width, in logical units, of characters in the font.
</td></tr></tbody>
</table>

