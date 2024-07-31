# QuickFilter

**QuickFilter** 对象提供对标签中快速过滤状态信息的访问。它由 **[Tab](tab.zh.md).quickfilter 属性** 返回。

  

<table>
<thead><tr><th>

**属性名称**</th><th>

**返回类型**</th><th>

**描述**
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*string*</td><td>
返回当前的过滤字符串，如果有的话。
</td></tr><tr><td>
autoclear</td><td>

*bool*</td><td>

返回 **True** 如果自动清除模式在偏好设置中启用。
</td></tr><tr><td>
autostar</td><td>

*bool*</td><td>

返回 **True** 如果自动星标模式在偏好设置中启用。
</td></tr><tr><td>
disable</td><td>

*bool*</td><td>

返回 **True** 如果过滤器已禁用。
</td></tr><tr><td>
easymode</td><td>

*bool*</td><td>

返回 **True** 如果已选择简易模式。
</td></tr><tr><td>
filter</td><td>

*string*</td><td>
返回当前的过滤字符串。
</td></tr><tr><td>
flatview</td><td>

*bool*</td><td>

返回 **True** 如果在平面视图中启用了文件夹过滤。
</td></tr><tr><td>
hidealldirs</td><td>

*bool*</td><td>

返回 **True** 如果所有文件夹都处于隐藏状态。
</td></tr><tr><td>
hideallfiles</td><td>

*bool*</td><td>

返回 **True** 如果所有文件都处于隐藏状态。
</td></tr><tr><td>
overrideflatview</td><td>

*bool*</td><td>

（遗留标志。）返回 **True** 如果在平面视图中启用了文件夹过滤的覆盖。使用 **flatview** 标志来确定它是否实际上处于启用或禁用状态。
</td></tr><tr><td>
partial</td><td>

*bool*</td><td>

返回 **True** 如果启用了部分匹配。
</td></tr><tr><td>
realtime</td><td>

*bool*</td><td>

返回 **True** 如果启用了实时过滤。
</td></tr><tr><td>
regex</td><td>

*bool*</td><td>

返回 **True** 如果启用了正则表达式模式。
</td></tr><tr><td>
showalldirs</td><td>

*bool*</td><td>

返回 **True** 如果所有文件夹都处于显示状态。
</td></tr><tr><td>
showallfiles</td><td>

*bool*</td><td>

返回 **True** 如果所有文件都处于显示状态。
</td></tr><tr><td>
showeverything</td><td>

*bool*</td><td>

返回 **True** 如果 [显示所有内容](/Manual/basic_concepts/searching_and_filtering/show_everything.zh.md) 模式处于启用状态，它会覆盖（几乎）所有过滤操作。
</td></tr></tbody>
</table>