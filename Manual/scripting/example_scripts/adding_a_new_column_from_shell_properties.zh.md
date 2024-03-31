# 使用 Shell 属性添加新列
Directory Opus 为 Windows shell 属性提供脚本支持，这使得脚本可以轻松枚举系统中的属性和检索文件属性。

- 使用 **FSUtil.GetShellPropertyList** 检索属性列表（可以选择匹配通配符模式）。
- 使用 **FSUtil.GetShellProperty** 获取文件的一个或多个属性的值。
- 使用 **Item.ShellProp** 获取项目单个属性的值。

下面是一个示例脚本加载项，该加载项向 Opus 中添加列，用于显示第三方工具添加的 DWG（AutoCAD）文件的 shell 属性值。
`Function OnInit(initData)
initData.name = "DWG 列"
initData.desc = "添加来自 JTB World 扩展的 DWG 列"
initData.copyright = "(c) 2016 jpotter"
initData.version = "1.0"
initData.default_enable = true
initData.min_version = "12.0.8"
Dim props, prop, col
Set props = DOpus.FSUtil.GetShellPropertyList("dwg.*", "r")

for each prop in props
Set col = initData.AddColumn
col.name = prop.raw_name
col.method = "OnDWGColumn"
col.label = prop.display_name
col.justify = "left"
col.autogroup = true
col.userdata = prop.pkey

next
End Function
Function OnDWGColumn(scriptColData)

scriptColData.value = scriptColData.item.shellprop(scriptColData.userdata)

End Function`