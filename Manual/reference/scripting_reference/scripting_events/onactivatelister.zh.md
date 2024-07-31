# OnActivateLister

**OnActivateLister** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便每当文件窗口窗口变为活动窗口或失去激活状态（归于其它窗口）时都能收到通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnActivateLister
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[ActivateListerData](../scripting_objects/activatelisterdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*无*
</td></tr><tr><td>

**说明：**</td><td>

**ActivateListerData.lister** 属性用于标识文件窗口，**active** 属性用于指示此文件窗口是处于活动状态还是非活动状态。如果激活从一个文件窗口移动到另一个文件窗口，则此事件将被调用两次，每次对应一个文件窗口。
</td></tr></tbody>
</table>