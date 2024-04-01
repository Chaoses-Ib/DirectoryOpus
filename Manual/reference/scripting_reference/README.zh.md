# 脚本参考

Directory Opus 脚本接口是围绕 ActiveX 构建的。它的优点在于 Opus 脚本是 *与语言无关的* - 您可以使用机器上安装的任何 ActiveX 脚本语言。Windows 附带 **VBScript** 和 **JScript** 解释器，而且您还可以从第三方提供程序（例如 Perlscript、Python 等）添加其它语言。

脚本接口以多个 *对象* 和 *事件* 的形式呈现。

- *[对象](/Manual/reference/scripting_reference/scripting_objects/README.zh.md)* 由脚本创建，或由 Opus 提供给脚本，并且已定义允许您与 Opus 交互的方法和属性。
- *[事件](/Manual/reference/scripting_reference/scripting_events/README.zh.md)* 是由脚本提供的函数，Opus 会在特定条件下调用此函数。例如，在更改查看器中的文件夹之前，会触发 *OnBeforeFolderChange* 事件。