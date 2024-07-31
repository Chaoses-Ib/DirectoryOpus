# Map

**Map** 对象是一个[关联容器](http://en.wikipedia.org/wiki/Associative_container)。它类似于数组或向量（例如 **[Vector](vector.zh.md)**），因为它可以存储一个或多个对象，但它具有使用字典系统来定位对象而不是数字索引的优势。因此，您可以使用任意值（字符串、整数、日期等）作为键插入或查找对象。（注意，键会隐式转换为字符串，无论初始类型如何。）

您可以像访问函数一样访问地图的元素（例如 **Map("foo")** 用于通过键 *"foo"* 引用元素）。您也可以使用方括号（像数组或向量一样），但前提是键的名称以下划线开头，或者完全是数字（例如 **Map\[123\]** 或 **Map\["\_foo"\]**）。此外，您还可以使用 **get** 和 **set** 方法。

您可以使用 **[DOpusFactory](dopusfactory.zh.md).Map** 方法创建一个新的 **Map**。

地图中的键可以枚举，并且会自动按字母顺序排序。如果您想保留添加到地图中的项目的顺序，请改用 **[OrderedMap](orderedmap.zh.md)** 对象。

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
描述
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>

返回 **Map** 当前持有的元素数量。
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
描述
</th></tr></thead><tbody><tr><td>
assign</td><td>

\<**Map**:from\></td><td>

*none*</td><td>

将另一个 **Map** 的内容复制到此 **Map** 中。
</td></tr><tr><td>
clear</td><td>

*none*</td><td>

*none*</td><td>

清除 **Map** 的内容。
</td></tr><tr><td>
erase</td><td>

\<variant:key\></td><td>

*none*</td><td>
擦除与指定键匹配的元素（如果它存在于地图中）。
</td></tr><tr><td>
exists</td><td>

\<variant:key\></td><td>

*bool*</td><td>

如果指定键存在于地图中，则返回 **True**。
</td></tr><tr><td>
get</td><td>

\<variant:key\></td><td>

*variant*</td><td>
返回指定键的值。
</td></tr><tr><td>
merge</td><td>

\<**Map**:from\></td><td>

*none*</td><td>

将另一个 **Map** 的内容与当前 **Map** 合并。
</td></tr><tr><td>
set</td><td>

\<variant:key\>  
\<variant:value\></td><td>

*none*</td><td>
设置指定键的值。
</td></tr></tbody>
</table>