# Rect

The **Rect** object represents a rectangle (or, in some cases, something relating to a rectangle's four sides).

The descriptions below give the properties' typical meanings. Where a method returns a **Rect** with different meanings, it will be noted in the documentation for that method.

| Property Name | Return Type | Description |
| --- | --- | --- |
| empty | *bool* | Returns true if the rectangle is empty (i.e. has no height or no width). |
| left | *int* | Returns the left edge of the rectangle. |
| top | *int* | Returns the top edge of the rectangle. |
| right | *int* | Returns the right edge of the rectangle.  <br />Note that this value is actually 1 outside the right edge. A rectangle includes everything from and including the left edge up to but excluding the right edge.  <br />A rectangle at position 0,7 with 0 width will have left=0 and right=0. The same but with a width of 1 will have left=0 and right=1, and so on. |
| bottom | *int* | Returns the bottom edge of the rectangle.  <br />Note that this value is actually 1 outside the right edge. A rectangle includes everything from and including the top edge up to but excluding the bottom edge.  <br />A rectangle at position 0,7 with 0 height will have top=7 and bottom=7. The same but with a height of 10 will have top=7 and bottom=17, and so on. |
| width | *int* | Returns the width of the rectangle. Equal to **right-left**. |
| height | *int* | Returns the height of the rectangle. Equal to **bottom-top**. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| ToString | *none* | \<string\> | Returns a string describing the rectangle's position and size, as a convenience when debugging scripts. The format is "(L,T - R,B; WxH)" i.e. Left, Top, Right, Bottom, Width, and Height. |

