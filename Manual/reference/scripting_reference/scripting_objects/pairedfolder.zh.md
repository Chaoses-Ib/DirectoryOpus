# PairedFolder

**PairedFolder** 对象由 **[FSUtil](fsutil.zh.md).GetFolderPair** 方法返回，用于查询文件夹的 [配对](/Manual/preferences/preferences_categories/frequently_used_paths/paired_folders.zh.md)。

请确保在查询任何其它属性之前检查 **valid** 属性 - 如果 **valid** 为 **False**，则表示该文件夹没有配对，因此其它任何属性都不存在。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
dual</td><td>

*bool*</td><td>

如果配对的 *默认双栏文件夹* 选项开启，则返回 **True**。
</td></tr><tr><td>
dualnavlock</td><td>

*bool*</td><td>

如果配对的 *默认导航锁定目标* 选项开启，则返回 **True**。
</td></tr><tr><td>
ifnonexistent</td><td>

*string*</td><td>

返回一个字符串，指示 *如果不存在* 选项的设置。有效值为 **gotoparent**、**ignorepair** 和 **useanyway**。
</td></tr><tr><td>
navlock</td><td>

*bool*</td><td>

如果配对的 *自动开启导航锁定* 选项开启，则返回 **True**。
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个 **[path](path.zh.md)** 对象，提供配对的文件夹。
</td></tr><tr><td>
primaryonleft</td><td>

*bool*</td><td>

如果 *始终将主文件夹显示在左侧/顶部* 选项开启，则返回 **True**。
</td></tr><tr><td>
sync</td><td>

*bool*</td><td>

如果配对的 *默认同步目标* 选项开启，则返回 **True**。
</td></tr><tr><td>
subfolders</td><td>

*bool*</td><td>

如果 *将设置应用于所有子文件夹* 选项开启，则返回 **True**。
</td></tr><tr><td>
valid</td><td>

*bool*</td><td>

如果配对的文件夹有效，则返回 **True**。
</td></tr></tbody>
</table>