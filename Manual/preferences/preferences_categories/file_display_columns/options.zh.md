# 选项

包含与文件列表中的列相关的通用选项。

- **在文件列表分组时自动添加“组”列**：在文件列表被 [分组](/Manual/basic_concepts/sorting_and_grouping/README.zh.md) 时自动添加 *组* 列。该列阻止组头出现在组之间，而是使用水平空间代替垂直空间来指示每个组的开始和结束位置。如果关闭此选项，你仍可显式添加该列，这使你能够在不同情况下使用两种分组样式。
- **通过单击“评级”列内的某个位置来编辑评级**：如果 *评级* 列显示且此选项开启，则你可以直接单击评级星来设置或更改文件的评级。否则，你可以通过 [元数据](/Manual/file_operations/editing_metadata/README.zh.md) 系统设置评级。
- **在空列中显示破折号**：如果某列没有数据，则将显示两条破折号，而不是一个空格。
- **显示友好日期**：允许你选择两种显示“友好”日期的不同选项：
  - **一周内的日期名称**：如果某个文件的时间戳在过去一周内，则会显示星期几（或 *今天* 或 *昨天*）而不是实际日期。
  - **仅今天**：显示今天修改的文件的 *今天*，否则显示正常日期。
- **在 *修改* 和 *创建* 日期和时间列后面显示图形**：在日期列后面显示条形图，指示文件与文件夹中最旧文件的相对时间戳。这些图形与在打开单独的 *修改（相对）* 和 *创建（相对）* 列时显示的图形相同（除了它们占用较少空间，因为它们与另一列共享空间之外）。
- **在大小列后面显示图形**：在 *大小* 列后面显示条形图，指示文件与文件夹中最旧文件之间的相对大小。此图形与在打开单独的 *相对大小* 列时显示的图形相同。
- **在时间列中显示秒**：通过此选项的打开，Opus将在带有此选项的时间列中显示秒（*hh:mm:ss*）——否则，它只会使用小时和分钟显示时间。如果显示秒，你还可以打开 **显示毫秒** 选项，以通过毫秒级的精度显示时间戳（取决于基础文件系统）。
- **为云文件夹显示扩展同步属性**：对于 OneDrive 等云储存文件夹，此选项会使 Opus 从 Windows 请求额外的同步状态属性。在此选项关闭的情况下，只会报告在线/离线状态；在此选项打开的情况下，还可以显示“同步中”等其他状态。