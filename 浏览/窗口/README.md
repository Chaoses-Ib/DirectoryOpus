# 文件窗口
![](images/README/文件窗口.png)

文件窗口由文件列表、[文件夹标签](../多文件夹/标签页/README.md)、状态栏、[工具栏](工具栏/README.md)、文件夹树和其它窗格组成。除了必须保留一个文件列表外，文件窗口中的所有其它组件都可移除。

## 新建与关闭
### 如何实现单窗口模式？
见 [单窗口模式](../多文件夹/单窗口模式.md)。

### 如何在关闭最后一个标签页时直接关闭窗口？
在配置窗口中勾选 `文件夹标签/选项/关闭最后的标签页时同时关闭窗口`。或者也可以使用脚本实现：[IbDOpusScripts/CloseTabOrLister](https://github.com/Chaoses-Ib/IbDOpusScripts/blob/main/Buttons/CloseTabOrLister.js)。

## 安全截屏
DOpus 支持对文件窗口进行“安全截屏”，即在截屏时自动对文件名进行打码。默认的安全截屏按钮位于 `操作工具栏 → 帮助 → 安全截图`：

![](images/README/screenshot/toolbar.png)

效果图：

![](images/README/screenshot/secure.png)

该按钮的相应命令为：
```cmd
Clipboard SCREENSHOT=secure
```

该命令会在截屏时播放快门声，同时弹窗进行提示。如果不希望弹出提示，可以将按钮的命令改为：

```cmd
Clipboard SCREENSHOT=secure,quiet
```

另外，也可以添加截屏倒计时，便于截取菜单之类的弹出式界面：
```cmd
Clipboard SCREENSHOT=secure,time:5
```

如果只希望对文件窗口进行截屏而不进行打码，可以去掉以上命令中的 `secure` 参数。