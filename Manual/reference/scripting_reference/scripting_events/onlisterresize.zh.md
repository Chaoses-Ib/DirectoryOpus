# OnListerResize

**OnListerResize** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便在每次调整文件窗口窗口大小时收到通知。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnListerResize
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[ListerResizeData](../scripting_objects/listerresizedata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*无*
</td></tr><tr><td>

**描述:**</td><td>

**ListerResizeData.lister** 属性标识文件窗口，**action** 属性是一个 *字符串*，指示执行调整大小操作的元素。使用 **width** 和 **height** 属性确定新窗口的大小。
</td></tr></tbody>
</table>