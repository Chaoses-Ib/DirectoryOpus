# 命令
## 修饰符
### 操作对象
修饰符 | 功能
--- | ---
@disalbenosel | 未选中文件时禁用按钮
@hidenosel | 未选中文件时隐藏按钮
@filesonly | 只对选中的文件执行操作
@firstfileonly | 只对选中的第一个文件执行操作
@dirsonly | 只对选中的目录执行操作
@nodeselect | 执行函数后不取消选中当前文件

重命名文件后不取消选中：
```cmd
@disalbenosel
Rename ADVANCED
@nodeselect
```