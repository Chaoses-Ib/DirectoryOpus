# Go
## 跳转
```cmd
Go PATH=跳转路径
```
参数名 PATH 可省略（`Go 跳转路径`）。

当跳转路径内含有空格时，需要在两边添加双引号。

例子：  
跳转到剪切板中的路径（目录或文件）：
```cmd
Go "{clip}"
```
只能用于纯文本路径，不能用于文件对象。

### 跳转到真实路径
```cmd
Go OPENCONTAINER=target
```

<details>

- OPENCONTAINER：文件集合、库、平面视图
  ```cmd
  Go OPENCONTAINER
  ```
- OPENCONTAINER：文件集合、库、平面视图、快捷方式、符号链接、junction
  ```cmd
  Go OPENCONTAINER=target
  ```
- {filepath}  
  ```cmd
  @set a={filepath}
  Go {$a}
  ```
  如果不将 `{filepath}` 设置到变量，路径就不会被展开为真实路径。

  另一种展开方法是：
  ```cmd
  dopusrt.exe /open {filepath}
  ```
- 打开文件所在的位置  
  ```cmd
  ContextMenu VERB="opencontaining" LOOKUP
  ```
  只能在新窗口打开。
</details>

## 关闭文件夹标签
### 关闭单个标签
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
```cmd
Go TABUNDOCLOSE
```

## 设置文件夹标签颜色
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