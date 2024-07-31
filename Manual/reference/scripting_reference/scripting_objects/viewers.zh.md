# Viewers

**Viewers** 对象是一个包含所有当前打开的独立 [图像查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 的集合。可以通过 **[DOpus](dopus.zh.md).viewers** 属性获取。

  

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*集合:***[Viewer](viewer.zh.md)**</td><td>
允许您枚举当前打开的查看器。
</td></tr><tr><td>
lastactive</td><td>

*对象:***[Viewer](viewer.zh.md)**</td><td>

返回一个表示最近活动查看器窗口的 **[Viewer](viewer.zh.md)** 对象。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Update</td><td>

*无*</td><td>

*无*</td><td>

脚本第一次访问 **DOpus.viewers** 属性时，会对所有当前打开的查看器进行快照。如果在此之后有查看器打开或关闭，这些更改不会反映在快照中，除非您通过调用 **Update** 方法重新同步。
</td></tr></tbody>
</table>