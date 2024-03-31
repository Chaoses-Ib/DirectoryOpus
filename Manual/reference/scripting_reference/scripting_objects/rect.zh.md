**Rect** 对象表示一个矩形（或者在某些情况下表示与矩形的四条边有关的内容）。

以下说明给出各个属性的典型含义。在方法返回具有不同含义的 **Rect** 的情况下，将在该方法的文档中注明。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
empty</td><td>

*bool*</td><td>
当矩形为空时（即高度或宽度为 0），返回 true。
</td></tr><tr><td>
left</td><td>

*int*</td><td>
返回矩形的左边界。
</td></tr><tr><td>
top</td><td>

*int*</td><td>
返回矩形的上边界。
</td></tr><tr><td>
right</td><td>

*int*</td><td>
返回矩形的右边界。  
请注意，该值实际上在右边界外 1 个单位。矩形包含从左边界（包括左边界）到右边界（不包括右边界）的一切。  
宽度为 0 的位于位置 0,7 的矩形将具有 left=0 和 right=0。相同的情况，但宽度为 1 时，将具有 left=0 和 right=1，依此类推。
</td></tr><tr><td>
bottom</td><td>

*int*</td><td>
返回矩形的下边界。  
请注意，该值实际上在下边界外 1 个单位。矩形包含从上边界（包括上边界）到下边界（不包括下边界）的一切。  
高度为 0 的位于位置 0,7 的矩形将具有 top=7 和 bottom=7。相同的情况，但高度为 10 时，将具有 top=7 和 bottom=17，依此类推。
</td></tr><tr><td>
width</td><td>

*int*</td><td>
返回矩形的宽度。等于 **right-left**。
</td></tr><tr><td>
height</td><td>

*int*</td><td>
返回矩形的高度。等于 **bottom-top**。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
ToString</td><td>

*无*</td><td>

\<string\></td><td>
返回描述矩形的位置和大小的字符串，以方便调试脚本。格式为 "(L,T - R,B; WxH)"，即 左边界、上边界、右边界、下边界、宽度和高度。
</td></tr></tbody>
</table>