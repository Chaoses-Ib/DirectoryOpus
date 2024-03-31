# 图标集 XML 定义文件

该 XML 文件定义了构成图标集的图标。下面是一个图标集 .xml 文件示例：

  
`<?xml version="1.0"encoding="utf-8"?>
<iconset name="sample">
    <display_name>示例图标集</display_name>
    <copyright>(c)2007 Fred Bloggs Productions</copyright>
    <artist>Fred Bloggs</artist>
    <set size="small" width="20" height="20" filename="MyIconsSmall.png">
        <icon name="copy" row="1" col="1" />
        <icon name="move" row="1" col="2" />
    </set>
    <set size="large" width="32" height="32" filename="MyIconsLarge.png">
        <icon name="copy" row="1" col="1" />
        <icon name="move" row="1" col="2" />
    </set>
</iconset>`

定义文件的根节点称为 `iconset`。此处给出的 `name` 属性指定用于此集的内部名称。该名称绝不会显示给用户，但内部用于引用用户在其工具栏中配置的图标。为图标集选择一个唯一名称非常重要 - 如果安装了两个具有相同内部名称的图标集，则其内容将被合并在一起，就像它们是一个大集合一样。

根节点下的几个值可让你指定图标集元数据 - **display_name** 是实际显示给用户的该集的名称，而 **copyright** 和 **artist** 是在配置的图标集列表中显示的字符串。

在此之后，**set** 节点用于指定集中一个或多个图标。每个图标集可以包含一组或两组不同的图标 - 一个 **small** 组和一个 **large** 组。**set** 节点中的 **size** 属性指定正在定义哪种图标尺寸，**width** 和 **height** 属性定义图标的实际像素大小。**filename** 属性指定此组图标从中绘制的图像文件。

每个 **set** 节点下方有一个或多个 **icon** 节点，该节点定义组成该集的各个图标。每个图标必须使用 **name** 属性指定一个名称，其所在图像文件中的行和列使用 **row** 和 **col** 属性指定。

 