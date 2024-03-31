# Directory Opus 13 - 详细发行说明

# 同步

- 类似于“查找”面板（有关详细信息，请参阅上面）：
  - 改进的 UI。
  - 重置菜单。
  - 预设。
  - 按路径、通配符或隐藏/系统属性排除文件夹。
  - 将“自动缩小”移到“缩小”按钮的上下文菜单。
- 其他内容：
  - 在比较大量文件时的性能改进。
  - 新选项，“同步所有内容（包括隐藏文件）”：打开“显示所有内容”模式，以确保在同步时不会因过滤器而遗漏任何内容。
  - 新的“大小（较小）”和“大小（较大）”比较模式。
  - 命令：
    - `查找 SYNC`——触发同步比较，而不打开面板：
      - `复制 SYNC`——在比较后执行实际数据同步。
      - `设置 CLEARSYNC`——完成时退出“同步模式”。
    - `查找 SYNC RUNINPANEL`允许单个命令配置面板，然后开始操作。
    - `查找 SYNC COMPARE=smaller`
    - `查找 SYNC COMPARE=larger`
    - `查找 SYNC PRESET="My Preset" NOAUTORUN`——类似于“查找”面板。使用 !list 作为预设名称来生成预设列表。
    - `设置实用工具=Sync PRESET="My Preset"`——类似于“查找”面板。

------------------------------------------------------------------------

下一部分：[其他实用工具面板](/Manual/release_history/opus13_detailed/other_util.zh.md)