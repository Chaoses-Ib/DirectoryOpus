如果某个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnSystemSettingChange](../scripting_events/onsystemsettingchange.zh.md)** 事件，那么该方法会在各种系统设置更改时收到 **SystemSettingChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
type</td><td>

*string*</td><td>

返回一个表示已更改设置的字符串。设置如下：

|                         |                                                                                                                                                                                                                                                               |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **theme**               | Windows 主题（视觉样式）已更改                                                                                                                                                                                                                  |
| **colorset**            | Opus 已从亮模式切换到暗模式，反之亦然                                                                                                                                                                                                        |
| **environment**         | 系统环境变量已更改                                                                                                                                                                                                                |
| **dwmcomposition**      | 指示 Windows DWM 合成已开启或关闭。                                                                                                                                                                                             |
| **dwmcolorization**     | 指示 Windows DWM 着色已更改。                                                                                                                                                                                                     |
| **intl**                | 系统区域设置已更改。                                                                                                                                                                                                                                |
| **userinteractionmode** | 系统输入法已更改（从鼠标更改为触控，反之亦然）。当前方法可通过 **[SysInfo](sysinfo.zh.md).TouchInput** 方法查询。                                                                                                  |
| **spacingscheme**       | 指示 [UI 间距方案已更改](/Manual/preferences/preferences_categories/user_interface/spacing.zh.md)。新方案名称在 **name** 属性中可用。还可以使用 **[DOpus](dopus.zh.md).spacingscheme** 属性查询方案。 |
| **windowmetrics**       | 系统窗口度量已更改（例如，字体大小）。                                                                                                                                                                                                          |
</td></tr><tr><td>
name</td><td>

*string*</td><td>
返回受支持设置的名称字符串。
</td></tr></tbody>
</table>