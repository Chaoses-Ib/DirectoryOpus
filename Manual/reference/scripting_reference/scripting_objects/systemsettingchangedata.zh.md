# SystemSettingChangeData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnSystemSettingChange](../scripting_events/onsystemsettingchange.zh.md)** 事件，当各种系统设置发生变化时，方法将接收一个 **SystemSettingChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
type</td><td>

*string*</td><td>

返回一个字符串，指示发生变化的设置。设置包括：

|                         |                                                                                                                                                                                                                                                               |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **theme**               | Windows 主题（视觉样式）已更改                                                                                                                                                                                                                  |
| **colorset**            | Opus 已从浅色模式更改为深色模式或反之                                                                                                                                                                                                        |
| **environment**         | 系统环境变量已更改                                                                                                                                                                                                                |
| **dwmcomposition**      | 指示 Windows DWM 合成已开启或关闭。                                                                                                                                                                                             |
| **dwmcolorization**     | 指示 Windows DWM 颜色已更改。                                                                                                                                                                                                     |
| **intl**                | 系统区域设置已更改。                                                                                                                                                                                                                                |
| **userinteractionmode** | 系统输入方法已更改（从鼠标到触控或反之）。可以使用 **[SysInfo](sysinfo.zh.md).TouchInput** 方法查询当前方法。                                                                                                  |
| **spacingscheme**       | 指示 [UI 间距方案已更改](/Manual/preferences/preferences_categories/user_interface/spacing.zh.md)。新方案名称可在 **name** 属性中获得。还可以使用 **[DOpus](dopus.zh.md).spacingscheme** 属性查询方案。 |
| **windowmetrics**       | 系统窗口度量已更改（例如字体大小）。                                                                                                                                                                                                          |
</td></tr><tr><td>
name</td><td>

*string*</td><td>
返回受支持设置的名称字符串。
</td></tr></tbody>
</table>