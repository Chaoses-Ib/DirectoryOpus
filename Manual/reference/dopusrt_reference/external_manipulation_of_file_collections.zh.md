# 文件集合外部操作

**[DOpusRT]()** 工具可在 Opus 外部用以操作 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)。

此功能可使用 **dopusrt.exe /col** 命令访问，在 **/col** 之后，你必须提供 *集合命令* 和该集合命令的适当参数。

与大多数命令行工具相同，如果路径或其它参数包含空格，你必须在周围“加上引号”。

<table>
<thead><tr><th>
命令</th><th>
参数</th><th>
描述
</th></tr></thead><tbody><tr><td>

**add**</td><td>

*\[\<flags\>\] \<coll-name\> \<item\> \[\<item\> ...\]*</td><td>

**向命名集合中添加一个或多个项目**。  
*\<flags\>* 是一个或多个可选标志，参阅下方获取这些标志的列表。如果标志的值包含空格，那么整个标志和值都必须用引号括起来。  
*\<coll-name\>* 是集合的名称（如果添加到子集合中，那么必须提供完整路径）。  
*\<item\>* 是要添加的项目或项目的完整路径和文件名。如果路径或文件名包含空格，那么它必须用引号括起来。文件名还可以包含 [标准通配符](../wildcard_reference/pattern_matching_syntax.zh.md) 以一次性在文件夹中添加多个项目。

示例：  
**dopusrt.exe /col add "Photos/Holidays" /mypictures/Hawaii/\*.jpg**
</td></tr><tr><td>
</td><td>

\[**/dupeid***=\<id\>*\]</td><td>
允许你通过提供要将项目分配到的组的数字 ID，使用“重复文件”样式集合。添加的具有相同重复 ID 的项目将在按重复项分组的文件列表中一同显示。
</td></tr><tr><td>
</td><td>

\[**/name**\]</td><td>

允许你向重复组分配自己的名称。这必须与 **/dupeid** 标志配合使用。例如，  
**dopusrt.exe /col add /dupeid=1 /name "My Dupes" "Group number 1"**
</td></tr><tr><td>

**clear**</td><td>

\[**/full**\] *\<coll-name\>*</td><td>

**清除命名集合中的内容**。  
*\<coll-name\>* 是集合的名称（如果清除子集合，那么必须提供完整路径）。默认情况下，清除集合时不会删除子集合，但你可以指定 **/full** 标志来执行此操作。

示例：  
**dopusrt.exe /col clear "Find Results"  
dopusrt.exe /col clear /full "Marked Pictures"**
</td></tr><tr><td>

**create**</td><td>

*\[\<flags\>\] \<coll-name\>*</td><td>

**创建新集合**。  
*\<flags\>* 是一个或多个可选标志，参阅下方获取这些标志的列表。如果标志的值包含空格，那么整个标志和值都必须用引号括起来。  
*\<coll-name\>* 是要创建的集合的名称。要创建子集合，请指定集合的完整路径。集合名称必须在任何可选标志之后。

示例：  
**dopusrt.exe /col create "/desc:My Photos" Photos**
</td></tr><tr><td>
</td><td>

**/noclear**</td><td>
如果集合已存在，则不清除它。
</td></tr><tr><td>
</td><td>

**/icon:***\<file\>*</td><td>
为新集合指定自定义图标。
</td></tr><tr><td>
</td><td>

**/desc:***\<desc\>*</td><td>
为新集合指定描述。
</td></tr><tr><td>
</td><td>
/dupes</td><td>
将该集合标记为“重复文件”集合。
</td></tr><tr><td>
</td><td>

**/query**</td><td>

将新集合创建为 [存储的查询](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.zh.md)。
</td></tr><tr><td>

**delete**</td><td>

*\<coll-name\>*</td><td>

**删除命名集合**。  
*\<coll-name\>* 是要删除的集合的名称。如果删除子集合，那么必须提供完整路径。

示例：  
**dopusrt.exe /col delete "Photos/Holidays/2010"**
</td></tr><tr><td>

**export**</td><td>

*\[\<flags\>\] \<coll-name\> \<export-file\>*</td><td>

