# 视图
可用的视图有：
- [详细](#详细视图)（默认）
- [增强模式](#增强模式)
- [缩略图](缩略图.md)
- 列表
- 小图标
- 大图标
- 平铺
- [平面视图](平面视图.md)

## 如何让缩略图、图标和平铺视图显示完整文件名？
在缩略图、大图标、小图标和平铺视图下，如果文件名在一定宽度内显示不下，DOpus 就会用“...”代替剩下的文件名，带来了一些不便。

缩略图的文件名行数可以在 `查看模式/缩略图/文字高度` 处设置，但大图标、小图标和平铺的文件名行数则无法设置。需要注意的是，即使增大了缩略图的文件名行数，也只有含有空格的文件名才能显示多行，不含空格的文件名仍然只能显示一行：

![](images/缩略图/文字高度.jpg)

过长文件名的“...”省略无法关闭，但有三种绕过方法：
- 调整 `查看模式/缩略图/间隔`，增大第一个水平间隔，让每行显示更多字符
- 调整 `查看模式/缩略图/大小`（取消勾选 `显示成方形`），增加缩略图宽度，让每行显示更多字符
- 关闭 `显示/选项/试用视觉模式拖曳条目`（使用视觉样式绘制项目），这样在选中文件时就会显示完整文件名，但这也会导致选中变丑一些