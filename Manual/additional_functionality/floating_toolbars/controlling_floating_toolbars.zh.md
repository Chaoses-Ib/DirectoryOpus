# 控制浮动工具栏

您可以更改许多会影响浮动工具栏的外观和行为的设置。

在 [自定义](/Manual/customize/README.zh.md) 模式下，将鼠标光标移动到浮动工具栏上时，工具栏右上角将显示一个小的图标 (![](/Manual/images/media/dock-edit.png))。单击该图标将显示以下上下文菜单。

![](/Manual/images/media/floater_edit.png)

如果您不在自定义模式下，还可以通过右键单击工具栏本身中的某个空白部分来显示此菜单（尽管这可能并不容易，例如如果边框已被关闭）。

- **自定义**：提供了一种快速方法，用于返回到“自定义”对话框。
- **外观**：此子菜单有许多影响浮动工具栏外观的选项。
  \* **框架**：工具栏将具有固定的背景和框架（可以选择带圆角）。  
  ![](/Manual/images/media/floater_-_frame.png)

      * **无框架**：工具栏将具有固定的背景，但没有框架 - 按钮将紧贴边缘.\\

![](/Manual/images/media/floater_-_no_frame.png)

      * **透明**：工具栏完全没有背景 - 它将显示为工具栏上的按钮漂浮在桌面上。由于透明工具栏更难操作，因此实际的工具栏不会在您退出“自定义”模式前变为透明 - 相反，它将以棋盘格图案渲染。退出“自定义”模式后，当您将鼠标移动到工具栏上时，如果按住 **Shift** 键，工具栏将显示其普通框架，这允许您重新定位透明工具栏.\\

![](/Manual/images/media/floater_-_transparent.png)

      * **玻璃**：工具栏将在 Vista 和 Windows 7 中以半透明的玻璃背景呈现。微软不再在 Windows 8 中考虑采用半透明的效果，因此从 Windows 8 以后，您将看到系统“色调”颜色，没有任何半透明效果.\\

![](/Manual/images/media/floater_-_glass.png)

      * **任务栏**：工具栏将以与 Windows 任务栏相同的样式呈现（因此在 Windows 的每个版本中外观自然不同）。\\

![](/Manual/images/media/floater_-_taskbar.png)

      * **圆角**：当工具栏设置为具有框架的类型时，它将具有圆角（如上面的图片所示）而不是直角。
      * **相同大小的按钮**：使浮动工具栏中的所有按钮都具有相同的大小。打开此选项时，所有工具栏按钮的大小都将与最大的按钮相同。
      * **垂直**：浮动工具栏将具有垂直方向，而不是水平方向。\\
    * **自动隐藏**：仅当工具栏停靠在屏幕一侧时，此选项才可用。如果打开此选项，工具栏将隐藏，直到鼠标移至其上时才能显示。
    * **启用热键：**当工具栏处于浮动状态时，其热键将变成系统全局热键 - 也就是说，它们可以在 Windows 的任何地方工作，而无需 Opus 或工具栏处于活动状态。这非常有用，但也可能造成混乱，因为热键将覆盖其他程序中使用相同的按压键。例如，如果某个工具栏按钮将 Ctrl-C 定义为热键并且将其设置为全局热键，您将不再能够在任何其他程序中按 Ctrl-C 复制到剪贴板！因此，默认情况下，在工具栏浮动时，为工具栏按钮定义的热键将被禁用。您可以使用此选项启用它们。
    * **置于顶层**：工具栏将显示在其他窗口之上。
    * **锁定位置**：锁定工具栏在屏幕上的位置，使其无法拖动或调整大小。
    * **新建**：创建新的工具栏按钮。
    * **关闭**：关闭浮动工具栏。

如需，您可以浮动相同工具栏的多个副本，Opus 将单独记住每个工具栏的设置。