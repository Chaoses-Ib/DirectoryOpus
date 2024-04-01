当查询文件夹的 [对](/Manual/preferences/preferences_categories/frequently_used_paths/paired_folders.zh.md)时，**[FSUtil](fsutil.zh.md).GetFolderPair** 方法会返回 **PairedFolder** 对象。

务必在查询任何其它属性之前检查 **valid** 属性；如果 **valid** 为 **False**，则表示该文件夹没有对，因此不会存在其它属性。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
dual</td><td>

*bool*</td><td>

如果这对文件夹启用了 *默认双栏文件夹* 选项，则返回 **True**。
</td></tr><tr><td>
dualnavlock</td><td>

*bool*</td><td>

如果这对文件夹启用了 *默认导航锁定目标* 选项，则返回 **True**。
</td></tr><tr><td>
ifnonexistent</td><td>

*string*</td><td>

返回一个字符串，表明 *如果不存在* 选项的设置。有效值为 **gotoparent**、**ignorepair** 和 **useanyway**。
</td></tr><tr><td>
navlock</td><td>

*bool*</td><td>

如果这对文件夹启用了 *自动启用导航锁定* 选项，则返回 **True**。
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个 **[path](path.zh.md)** 对象，它提供配对的文件夹。
</td></tr><tr><td>
primaryonleft</td><td>

*bool*</td><td>

如果启用了 *始终在左侧/顶部显示主文件夹* 选项，则返回 **True**。
</td></tr><tr><td>
sync</td><td>

*bool*</td><td>

如果为这对文件夹启用了 *默认同步目标*，则返回 **True**。
</td></tr><tr><td>
subfolders</td><td>

*bool*</td><td>

如果启用了 *将设置应用到所有子文件夹* 选项，则返回 **True**。
</td></tr><tr><td>
valid</td><td>

*bool*</td><td>

如果配对的文件夹有效，则返回 **True**。
</td></tr></tbody>
</table>