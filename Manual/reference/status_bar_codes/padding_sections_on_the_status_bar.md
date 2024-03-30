# Padding sections on the status bar

The following codes let you pad the width of sections to align with various Lister elements. For example, you can pad a section to align with the edge of the folder tree, so that no matter how wide the tree is the section will always be the same width. This is particularly useful in dual-display Listers, where you can define the status bar to show information for both file displays at once - in this instance, you would want to pad the section for the right file display to always align with it.

<table>
<thead><tr><th>
Code</th><th>
Description
</th></tr></thead><tbody><tr><td>

{pad*X*}</td><td>

**Pad to percentage of total space**  
Pads the width of a status bar section to a percentage of the total width of the status bar.

**X** is a value from 1 to 100. For example, **{pad50}** pads the section to 50% of the width of the Lister.
</td></tr><tr><td>

{rpad*X*}</td><td>

**Pad to percentage of remaining space**  
Pads the width of a status bar section to a percentage of the remaining width on the status bar (that is, the space from the beginning of this section to the right-hand edge of the Lister).

**X** is a value from 1 to 100. For example, {pad25} pads the section to 25% of the remaining space.
</td></tr><tr><td>
{wtree}</td><td>

**Pad to width of folder tree**  
The section will be padded to the same width as the folder tree. In a dual-display Lister, with dual trees, this will be the width of the left folder tree. This code has no effect if the folder tree is not visible.
</td></tr><tr><td>
{wtree2}</td><td>

**Pad to width of second folder tree\\** The section will be padded to the same width as the second folder tree in a dual-display Lister. This code has no effect if the second folder tree is not visible.
</td></tr><tr><td>
{rtree}</td><td>

**Pad to right edge of folder tree**  
The section will be right-aligned with the right edge of the folder tree. In a dual-display Lister, this will be the left folder tree.
</td></tr><tr><td>
{rtree-}</td><td>

**Pad to right edge of folder tree, right-justify contents**  
The section will be right-aligned with the right edge of the folder tree. As well, the contents of this section will be right-justified.
</td></tr><tr><td>
{rtree2}</td><td>

**Pad to right edge of second folder tree**  
The section will be right-aligned with the right edge of the second folder tree.
</td></tr><tr><td>
{rtree2-}</td><td>

**Pad to right edge of second folder tree, right-justify contents**  
The section will be right-aligned with the right edge of the second folder tree. As well, the contents of this section will be right-justified.
</td></tr><tr><td>
{wleft}</td><td>

**Pad to width of left file display**  
The section will be padded to the same width as the left file display (or the only file display in a single-display Lister).
</td></tr><tr><td>
{rleft}</td><td>

**Pad to right edge of left file display**  
The section will be right-aligned with the right edge of the left file display (or the only file display in a single-display Lister).
</td></tr><tr><td>
{rleft-}</td><td>

**Pad to right edge of left file display, right-justify contents**  
The section will be right-aligned with the right edge of the left file display. As well, the contents of this section will be right-justified.
</td></tr><tr><td>

{width*X*}</td><td>

**Absolute width, scale with DPI**  
Sets the section to an absolute width in pixels (adjusted for your system DPI).

**X** is the desired width. For example, **{width240}** pads the section to 240 pixels wide at standard DPI and 480 pixels wide at 200% DPI.
</td></tr><tr><td>

{width-*X*}</td><td>

**Absolute width**  
Sets the section to an absolute width in pixels.

**X** is the desired width. For example, **{width-240}** pads the section to 240 pixels wide regardless of system DPI.
</td></tr></tbody>
</table>

