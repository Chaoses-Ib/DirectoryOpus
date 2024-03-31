# 映射

**Map** 对象是一个 [关联容器](http://en.wikipedia.org/wiki/Associative_container)。它类似于数组或矢量 (例如 **[Vector](vector.zh.md)**)，因为可以存储一个或多个对象，但是它的优势在于使用字典系统定位对象，而不是使用数字索引。因此，您可以使用任意值（字符串、整数、日期等）作为键来插入或查找对象。（请注意，无论初始类型如何，键都会隐式转换为字符串。）

您可以访问映射中的元素，就好像映射是一个函数（例如 **Map("foo")** 按键 *"foo"* 引用元素）。您还可以使用方括号（如数组或 Vector），但仅在键的名称以下划线开头或完全是数字时才可以使用（例如 **Map\[123\]** 或 **Map\["\_foo"\]**）。此外，您还可以使用 **get** 和 **set** 方法。

您可以使用 **[DOpusFactory](dopusfactory.zh.md).Map** 方法创建一个新 **Map**。可以枚举映射中的键，并且它们会自动保持排序。

以下两个示例都输出以下内容：

    count: 4
    bird -> tweet
    cat -> meow
    dog -> woof
    snake -> hiss

### JScript 示例：

    var map = DOpus.Create.Map();

    map("cat") = "meow";
    map("dog") = "woof";
    map("bird") = "tweet";
    map("snake") = "hiss";

    DOpus.Output("count: " + map.count);

    for (var e = new Enumerator(map); !e.atEnd(); e.moveNext())
    {
     var key = e.item();
     var value = map(key);
     DOpus.Output(key + " -> " + value);
    }

### VBScript 示例：

    Dim map, key, value
    Set map = DOpus.Create.Map

    map("cat") = "meow"
    map("dog") = "woof"
    map("bird") = "tweet"
    map("snake") = "hiss"

    DOpus.Output "count: " & map.count

    For Each key In map
     value = map(key)
     DOpus.Output(key & " -> " & value)
    Next

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>

返回 **Map** 当前所包含的元素数。
</td></tr><tr><td>
empty</td><td>

*bool*</td><td>

如果 **Map** 为空，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
length</td><td>

*int*</td><td>

**count** 的同义词。
</td></tr><tr><td>
size</td><td>

*int*</td><td>

**count** 的同义词。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
assign</td><td>

\<**Map**:from\></td><td>

*none*</td><td>

将另一个 **Map** 的内容复制到此 **Map**。
</td></tr><tr><td>
clear</td><td>

*none*</td><td>

*none*</td><td>

清除 **Map** 的内容。
</td></tr><tr><td>
erase</td><td>

\<variant:key\></td><td>

*none*</td><td>
如果映射中存在与指定键匹配的元素，则擦除该元素。
</td></tr><tr><td>
exists</td><td>

\<variant:key\></td><td>

*bool*</td><td>

如果映射中存在指定键，则返回 **True**。
</td></tr><tr><td>
get</td><td>

\<variant:key\></td><td>

*variant*</td><td>
返回指定键的值。
</td></tr><tr><td>
merge</td><td>

\<**Map**:from\></td><td>

*none*</td><td>

将另一个 **Map** 的内容与该 **Map** 合并。
</td></tr><tr><td>
set</td><td>

\<variant:key\>  
\<variant:value\></td><td>

*none*</td><td>
设置指定键的值。
</td></tr></tbody>
</table>