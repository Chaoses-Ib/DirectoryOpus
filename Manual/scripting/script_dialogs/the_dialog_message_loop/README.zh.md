# 对话消息循环

有两种方法可以让你脚本管理对话框的显示。

- **简单：**“简单”方法显示对话并不会在用户关闭它之前将控制权返回到脚本。使用简单方法显示的对话框只能作为“哑”数据输入窗口使用。一旦对话框返回，你的脚本就可以读取对话框中任何控件的值，但它不能在对话框打开时与对话框交互。
  \* **分离：**另一种更复杂的方法称为“分离”。使用此方法，脚本显示对话框并立即接收回控制权。然后脚本负责运行一个“消息循环”，它处理对话框中的用户操作。脚本可以检测到用户点击按钮或输入数据的时候，并且能够与对话框中的控件交互，例如更新列表、启用或禁用选项或显示消息。
分离的方法要灵活得多，你可能希望经常使用此方法，但是如果你只有一个简单的对话框供用户输入数据，那么第一种方法使用起来更容易。
**[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md)** 对象是创建和显示脚本对话框的主要对象。要使用**[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md)** 对象显示脚本对话框，请在调用**Show** 方法之前将它的**template** 参数设置成对话框的名称。
更多信息：
[简单对话框](/Manual/scripting/script_dialogs/the_dialog_message_loop/simple_dialogs.zh.md)  
[分离的对话框](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.zh.md)