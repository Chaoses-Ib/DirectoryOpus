# 命令
## 语法
`命令名 参数 参数...`  
命令名和参数名都不区分大小写，但一般的规范是将命令名首字母大写，参数名全部大写。

参数有四种类型：
- 开关参数（/S）  
    只用来开关选项，不含有值。  
    例如 `Copy MOVE`（移动文件）中的 `MOVE` 就是一个开关参数。
- 值参数  
    `参数名=值`  
    例如 `Copy COPYATTR=no`（复制文件时不保留属性）中的 `COPYATTR` 就是一个值参数，后面的 `no` 是它的值。

    值参数又可以分为四类：
    - 关键字参数（/K）  
        例如上述的 `Copy COPYATTR=no`
    - 数值参数（/N）  
        例如 `FileType NEW=.txt NEWCOUNT=5`（创建 `5` 个 `.txt` 文件）中的 `NEWCOUNT`
    - 多值参数（/M）  
        例如 `Copy FILE a.txt b.txt TO=C:\`（复制 `a.txt` 和 `b.txt` 到 `C:\`）中的 `FILE`
    - 原始参数（/R）  
        例如 `Clipboard SET=hello world`（复制 `hello world` 到剪切板）
    
    多值参数参数名后的等号必须被省略，其它参数可以自由选择是否省略等号，除非值恰好与另一个参数名冲突。

    注意，除了原始参数外，如果值中含有空格，必须要在值两边加上双引号，例如：  
    `Go PATH="C:\Program Files"`
- 可空参数（/O）  
    即有默认值的值参数。  
    例如 `Copy ADDTOARCHIVE`（创建压缩包）中的 `ADDTOARCHIVE` 就是一个可空参数，与 `Copy ADDTOARCHIVE=.zip` 等价。
- 默认参数（空）  
    不指定参数名时默认使用的参数。  
    例如，Go 的默认参数为 `PATH`，`Go C:\Windows` 等价于 `Go PATH=C:\Windows`。

## 修饰符
### 操作对象
修饰符 | 功能
--- | ---
@disablenosel | 未选中文件时禁用按钮
@hidenosel | 未选中文件时隐藏按钮
@filesonly | 只对选中项中的文件执行操作
@firstfileonly | 只对选中项中的第一个文件执行操作
@dirsonly | 只对选中项中的目录执行操作
@nodeselect | 执行函数后保留文件的选中状态

#### 例子
重命名文件后保留选中状态：
```cmd
@disablenosel
Rename ADVANCED
@nodeselect
```