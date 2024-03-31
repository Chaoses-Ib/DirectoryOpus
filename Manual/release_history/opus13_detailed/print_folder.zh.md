# Directory Opus 13 - 详细发行说明

# 打印 / 导出文件夹列表

- UI 现在拥有预设系统，允许你保存和加载已命名的配置以备将来使用。
- 添加了自动调整列大小的选项。适用于打印和纯文本输出。（针对 CSV 和 TSV 输出隐藏，它们本身自动调整大小。）
- 现在总是使用完整日期，从不使用最近日期的星期几名称。
- 将输出格式（逗号分隔的 CSV、制表符分隔的 TSV、纯文本）和编码选项（ANSI、UTF8、带 BOM 的 UTF8）移动到了主对话框。
- 命令：
  - `Print FOLDER PRESET="My Preset"`
  - `Print FOLDER PRESET="!reset"` -- 使用默认设置打开 UI。
  - `Print FOLDER AUTOSIZECOLUMNS=yes`
  - `Print FOLDER KEYWORDS` -- 对标题使用唯一的列关键字，而不是（不总是唯一的）友好名称。旨在用于将输出交给工具处理。

------------------------------------------------------------------------

下一部分：[拆分 / 合并](/Manual/release_history/opus13_detailed/split_join.zh.md)