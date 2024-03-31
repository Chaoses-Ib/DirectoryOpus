# Help

**Help** 内部命令可用于：

- 显示程序帮助文件
- 显示有关程序的信息（关于对话框）
- 检查 [程序更新](/Manual/additional_functionality/update_checker.zh.md)
- 访问许可证管理器以安装程序证书
- 发送快速电子邮件

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能值</th><th>
说明
</th></tr></thead><tbody><tr><td>

*(无参数)*</td><td>
-</td><td>
-</td><td>

显示程序帮助文件。

*示例:* `Help`
</td></tr><tr><td>
ABOUT</td><td>
/S</td><td>

*(无值)*</td><td>

显示关于对话框，其中显示有关当前程序版本、版权和技术支持联系方式的信息。

*示例:* `Help ABOUT`
</td></tr><tr><td>
CHECKUPDATE</td><td>
/O</td><td>

*(无值)*</td><td>

在线检查 [程序更新](/Manual/additional_functionality/update_checker.zh.md)。

*示例:* `Help CHECKUPDATE`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

执行静默检查更新 - 仅当找到更新时才会显示对话框。

*示例:* `Help CHECKUPDATE=quiet`
</td></tr><tr><td>
CRASHLOGS</td><td>
/S</td><td>

*(无值)*</td><td>

显示 [崩溃日志](/Manual/additional_functionality/crash_logs.zh.md) 对话框，其中显示任何已自动生成的崩溃日志，并允许你将这些日志提交给 GPSoftware 进行分析。
</td></tr><tr><td>
LANG</td><td>
/K</td><td>

*\<语言名称\>*</td><td>

如果存在，则显示指定语言的帮助文件。

*示例:* `Help LANG=deutsch`
</td></tr><tr><td>
LICENCEMANAGER</td><td>
/S</td><td>

*(无值)*</td><td>

显示许可证管理器，你可以在其中查看和管理当前程序许可证，或申请免费求值许可证。

*示例:* `Help LICENCEMANAGER`
</td></tr><tr><td>
NEWEMAIL</td><td>
/S</td><td>

*(无值)*</td><td>

发送快速电子邮件消息。你必须将 Opus 配置为通过 SMTP 发送电子邮件（在配置的 **[杂项/电子邮件](/Manual/preferences/preferences_categories/internet/email.zh.md)** 页面上）才能使此功能正常工作。

*示例:* `Help NEWEMAIL`
</td></tr><tr><td>
REF</td><td>
/K</td><td>

**命令  
dopusrt  
元数据  
状态栏  
通配符  
脚本  
cmd\_*name***</td><td>

提供一个快捷方式，用于显示帮助文件的特定参考部分。例如，你可以定义一个热键，以直接进入 *[通配符](../../wildcard_reference/README.zh.md)* 参考部分。

*示例:* `Help REF=wildcards`  
*示例:* `Help REF=cmd_CreateFolder`
</td></tr><tr><td>
RELEASENOTES</td><td>
/S</td><td>

*(无值)*</td><td>

显示当前版本的发布说明。

*示例:* `Help RELEASENOTES`
</td></tr><tr><td>
THEMETESTER</td><td>
/S</td><td>

*(无值)*</td><td>

打开一个 UI，可用于测试各种标准 Windows 控件在自定义主题中颜色的外观。

*示例:* `Help THEMETESTER`
</td></tr></tbody>
</table>