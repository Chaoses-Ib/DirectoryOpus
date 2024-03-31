**SysInfo** 对象由 **[DOpusFactory](dopusfactory.zh.md).SysInfo** 方法创建。此方法允许脚本访问难以从脚本中获取的其他系统信息。

<table>
<thead>
<tr>
<th>
方法名称</th>
<th>
参数</th>
<th>
返回类型</th>
<th>
说明
</th>
</tr>
</thead>
<tbody>
<tr>
<td>
DarkMode</td>
<td>

*无*</td>
<td>

*布尔值*</td>
<td>

如果 Opus 中启用了“深色模式”，则返回 true，否则返回 false。

如果将 Opus 配置为覆盖系统范围的设置，或在没有“深色模式”的旧版 Windows 上，则可能不同于 **DarkModeApps**。
</td>
</tr>
<tr>
<td>
DarkModeApps</td>
<td>

*无*</td>
<td>

*布尔值*</td>
<td>

如果将 Windows 配置为在“深色模式”下运行应用程序，则返回 true，否则返回 false。

在没有“深色模式”的旧版 Windows 上，始终返回 false。
</td>
</tr>
<tr>
<td>
DPI</td>
<td>

*无*</td>
<td>

*int*</td>
<td>
返回 Opus 当前运行的 DPI（例如，96 DPI 为 100% 缩放）。
</td>
</tr>
<tr>
<td>
FindProcess</td>
<td>

*字符串*</td>
<td>

*int*</td>
<td>

允许您测试命名的进程是否正在运行，如果是，则返回进程的 ID。如果进程未运行，则返回 **0**。您可以使用通配符或（通过使用 **regex:** 前缀模式）正则表达式。
</td>
</tr>
<tr>
<td>
Language</td>
<td>

*无*</td>
<td>

*字符串*</td>
<td>
返回表示 Opus 当前使用的语言的字符串。
</td>
</tr>
<tr>
<td>
Monitors</td>
<td>

*无*，
或
*int:index*</td>
<td>

**[Vector](vector.zh.md):[Rect](rect.zh.md)** ，
或
**[Rect](rect.zh.md)**</td>
<td>

如果在没有参数的情况下调用，则返回 **[Vector](vector.zh.md)**，其中包含 **[Rect](rect.zh.md)** 对象，这些对象提供有关系统中显示器位置和大小的信息。

如果使用索引参数调用，则返回具有单个特定显示器信息的单个 **[Rect](rect.zh.md)**。

有时应该使用下面记录的 **WorkAreas** 方法替代此方法。
</td>
</tr>
<tr>
<td>
MouseMonitor</td>
<td>

*无*</td>
<td>

*int*</td>
<td>
返回鼠标指针当前所在显示器的索引。
</td>
</tr>
<tr>
<td>
MousePosX</td>
<td>

*无*</td>
<td>

*int*</td>
<td>
返回鼠标指针当前的 x 坐标。
</td>
</tr>
<tr>
<td>
MousePosY</td>
<td>

*无*</td>
<td>

*int*</td>
<td>
返回鼠标指针当前的 y 坐标。
</td>
</tr>
<tr>
<td>
ShadowBorder</td>
<td>

*无*</td>
<td>

**[Rect](rect.zh.md)**</td>
<td>

返回一个 **[Rect](rect.zh.md)**，给出窗口周围不可见的边框的大小。

在某些操作系统（例如 Windows 10）上，窗口可能大于显示的窗口：在可见边缘的超出了是一个边框，它是窗口的一部分，但不可见。此边框存在于旧版本中，以允许窗口边框显示纤细，同时提供足够厚的东西以通过鼠标进行调整。

 通常情况下，可以忽略边框，但当将窗口相互放置或放置在屏幕边缘时，忽略边框会导致窗口之间出现间隙，此时边框就非常重要。

此方法返回的 **Rect** 是不同寻常的：**left**、**right**、**top** 和 **bottom** 属性不表示矩形的坐标，而是表示窗口每侧的边框宽度（如果有）。因此，**Rect** 的 **width** 和 **height** 属性是无意义的。

在 Windows 10 上，顶部边框通常为零，而其他边框通常为几个像素。厚度因操作系统版本、系统 DPI 和其他因素而异；您不应该将其存储到磁盘中，因为它对于加载它的系统可能不正确。

计算此属性相对耗时。例如，您不应该为每侧调用此方法一次；相反，调用它一次并将 **Rect** 存储在变量中，然后针对每一侧查询该变量。
</td>
</tr>
<tr>
<td>
SystemDPI</td>
<td>

*无*</td>
<td>

*int*</td>
<td>

返回系统当前运行的 DPI（例如，96 DPI 为 100% 缩放）。这通常与 **DPI** 值相同，但如果系统 DPI 已更改且 Opus 尚未重新启动，则这两个值可能不同。
</td>
</tr>
<tr>
<td>
TouchInput</td>
<td>

*无*</td>
<td>

*布尔值*</td>
<td>

如果系统当前使用触控输入，则返回 **True**。
</td>
</tr>
<tr>
<td>
USBInstall</td>
<td>

*无*</td>
<td>

*布尔值*</td>
<td>

如果 Opus 是从 [USB 导出](/Manual/additional_functionality/exporting_to_usb.zh.md) 运行的，则返回 **True**。
</td>
</tr>
<tr>
<td>
WorkAreas</td>
<td>

*无*，
或
*int:index*</td>
<td>

**[Vector](vector.zh.md):[Rect](rect.zh.md)** ，
或
**[Rect](rect.zh.md)**</td>
<td>

类似于上面记录的 **Monitors** 方法，但它返回的是每个显示器的“工作区”，而不是整个显示器区域。

显示器的“工作区”是显示器的矩形，减去 Windows 任务栏和任何其他“应用程序栏”（其中可以包括由 Opus 创建的已停靠工具栏或其他软件添加的类似内容）。如果显示器没有任务栏或其他应用程序栏停靠在其上，则其工作区与其整个矩形相同。
</td>
</tr>
</tbody>
</table>