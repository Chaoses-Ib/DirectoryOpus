# Play

内部 **Play** 命令用于 [播放](/Manual/additional_functionality/playing_sounds.zh.md) 选定的声音文件。这是一个非常简单的内置实用程序——它不会替代一个专门的播放器。它可能也不支持所有音频格式——从根本上说，只支持 **.wav** 文件，但如果已安装了适合的编解码器，**.mp3** 和其他格式也可行。

**命令参数**：

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
描述
</th></tr></thead><tbody><tr><td>

<nobr>*(无参数)*</nobr></td><td>
-</td><td>
-</td><td>

使用内部 [播放器](/Manual/additional_functionality/playing_sounds.zh.md) 播放当前文件夹中选定的声音文件。

*示例:* `Play`
</td></tr><tr><td>
FILE</td><td>
/M</td><td>

*\<filename\> ...*</td><td>

播放指定的声音文件或文件。这允许你播放特定声音——例如，你可能会将此命令添加到按钮末尾来表明某个功能已完成。在这些情况下，你通常还会想使用 **QUIET** 参数。

记住，如果文件名包含空格，则需要用引号将其括起来。这是 **Play** 命令的默认参数，因此你不必提供 **FILE** 关键字。

*示例:* `Play C:\Data\Sounds\Complete.wav QUIET`
</td></tr><tr><td>
QUIET</td><td>
/S</td><td>

*(无值)*</td><td>

播放指定（或选定）的声音而不显示播放对话框。

*示例:* `Play QUIET`
</td></tr><tr><td>
STOPALL</td><td>
/S</td><td>

*(无值)*</td><td>

停止任何当前在后台播放的声音（根据 `Play QUIET` 命令）。

*示例:* `Play STOPALL`
</td></tr></tbody>
</table>