# 文件夹标签
## 如何让文件夹标签垂直排列？
![](images/README/垂直排列.png)

在 `配置/文件夹标签/选项/标签位置` 中选择 `左侧` 或 `右侧`。

设置 `双栏位置` 为 `一起` 可以让双栏状态下的文件夹标签显示在一起，即左栏在右侧显示，右栏在左侧显示；`分开` 可以让文件夹标签对立显示，即左栏在左侧显示，右栏在右侧显示。

## 文件夹标签颜色
### 文件夹标记颜色
默认情况下，文件夹标签的颜色与文件夹的标记颜色是独立的[^color-1][^color-2]。如果想让文件夹标签默认使用文件夹的标记颜色，可以安装脚本 [TabColorizer](https://github.com/Chaoses-Ib/IbDOpusScripts/blob/main/README.zh-Hans.md#:~:text=%E7%BC%A9%E7%95%A5%E5%9B%BE%E5%B0%BA%E5%AF%B8%EF%BC%9A-,TabColorizer,-%E4%BD%BF%E7%94%A8%E6%96%87%E4%BB%B6%E5%A4%B9)：

使用前 | 使用后
--- | ---
![](https://github.com/Chaoses-Ib/IbDOpusScripts/blob/9f6ac321b31d21bb20ed46b678f7d5f722865fb1/Scripts/TabColorizer/images/before.png?raw=true) | ![](https://github.com/Chaoses-Ib/IbDOpusScripts/blob/9f6ac321b31d21bb20ed46b678f7d5f722865fb1/Scripts/TabColorizer/images/after.png?raw=true)

[^color-1]: [DO12 - Tabs color - Help & Support - Directory Opus Resource Centre](https://resource.dopus.com/t/do12-tabs-color/22194)
[^color-2]: [Tab Color from Label Assignments - Help & Support - Directory Opus Resource Centre](https://resource.dopus.com/t/tab-color-from-label-assignments/23473)

### 命令
设置 RGB 颜色：
```cmd
Go TABCOLOR #ff8000
```
或
```cmd
Go TABCOLOR 255,128,0
```

重置颜色：
```
Go TABCOLOR=reset
```

## 关闭文件夹标签
### 关闭单个标签
命令：
```cmd
Go TABCLOSE=文件列表
```
默认为当前文件列表，`left` 为左栏，`right` 为右栏，`dest` 为目标文件列表。

例子：

关闭当前标签：
```cmd
Go TABCLOSE
```

### 关闭多个标签
命令：
```cmd
Go TABCLOSEALL=标签范围
```
默认为当前文件列表中的所有其它标签，`left` 为左侧所有标签，`right` 为右侧所有标签，`dest` 为目标文件列表的所有标签，`force` 为强制关闭锁定标签；可组合使用。

例子：

关闭当前文件列表中的所有其它标签：
```cmd
Go TABCLOSEALL
```

### 撤销关闭标签
命令：
```cmd
Go TABUNDOCLOSE
```