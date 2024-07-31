# BusyIndicator

一个 **BusyIndicator** 对象允许您从脚本中控制面包屑栏的忙碌指示器。

![](/Manual/images/media/throbbler.png)

默认情况下，忙碌指示器只是表示正在发生某些事情；它也可以用于指示作业的进度（从 0% 到 100% 的完成百分比）。用户可以点击旋转圆圈以查看正在运行的作业的描述，并且每个作业可以选择允许用户通过显示一个 *Abort* 链接来中止它，用户可以点击该链接。

**BusyIndicator** 对象是使用 **[DOpusFactory](dopusfactory.zh.md).BusyIndicator** 方法创建的。在您的脚本中使用一个的基本步骤是：

1.  通过调用 **DOpus.Create.BusyIndicator()** 创建对象。
2.  可以选择将 **abort** 属性设置为 **True** 以启用用户中止。
3.  调用 **Init** 方法初始化并显示忙碌指示器。
4.  在需要时调用 **Update** 方法来更新进度或说明性文本。
5.  如果需要，轮询 **abort** 属性以检查用户是否中止。
6.  在作业完成后，调用 **Destroy** 方法以删除忙碌指示器。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
abort</td><td>

*bool*</td><td>

在调用 **Init** 方法之前，您可以将此属性设置为 **True** 以启用用户中止（如上所示）。  
在调用 **Init** 之后，如果用户点击了 *Abort* 链接，此属性将返回 **True**。  
如果与您的 **BusyIndicator** 关联的文件窗口或标签页关闭，则 **abort** 属性不会改变。如果您需要在发生这种情况时停止，则必须单独检查，通常是通过测试 **Update** 方法的结果。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Destroy</td><td>

*无*</td><td>

*bool*</td><td>

从显示中删除忙碌指示器并销毁其内部数据结构。**BusyIndicator** 对象本身可以通过再次调用 **Init** 方法来重新使用。  
返回布尔值成功。失败通常意味着文件窗口或标签页已关闭。
</td></tr><tr><td>
Hide</td><td>

*无*</td><td>

*bool*</td><td>

从显示中删除忙碌指示器，但不会销毁其内部数据。可以通过调用 **Show** 方法重新显示指示器。  
返回布尔值成功。失败通常意味着文件窗口或标签页已关闭。
</td></tr><tr><td>
Init</td><td>

\<object:window\>  
\<string:description\>  
\<bool:visible\></td><td>

*bool*</td><td>

初始化一个 **BusyIndicator** 对象并选择性地显示它。  
**window** 参数指定要附加指示器的 **[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)** 对象。通常最好使用 **Tab**。  
可选的 **description** 参数允许您指定在用户点击旋转圆圈时显示给用户的文本字符串。  
可选的 **visible** 参数允许您通过传递 **True** 立即使指示器可见。或者，调用 **Show** 方法以使指示器可见。  
返回布尔值成功。失败通常意味着文件窗口或标签页已关闭或无效。
</td></tr><tr><td>
Show</td><td>

*无*</td><td>

*bool*</td><td>

显示忙碌指示器。  
返回布尔值成功。失败通常意味着文件窗口或标签页已关闭。
</td></tr><tr><td>
Update</td><td>

\<string:description\>  
\<int:percentage\></td><td>

*bool*</td><td>

更新忙碌指示器。  
**description** 参数允许您指定新的描述字符串。  
可选的 **percentage** 参数允许您指定 0 到 100 之间的新的进度条百分比。如果没有指定 **percentage**，并且之前没有调用设置，进度条将显示动画，表示正在发生某些事情，但没有已知的百分比。  
返回布尔值成功。失败通常意味着文件窗口或标签页已关闭。
</td></tr></tbody>
</table>