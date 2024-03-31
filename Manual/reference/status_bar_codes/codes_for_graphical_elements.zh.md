# 图形元素代码

以下代码用于在状态栏中显示各种图形元素。有的（例如图标的 {i} 代码）纯属装饰目的，有的则有更多功能用途。

<table>
<thead><tr><th>
代码</th><th>
说明
</th></tr></thead><tbody><tr><td>

{fl}  
{gfl}</td><td>

**格式锁定控件**

显示格式锁定图标（![](/Manual/images/media/format_lock.png)）。此图标表示 [格式锁定](/Manual/basic_concepts/folder_options/locking_the_format.zh.md) 的当前状态，单击可切换锁定状态。将鼠标悬停在图标上可显示工具提示，指示 [当前文件夹格式的来源](/Manual/basic_concepts/folder_options/identifying_the_current_format.zh.md)。

**{gfl}** 会显示灰色图标，但行为相同。
</td></tr><tr><td>

{i:dir}  
{i:file}  
\<nobr\>{i:*\<ext\>*}\</nobr\>  
\<nobr\>{i:*\<file\>*}\</nobr\></td><td>

**图标**

让你在状态栏中显示任意图标。例如，你可以显示通用文件夹图标，而不再显示状态栏上显示为 *Folders: xxx / yyy* 的文本。

    {{:media:status_bar_icons.png?nolink|}}
    {i:dir} {sd}/{td} {i:file} {sf}/{tf} {i:.mp3} {smp3}/{tmp3}

出于节省状态栏空间或纯粹的装饰原因，你可能需要这么做。

你可以指定通用文件夹图标（`{i:dir}`）、通用文件图标（`{i:file}`）、或特定文件类型的图标（如 MP3 文件图标`{i:.mp3}`）。

你还可以提供图标的路径和文件名，使用你自己的自定义图标或图像。例如，`{i:/mypictures/myicon.png}`。图像文件会被自动缩小以适应状态栏。
</td></tr><tr><td>
{bg}</td><td>

**条形图**

条形图可用于以百分比的形式直观表示一个值。条形图的默认行为是在当前驱动器上显示磁盘空间使用率的百分比，但通过使用 {bg} 代码的各种参数，你可以配置条形图以将任何其他状态栏值表示为另一个值或绝对值的百分比。

有关配置条形图的详细信息，请参见有关 [条形图](bar_graphs_and_percentages.zh.md) 的页面。
</td></tr></tbody>
</table>