**将集合的内容导出到文本文件**。  
*\<flags\>* 是一个或多个可选标志，参阅下方获取这些标志的列表。  
*\<coll-name\>* 是要导出的集合的名称。  
*\<export-file\>* 是要导出到的完整路径和文件，如果其中包含空格，那么必须加引号。

如果未指定编码类型（使用可选标志），如果任何文件名需要 Unicode，那么该文件将被编码为 UTF16-LE，否则将被编码为当前的 ANSI 代码页。

示例：  
**dopusrt.exe /col export /utf8 "Find Results" D:\Results.txt**
</td></tr><tr><td>
</td><td>

**/append**</td><td>

如果导出文件已存在，那么追加到其中，否则将覆盖它。
</td></tr><tr><td>
</td><td>

**/utf16be**</td><td>
强制编码为 UTF16-BE。
</td></tr><tr><td>
</td><td>

**/utf16le**</td><td>
强制编码为 UTF16-LE。
</td></tr><tr><td>
</td><td>

**/utf8**</td><td>
强制编码为 UTF8。
</td></tr><tr><td>
</td><td>

**/ansi**</td><td>
强制编码为当前的 ANSI 代码页。
</td></tr><tr><td>
</td><td>

**/cp:***\<codepage\>*</td><td>
指定代码页。
</td></tr><tr><td>

**import**</td><td>

*\[\<flags\>\] \<coll-name\> \<import-file\>*</td><td>

**将文本文件的内容导入到集合中**。  
*\<flags\>* 是一个或多个可选标志，参阅下方获取这些标志的列表。  
*\<coll-name\>* 是要导入到的集合的名称。  
*\<import-file\>* 是要从中导入的文件。导入文件应每行包含一个文件或文件夹名称。  
  
你可以通过在导入文件中的每行的前面加上 **\#***\<id\>*\*\* 来导入“重复文件”样式集合，****以指定数字重复 ID。具有相同重复 ID 的项目将在按重复项分组设置的文件列表中分组到一起。  
  
你还可以通过包含以下格式的行来为重复组分配名称：**group:***\<id\>***,***\<name\>***.**  
  
如果导入文件中带 BOM，那么此 BOM 将用于确定编码类型。  
  
示例：  
**dopusrt.exe /col import /ansi "My Photos" /desktop/photos.txt**
</td></tr><tr><td>
</td><td>

**/clear**</td><td>
在导入新项目前清除集合。
</td></tr><tr><td>
</td><td>

**/create**</td><td>
如果集合尚不存在，则创建它。
</td></tr><tr><td>
</td><td>

**/nocheck**</td><td>
在将导入文件中的项目导入到集合中之前，不要检查这些项目是否存在。
</td></tr><tr><td>
</td><td>

**/relative:*\<path\>***</td><td>

指定列表中各行的相对路径，如果文件不包含完全限定的路径。如果没有指定，则假定路径相对于包含列表的相同文件夹。  
指定 **/relative:none** 如果做点特殊事情，你希望按原样导入行，即使它们未完全限定，在这种情况下，它不能与 **/nocheck** 结合使用。  
如果路径包含空格，那么整个参数都应加引号。  
  
示例：  
**dopusrt.exe /col import "/relative:C:\My Music" "Jazz" C:\Trane.m3u**
</td></tr><tr><td>
</td><td>

**/utf16be**</td><td>
如果没有 BOM，则假定为 UTF16-BE。
</td></tr><tr><td>
</td><td>

**/utf16le**</td><td>
如果没有 BOM，则假定为 UTF16-LE。
</td></tr><tr><td>
</td><td>

**/utf8**</td><td>
如果无 BOM 则假定为 UTF8。
</td></tr><tr><td>
</td><td>

**/ansi**</td><td>
强制转换自当前的 ANSI 代码页。
</td></tr><tr><td>
</td><td>

**/cp:***\<codepage\>*</td><td>
强制转换自特定代码页。
</td></tr><tr><td>

**remove**</td><td>

*\<coll-name\> \<item\> \[\<item\> ...\]*</td><td>

