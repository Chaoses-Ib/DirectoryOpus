# SysInfo

**SysInfo** 对象由 **[DOpusFactory](dopusfactory.zh.md).SysInfo** 方法创建。它允许脚本访问各种系统信息，这些信息可能无法通过其它方式从脚本中轻松获取。

<table>
<thead><tr><th>
方法名称</th><th>
参数</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
DarkMode</td><td>

*无*</td><td>

*bool*</td><td>

如果 Opus 中启用了深色模式，则返回 true，否则返回 false。

如果 Opus 配置为覆盖系统范围的设置，或者在没有深色模式的旧版 Windows 上，则可能与 **DarkModeApps** 不同。
</td></tr><tr><td>
DarkModeApps</td><td>

*无*</td><td>

*bool*</td><td>

如果 Windows 配置为在深色模式下运行应用程序，则返回 true，否则返回 false。

在没有深色模式的旧版 Windows 上始终返回 false。
</td></tr><tr><td>
DPI</td><td>

*无*</td><td>

*int*</td><td>
返回 Opus 当前运行的 DPI（例如 96 DPI 为 100% 缩放）。
</td></tr><tr><td>
FindProcess</td><td>

*string*</td><td>

*int*</td><td>

允许您测试命名进程是否正在运行，如果正在运行，则返回进程的 ID。如果进程未运行，则返回 **0**。您可以使用通配符或（通过在模式前加上 **regex:**）正则表达式。
</td></tr><tr><td>
Language</td><td>

*无*</td><td>

*string*</td><td>
返回一个字符串，指示 Opus 当前使用的语言。
</td></tr><tr><td>
Monitors</td><td>

*无*  
或  
*int:index*</td><td>

**[Vector](vector.zh.md):[Rect](rect.zh.md)**   
或  
**[Rect](rect.zh.md)**</td><td>

如果调用时没有参数，则返回一个包含 **[Rect](rect.zh.md)** 对象的 **[Vector](vector.zh.md)**，这些对象提供有关系统中显示器位置和大小的信息。

如果调用时带有索引参数，则返回一个单独的 **[Rect](rect.zh.md)**，其中包含特定显示器的信息。

下面介绍的 **WorkAreas** 方法有时是您应该使用的方法，而不是此方法。
</td></tr><tr><td>
MouseMonitor</td><td>

*无*</td><td>

*int*</td><td>
返回鼠标指针当前所在显示器的索引。
</td></tr><tr><td>
MousePosX</td><td>

*无*</td><td>

*int*</td><td>
返回鼠标指针的当前 x 坐标。
</td></tr><tr><td>
MousePosY</td><td>

*无*</td><td>

*int*</td><td>
返回鼠标指针的当前 y 坐标。
</td></tr><tr><td>
ShadowBorder</td><td>

*无*</td><td>

**[Rect](rect.zh.md)**</td><td>

返回一个 **[Rect](rect.zh.md)**，给出窗口周围不可见边框的大小。

在某些操作系统（例如 Windows 10）上，窗口可能比它们看起来更大：在可见边缘之外是窗口的一部分，但不可见。此边框存在是为了向后兼容，允许窗口框架看起来很薄，同时提供足够厚的东西以便用鼠标调整大小。

您通常可以忽略边框，但在将窗口并排放置或放置到屏幕边缘时，它很重要，忽略它会导致窗口之间出现间隙。

此方法返回的 **Rect** 很不寻常：**left**、**right**、**top** 和 **bottom** 属性不代表矩形的坐标，而是表示窗口每侧边框的宽度（如果有）。因此，**Rect** 的 **width** 和 **height** 属性毫无意义。

在 Windows 10 上，顶部边框通常为零，其它边框通常有几个像素宽。厚度因操作系统版本、系统 DPI 和其它因素而异；您不应该将其存储到磁盘，因为它可能不适用于加载它的系统。

此属性计算起来相对昂贵。例如，您不应该为每侧调用一次方法；而是调用一次并将 **Rect** 存储在一个变量中，然后为每侧查询该变量。
</td></tr><tr><td>
SystemDPI</td><td>

*无*</td><td>

*int*</td><td>

返回系统当前运行的 DPI（例如 96 DPI 为 100% 缩放）。这通常与 **DPI** 值相同，但如果系统 DPI 发生了更改而 Opus 未重新启动，它们可能不同。
</td></tr><tr><td>
TouchInput</td><td>

*无*</td><td>

*bool*</td><td>

如果系统当前使用触摸输入，则返回 **True**。
</td></tr><tr><td>
USBInstall</td><td>

*无*</td><td>

*bool*</td><td>

如果 Opus 从 [USB 导出](/Manual/additional_functionality/exporting_to_usb.zh.md) 中运行，则返回 **True**。
</td></tr><tr><td>
WorkAreas</td><td>

*无*  
或  
*int:index*</td><td>

**[Vector](vector.zh.md):[Rect](rect.zh.md)**   
或  
**[Rect](rect.zh.md)**</td><td>

与上面介绍的 **Monitors** 方法类似，但它返回每个显示器的 *工作区* 而不是整个显示器区域。

显示器的 *工作区* 是显示器的矩形减去 Windows 任务栏和任何其它 *应用程序栏*（可以包括 Opus 创建的对接工具栏，或者其它软件添加的类似内容）。如果显示器没有对接在其上的任务栏或其它应用程序栏，则其工作区将与其完整矩形相同。
</td></tr></tbody>
</table>