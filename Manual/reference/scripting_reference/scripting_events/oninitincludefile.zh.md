# OnInitIncludeFile

**OnInitIncludeFile** 事件针对每个 [包含文件](/Manual/scripting/script_add-ins/include_files.zh.md) 脚本调用一次，用于初始化脚本。实现此事件是可选的，但建议进行，因为它允许您提供名称、描述以及其它信息，例如最低版本要求。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnInitIncludeFile
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[IncludeFileInitData](../scripting_objects/includefileinitdata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

当 Opus 启动或添加或编辑包含文件脚本时，将调用其 **OnInitIncludeFile** 方法。这使包含文件有机会通过设置 **IncludeFileInitData** 对象的各种属性来告诉 Opus 有关自身的信息。
</td></tr></tbody>
</table>