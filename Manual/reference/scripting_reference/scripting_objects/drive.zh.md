# Drive

**Drive** 对象提供了有关系统中驱动器（硬盘驱动器、CD ROM 等）的信息。您可以从 **[FSUtil](fsutil.zh.md).Drives** 方法获取 **[Vector](vector.zh.md)** 中的 **Drive** 对象，每个驱动器对应一个对象。

  

<table>
<thead><tr><th>

**属性名称**</th><th>

**返回** 类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*默认值*</td><td>

*string*</td><td>

返回驱动器的根目录（例如 **C:\\**）。
</td></tr><tr><td>
avail</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

返回一个 **[FileSize](filesize.zh.md)** 对象，指示驱动器上可用的空闲空间。
</td></tr><tr><td>
bpc</td><td>

*int*</td><td>
返回驱动器每个簇的字节数。
</td></tr><tr><td>
filesys</td><td>

*string*</td><td>
返回一个字符串，表示文件系统类型。
</td></tr><tr><td>
flags</td><td>

*int*</td><td>
返回一个表示驱动器文件系统标志的值。
</td></tr><tr><td>
free</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

返回一个 **[FileSize](filesize.zh.md)** 对象，指示驱动器上的总空闲空间。
</td></tr><tr><td>
label</td><td>

*string*</td><td>
返回驱动器的标签。
</td></tr><tr><td>
total</td><td>

*object:***[FileSize](filesize.zh.md)**</td><td>

返回一个 **[FileSize](filesize.zh.md)** 对象，指示驱动器的总大小。
</td></tr><tr><td>
type</td><td>

*string*</td><td>
返回一个字符串，指示驱动器类型（可移动、固定、远程、cdrom、ramdisk）。
</td></tr></tbody>
</table>