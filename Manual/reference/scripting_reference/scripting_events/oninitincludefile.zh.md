**OnInitIncludeFile** 事件对每个 [包含文件](/Manual/scripting/script_add-ins/include_files.zh.md) 脚本调用一次，以对其进行初始化。实现此事件是可选的，但强烈建议您实现，因为它允许您提供名称、**描述** 和其他信息，例如最小版本要求。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnInitIncludeFile
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[IncludeFileInitData](../scripting_objects/includefileinitdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*无*
</td></tr><tr><td>

**描述：**</td><td>

Opus 启动后或者某个包含文件脚本已添加或已编辑时，将调用其 **OnInitIncludeFile** 方法。这给了包含文件一个机会来通过设置 **IncludeFileInitData** 对象的各个属性向 Opus 讲述有关它自己的信息。
</td></tr></tbody>
</table>