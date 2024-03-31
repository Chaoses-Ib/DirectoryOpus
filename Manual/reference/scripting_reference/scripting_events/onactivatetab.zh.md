[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 可以在每次制表符变为活动（即位于同一文件列表中其他制表符的前面）时实现 **OnActivateTab** 事件，以接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnActivateTab
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[ActivateTabData](../scripting_objects/activatetabdata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

*无*
</td></tr><tr><td>

**说明：**</td><td>

**ActivateTabData.oldtab** 属性识别出之前活动的制表符，**newtab** 属性识别出新活动制表符。
</td></tr></tbody>
</table>