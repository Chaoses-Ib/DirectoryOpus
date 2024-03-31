# 外部控制代码

外部控制代码用于传递信息，例如将所选文件的文件名传递给外部程序。例如，命令 **notepad.exe {f}** 将启动记事本，并将第一个所选文件的文件名作为其命令行的一个参数传递。

外部控制代码（尽管名称如此）也可以与内部命令一起使用。例如，命令 **CreateFolder {date\|yyyyMMdd}** 将创建一个新文件夹，并自动以当前日期命名。

大多数控制代码既有短形式，也有长形式。短形式需要输入的内容更少，并生成一个更小的函数定义，而长形式更具描述性，可能使函数更易于理解。请注意，与内部命令的参数不同，外部控制代码是大小写敏感的。

请参阅有关 [传递文件给外部程序](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.zh.md) 的页面，了解更多有关外部控制代码的信息。

更多信息：

[传递文件名代码](/Manual/reference/command_reference/external_control_codes/codes_for_passing_filenames.zh.md)  
[传递路径代码](/Manual/reference/command_reference/external_control_codes/codes_for_passing_paths.zh.md)  
[显示对话框代码](/Manual/reference/command_reference/external_control_codes/codes_to_display_dialogs.zh.md)  
[日期和时间代码](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.zh.md)  
[剪贴板和变量代码](/Manual/reference/command_reference/external_control_codes/codes_for_clipboard_and_variables.zh.md)