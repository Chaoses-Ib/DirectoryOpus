**驱动器** 对象提供了关于您系统中一个驱动器（硬盘、光盘 ROM 等）的信息。您可以从 **[FSUtil](fsutil.zh.md).Drives** 方法中获取一个 **[矢量](vector.zh.md)** **驱动器** 对象，一个用于您的系统中的每个驱动器。

  

<table><tr><th>

**属性名称**</th><th>

**返回值** 类型</th><th>
说明
</th></tr><tr><td>

*默认值*</td><td>

*字符串*</td><td>

返回驱动器的根目录（例如 **C:\\**）。
</td></tr><tr><td>
可用</td><td>

*Object:***[文件大小](filesize.zh.md)**</td><td>

返回一个 **[文件大小](filesize.zh.md)** 对象，表明驱动器上可用的可用空间。
</td></tr><tr><td>
bpc</td><td>

*int*</td><td>
返回该驱动器的每簇字节数。
</td></tr><tr><td>
文件系统</td><td>

*字符串*</td><td>
返回一个表示文件系统类型的字符串。
</td></tr><tr><td>
标记</td><td>

*int*</td><td>
返回一个代表该驱动器的文件系统的标记值。
</td></tr><tr><td>
免费</td><td>

*Object:***[文件大小](filesize.zh.md)**</td><td>

返回一个 **[文件大小](filesize.zh.md)** 对象，表明驱动器上可用的总空间。
</td></tr><tr><td>
标签</td><td>

*字符串*</td><td>
返回该驱动器的标签。
</td></tr><tr><td>
总计</td><td>

*Object:***[文件大小](filesize.zh.md)**</td><td>

返回一个 **[文件大小](filesize.zh.md)** 对象，表明该驱动器的总大小。
</td></tr><tr><td>
类型</td><td>

*字符串*</td><td>
返回一个表明该驱动器类型的字符串（可移动的、固定的、远程的、cdrom、ramdisk）。
</td></tr></table>