**从集合中移除项目**。  
*\<coll-name\>* 是集合的名称。  
*\<item\>* 是移除项目或项目的名称。可以给出项目在磁盘上的完整路径，或其在集合内的名称。如果路径或文件名包含空格，则必须用引号引起来。文件名还可以包含 [标准通配符](../wildcard_reference/pattern_matching_syntax.zh.md)，以便一次移除多个项目。  
  
示例：  
**dopusrt.exe /col remove "Find Results" \*.txt**
</td></tr><tr><td>

**rename**</td><td>

*\<old-coll-name\> \<new-coll-name\>*</td><td>

**重命名集合**。  
*\<old-coll-name\>* 是集合的现有名称。  
*\<new-coll-name\>* 是集合的新名称。  
  
示例：  
**dopusrt.exe /col rename "Find Results" "Saved Results 1"**
</td></tr><tr><td>

**runquery**</td><td>

*\<coll-name\>*</td><td>

**运行（刷新）[存储的查询](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.zh.md)**。  
*\<coll-name\>* 是存储的查询集合的名称。  
  
示例：  
**dopusrt.exe /col runquery "Stored Queries\Backup Files"**
</td></tr><tr><td>

**setdesc**</td><td>

*\<coll-name\> \<desc\>*</td><td>

**设置集合的说明**。  
**\<coll-name\>** 是集合的名称。  
**\<desc\>** 是集合的新说明（或为空以清除说明）。  
  
示例：  
**dopusrt.exe /col setdesc "Saved Results 1" "Music before 1990"**
</td></tr><tr><td>

**seticon**</td><td>

*\<coll-name\> \<icon-file\>*</td><td>

**为集合设置自定义图标**。  
*\<coll-name\>* 是集合的名称。  
*\<icon-file\>* 要使用的图标文件的完整路径和文件名。  
  
图标可以来自 .ico 或 .icl 文件，或 .exe 或 .dll 文件。对于包含多个图标的文件，请将所需图标索引追加到文件名后。  
  
示例：  
**dopusrt.exe /col seticon "Pics" C:\Tools\viewer.exe,2**
</td></tr><tr><td>

**setpaths**</td><td>

*\[\<flags\>\] \<coll-name\> \<path\> \[\<path\> ...\]*</td><td>

**设置[存储的查询](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.zh.md) 的搜索路径或路径**。  
*\<flags\>* 为可选标记，请参阅下文了解这些标记的列表。  
*\<coll-name\>* 是存储的查询集合的名称。  
*\<path\>* 是要添加到查询的路径或路径。如果路径包含空格，则必须用引号引起来。  
  
示例：  
**dopusrt.exe /col setpaths "Backup Files" X:\Backup**
</td></tr><tr><td>
</td><td>

**/add**</td><td>
将路径添加到查询，不要移除任何现有的路径。
</td></tr><tr><td>

**setquery**</td><td>

*\[\<flags\>\] \<coll-name\> \<query\>*</td><td>

**设置[存储的查询](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.zh.md) 的查询字符串**。  
\<flags\> 是一个或多个可选标记，请参阅下文了解这些标记的列表。  
\<coll-name\> 是存储的查询集合的名称。  
\<query\> 是查询字符串，采用 [高级查询语法](https://learn.microsoft.com/en-us/windows/win32/lwef/-search-2x-wds-aqsreference)。  
  
命名集合必须已创建为存储的查询（例如，使用 **dopusrt.exe /col create /query** 命令）。

结合使用时，你可以使用 **/engine** 参数设置查询使用的搜索引擎。默认值为 Windows 搜索；其它选项为 **everything**、**everythingglobal** 和 **opus**。

示例：  
**dopusrt.exe /col setquery "Backup Files" name:\*.bak /engine=everything**
</td></tr><tr><td>
</td><td>

**/auto**</td><td>

将存储的查询设置为 “自动刷新” 模式 - 加载查询时会运行/刷新查询。
</td></tr><tr><td>
</td><td>

**/noauto**</td><td>
将存储的查询设置为不自动刷新。
</td></tr></tbody>
</table>