# Rect

The **Rect** object represents a rectangle (or, in some cases, something relating to a rectangle's four sides).

The descriptions below give the properties' typical meanings. Where a method returns a **Rect** with different meanings, it will be noted in the documentation for that method.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
empty</td><td>

*bool*</td><td>
Returns true if the rectangle is empty (i.e. has no height or no width).
</td></tr><tr><td>
left</td><td>

*int*</td><td>
Returns the left edge of the rectangle.
</td></tr><tr><td>
top</td><td>

*int*</td><td>
Returns the top edge of the rectangle.
</td></tr><tr><td>
right</td><td>

*int*</td><td>

Returns the right edge of the rectangle.  
Note that this value is actually 1 outside the right edge. A rectangle includes everything from and including the left edge up to but excluding the right edge.  
A rectangle at position 0,7 with 0 width will have left=0 and right=0. The same but with a width of 1 will have left=0 and right=1, and so on.
</td></tr><tr><td>
bottom</td><td>

*int*</td><td>

Returns the bottom edge of the rectangle.  
Note that this value is actually 1 outside the right edge. A rectangle includes everything from and including the top edge up to but excluding the bottom edge.  
A rectangle at position 0,7 with 0 height will have top=7 and bottom=7. The same but with a height of 10 will have top=7 and bottom=17, and so on.
</td></tr><tr><td>
width</td><td>

*int*</td><td>

Returns the width of the rectangle. Equal to **right-left**.
</td></tr><tr><td>
height</td><td>

*int*</td><td>

Returns the height of the rectangle. Equal to **bottom-top**.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
ToString</td><td>

*none*</td><td>

\<string\></td><td>

Returns a string describing the rectangle's position and size, as a convenience when debugging scripts. The format is "(L,T - R,B; WxH)" i.e. Left, Top, Right, Bottom, Width, and Height.
</td></tr></tbody>
</table>

