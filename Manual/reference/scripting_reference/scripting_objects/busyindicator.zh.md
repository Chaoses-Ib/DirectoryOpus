**BusyIndicator** 对象允许您从脚本控制面包屑栏忙碌指示器。

![](/Manual/images/media/throbbler.png)

默认情况下，忙碌指示器仅表示正在发生某些事情；它还可以用于指示作业的进度（从 0% 到 100% 的完成百分比）。用户可以单击旋转圆圈以查看正在运行的作业的描述，并且每个作业可以选择允许用户通过显示他们可以单击的 *中止* 链接来中止它。

**BusyIndicator** 对象使用 **[DOpusFactory](dopusfactory.zh.md).BusyIndicator** 方法创建。在脚本中使用一个对象的步骤如下：

1.  通过调用 **DOpus.Create.BusyIndicator()** 创建对象。
2.  可以选择将 **abort** 属性设置为 **True** 以启用用户中止。
3.  调用 **Init** 方法以初始化并显示忙碌指示器。
4.  在需要时调用 **Update** 方法以更新进度或说明性文字。
5.  如果需要，轮询 **abort** 属性以检查用户中止。
6.  在作业完成后调用 **Destroy** 方法以移除忙碌指示器。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
abort</td><td>

*bool*</td><td>

在调用 **Init** 方法之前，您可以将此属性设置为 **True** 以启用用户中止（如上所示）。  
调用 **Init** 之后，如果用户单击了 *中止* 链接，此属性将返回 **True**。  
lister 或与您的 **BusyIndicator** 关联的标签页关闭不会更改 **abort** 属性。如果您需要在发生这种情况时停止，那么您必须单独检查它，通常通过测试 **Update** 方法的结果来进行。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
Destroy</td><td>

*none*</td><td>

*bool*</td><td>

从显示中移除忙碌指示器并销毁其内部数据结构。可以通过再次调用 **Init** 方法来重新使用 **BusyIndicator** 对象。  
返回布尔值成功。失败通常意味着 lister 或标签页已关闭。
</td></tr><tr><td>
Hide</td><td>

*none*</td><td>

*bool*</td><td>

从显示中移除忙碌指示器，但不销毁其内部数据。可以通过调用 **Show** 方法来重新显示指示器。  
返回布尔值成功。失败通常意味着 lister 或标签页已关闭。
</td></tr><tr><td>
Init</td><td>

\<object:window\>  
\<string:description\>  
\<bool:visible\></td><td>

*bool*</td><td>

初始化 **BusyIndicator** 对象，并可以选择显示它。  
**window** 参数指定将指示器附加到的 **[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)** 对象。通常最好使用 **Tab**。  
可选的 **description** 参数允许您指定在用户单击旋转圆圈时显示给用户的文本字符串。  
可选的 **visible** 参数允许您通过传递 **True** 立即使指示器可见。或者，调用 **Show** 方法以使指示器可见。  
返回布尔值成功。失败通常意味着文件窗口或标签页已关闭或无效。
</td></tr><tr><td>
Show</td><td>

*none*</td><td>

*bool*</td><td>

显示忙碌指示器。  
返回布尔值成功。失败通常意味着 lister 或标签页已关闭。
</td></tr><tr><td>
Update</td><td>

\<string:description\>  
\<int:percentage\></td><td>

*bool*</td><td>

更新忙碌指示器。  
**description** 参数允许您指定新的描述字符串。  
可选的 **percentage** 参数允许您指定从 0 到 100 的新进度条百分比。如果没有指定 **percentage**，并且上次调用未设置 **percentage**，进度条将显示一个动画，指示正在发生某些事情，而没有已知的百分比。  
返回布尔值成功。失败通常意味着 lister 或标签页已关闭。
</td></tr></tbody>
</table>