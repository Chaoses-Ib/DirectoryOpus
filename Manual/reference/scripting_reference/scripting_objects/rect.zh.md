# Rect

**Rect** 对象表示一个矩形（或在某些情况下，与矩形的四条边相关的东西）。

下面的描述给出了属性的典型含义。如果方法返回的 **Rect** 具有不同的含义，则会在该方法的文档中注明。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
empty</td><td>

*bool*</td><td>
如果矩形为空（即没有高度或没有宽度），则返回 true。
</td></tr><tr><td>
left</td><td>

*int*</td><td>
返回矩形的左边缘。
</td></tr><tr><td>
top</td><td>

*int*</td><td>
返回矩形的顶边缘。
</td></tr><tr><td>
right</td><td>

*int*</td><td>

返回矩形的右边缘。  
注意，此值实际上在右边缘之外为 1。矩形包含从左边缘开始到右边缘结束（不包括右边缘）的所有内容。  
位置为 0,7 且宽度为 0 的矩形将具有 left=0 和 right=0。相同位置，但宽度为 1 的矩形将具有 left=0 和 right=1，依此类推。
</td></tr><tr><td>
bottom</td><td>

*int*</td><td>

返回矩形的底边缘。  
注意，此值实际上在右边缘之外为 1。矩形包含从顶边缘开始到底边缘结束（不包括底边缘）的所有内容。  
位置为 0,7 且高度为 0 的矩形将具有 top=7 和 bottom=7。相同位置，但高度为 10 的矩形将具有 top=7 和 bottom=17，依此类推。
</td></tr><tr><td>
width</td><td>

*int*</td><td>

返回矩形的宽度。等于 **right-left**。
</td></tr><tr><td>
height</td><td>

*int*</td><td>

返回矩形的宽度。等于 **bottom-top**。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
ToString</td><td>

*none*</td><td>

\<string\></td><td>

返回一个字符串，描述矩形的位置和大小，便于调试脚本。格式为 "(L,T - R,B; WxH)"，即左、上、右、下、宽和高。
</td></tr></tbody>
</table>