# Adding a new Column from Shell Properties

Directory Opus has script support for Windows shell properties, making it easy for a script to enumerate properties in the system and retrieve the properties for a file.

- Use **FSUtil.GetShellPropertyList** to retrieve a list of properties (optionally matching a wildcard pattern).
- Use **FSUtil.GetShellProperty** to get the value of one or more properties for a file.
- Use **Item.ShellProp** to get the value of a single property for the item.

Below is an example script add-in that adds columns to Opus that show the value of shell properties for DWG (AutoCAD) files added by a third party tool.  
`Function OnInit(initData)
initData.name = "DWG Columns"
initData.desc = "Adds DWG Columns from the JTB World extension"
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
