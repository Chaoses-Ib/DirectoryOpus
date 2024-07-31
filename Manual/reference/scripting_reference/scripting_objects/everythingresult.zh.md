# EverythingResult

表示 Everything 查询结果集中返回的单个项目。**[EverythingInterface](everythinginterface.zh.md).Query** 方法调用返回这些对象的 [Vector](vector.zh.md)。

当你向 Everything 发送查询时，你可以指定返回哪些信息。只有你请求的信息才会出现在结果项中，例如，如果你想要文件大小，你必须在发送查询时请求它。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

access  
access_utc</td><td>

*date*</td><td>
返回结果项的最后访问日期（本地时间和 UTC 时间）。必须在查询中请求最后访问日期。
</td></tr><tr><td>

create  
create_utc</td><td>

*date*</td><td>
返回结果项的创建日期（本地时间和 UTC 时间）。必须在查询中请求创建日期。
</td></tr><tr><td>

daterecentlychanged  
daterecentlychanged_utc</td><td>

*date*</td><td>
返回结果项的最近更改日期（本地时间和 UTC 时间）。必须在查询中请求此值。
</td></tr><tr><td>

daterun  
daterun_utc</td><td>

*date*</td><td>
返回结果项的最后运行日期（本地时间和 UTC 时间）。必须在查询中请求此值。
</td></tr><tr><td>
filelist_filename</td><td>

*string*</td><td>
返回结果项的文件列表文件名。必须在查询中请求此值。
</td></tr><tr><td>
fullpath</td><td>

*object*:**[Path](path.zh.md)**</td><td>
返回结果项的完整路径和名称。必须在查询中请求完整路径和名称（或分别请求路径和名称）。
</td></tr><tr><td>
highlighted_fullpath</td><td>

*string*</td><td>
返回结果项的突出显示的完整路径和名称，如果在查询中请求此值。
</td></tr><tr><td>
highlighted_name</td><td>

*string*</td><td>
返回结果项的突出显示的名称，如果在查询中请求此值。
</td></tr><tr><td>
highlighted_path</td><td>

*string*</td><td>
返回结果项的突出显示的路径，如果在查询中请求此值。
</td></tr><tr><td>
name</td><td>

*string*</td><td>
返回结果项的名称。必须在查询中请求名称（或完整路径和名称）。
</td></tr><tr><td>
path</td><td>

*object*:**[Path](path.zh.md)**</td><td>
返回结果项的路径。必须在查询中请求路径（或完整路径和名称）。
</td></tr><tr><td>
runcount</td><td>

*int*</td><td>
返回项目的运行次数，如果在查询中请求此值。
</td></tr><tr><td>
size</td><td>

*object*:**[FileSize](filesize.zh.md)**</td><td>
返回结果项的大小，如果在查询中请求此值。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
GetItem</td><td>

*none*</td><td>

*object*:**[Item](item.zh.md)**</td><td>

构造一个表示此结果的 Opus [Item](item.zh.md) 对象。为了使此函数正常工作，必须在结果集中返回完整路径和文件名。
</td></tr></tbody>
</table>