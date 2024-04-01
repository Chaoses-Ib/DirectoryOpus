# Directory Opus 13 - 详细发行说明

# 查找文件

- 常规：
  - 界面重新设计。
  - 删除了“简单/高级”标签页控件，用面板顶部的“高级模式”复选框代替。
  - 用顶部的菜单替换了“重置”按钮。
  - 您现在可以保存自己的默认设置并重置为默认设置，以及恢复出厂默认设置。
  - 在“排除”字段中，单击齿轮按钮可获取排除隐藏和系统文件夹的选项。
  - “禁止 UAC 提示”选项：在尝试查找文件或文件夹时出现访问被拒绝错误时，将予以跳过，而不是提示提升权限。
  - 如果搜索结束而未找到任何结果，文件列表顶部会有一条消息提示。
  - 添加了“忽略变音符号”选项。
  - 名称、描述、包含/文本、标签、目标等字段现在具有全套匹配选项（大小写/部分/任一单词/忽略变音符号/通配符/正则表达式）。
  - “索引搜索”字段允许您指定一个索引搜索查询，然后通过其余的“查找”参数馈送结果。
    - 允许您使用快速的索引搜索来缩小所考虑的文件范围，然后应用更高级的条件对其进一步过滤。
    - 适用于 Windows Search、Everything 和 Global Everything。
  - “另存为存储的查询”命令现在可以在使用“查找”对话框生成的集合中使用。
    - “查找”面板的配置将作为集合的一部分存储。
    - 创建一个文件集合，每当您导航到它和/或刷新时，它都将自动重新运行“查找”。
  - 存储的查询现在可以与 Everything 和 Opus Find 一起使用。
    - 使用 Opus Find 的存储的查询还可以通过在前面加 & 字符或通过在后面加 `=` 提供文本过滤器（见下文）定义。
  - “显示结果”现在允许您将结果发送到左侧或右侧的新标签页（不仅限于源或目标）。
  - 现在可以通过右键单击实用程序面板的“收缩”按钮（该按钮紧邻关闭按钮）找到“自动收缩”选项。
  - “查找结果”现在拥有自己的文件夹格式，不同于更通用的“集合”格式。
- 预设：
  - 您现在可以配置“查找”面板并将所有内容另存为一个预设。
  - 预设可以加载到“查找”面板中，还可以与“查找”命令同时使用。
  - 在文件窗口中，默认的工具菜单有一个“查找预设”子菜单，其中列出了所有已保存的预设。选择一个预设会立即运行已保存的搜索，而无需打开“查找”面板。
  - 工具菜单的“预设”子菜单还包括几个使用硬编码过滤器搜索当前目录下的示例：
    - 查找空文件夹 -- 查找完全为空的文件夹。
    - 查找零字节文件夹 -- 查找仅包含空文件或其它空文件夹的文件夹。
- 排除文件夹：
  - 新的“排除”字段允许您排除文件和文件夹。默认情况下，排除回收站和系统卷信息文件夹。支持多个路径、通配符和正则表达式。语法选项：
    - `regex:xxxx` - 正则表达式必须匹配才能排除一个项。
    - `wild:xxxx` - 标准通配符必须匹配才能排除一个项。

(如果使用了 `*?|` 字符，通配符将自动检测到，而不需要 `wild:` 前缀。其它作为有效路径字符的通配符字符需要一个显式的 `wild:` 前缀才能被解释为通配符。）

        * <ib:inline-code><code>C:\Temp</code></ib:inline-code> - 完全限定路径；匹配路径本身和内容。
        * <ib:inline-code><code>C:\Temp\*</code></ib:inline-code> - 完全限定路径，带有通配符；仅匹配内容。
        * <ib:inline-code><code>Name</code></ib:inline-code> - 非通配符，非完全限定；匹配自身和内容。变为： <ib:inline-code><code>*\Name(|\*)</code></ib:inline-code>\
        * <ib:inline-code><code>Name\*</code></ib:inline-code> - 具有尾部 <ib:inline-code><code>*</code></ib:inline-code> 的非通配符名称；仅匹配内容。变为： <ib:inline-code><code>*\Name\*</code></ib:inline-code>\
        * <ib:inline-code><code>Name*</code></ib:inline-code> - 通配符名称；匹配自身和内容。变为： <ib:inline-code><code>*\Name*</code></ib:inline-code>\
    * 简单模式：
      * 可以选择大小单位（千字节/兆字节/千兆字节）。
      * 文本（内容搜索）字段有“假设 UTF8”选项。
      * 增强“任意单词”匹配：
        * 带有前缀 <ib:inline-code><code>+</code></ib:inline-code> 的单词必须匹配（按任意顺序）。
        * 带有前缀 <ib:inline-code><code>-</code></ib:inline-code> 的单词不能匹配。
        * 没有 <ib:inline-code><code>+</code></ib:inline-code> 或 <ib:inline-code><code>-</code></ib:inline-code> 的单词可以匹配，并且只要指定了一个，就必须至少匹配一个。
        * 如果指定了一个或多个文件扩展名，则将排除所有文件夹，并且文件必须匹配其中一个扩展名（除了指定的所有其它单词之外）。
        * 支持部分文件扩展名。“.jp”还将匹配“.jpg”。
        * 可以通过使用显式通配符禁止部分扩展名匹配：“*.jp”将仅匹配“.jp”，而不会匹配“.jpg”。
        * 所有其它包含通配符的单词都将被视为开启了部分匹配，无论是否实际开启。
        * //示例：// 在关闭的部分匹配的情况下，“dog c?t” - “dog”将仅匹配“dog”（因为没有通配符字符），但“c?t”将匹配“cat”和“city”。
        * 请记住，上述规则仅适用于“任意单词”模式。当模式未开启时，无法使用这些规则。
        * 这些规则还适用于“过滤栏”处于“任意单词”模式时。
    * 高级模式：
      * 添加了“名称词干”过滤条款。根据没有扩展名的文件名进行匹配。
      * 添加了“文件夹内容”过滤条款。允许您搜索包含与指定条件相符的文件的文件夹。
      * 过滤器现在可以通过文本形式和 GUI 构建器进行编辑：
        * 您可以在模式之间随时进行切换（前提是文本有效）。
        * 文本过滤器定义可用于独立按钮中，而无需将过滤器保存到全局列表并通过名称引用它。
        * 文本过滤器还可以由脚本代码生成或修改，从而允许脚本更改过滤器中的各个参数。
        * 文本过滤器也更容易与他人共享（例如，在支持论坛上）。
      * 文本过滤器还可以在求值器中运行代码：
        * 完全绕过过滤系统，并对每个文件调用求值器。
        * 在过滤器定义前面加上前缀 <ib:inline-code><code>=</code></ib:inline-code>。
        * 如果过滤器文本控件中包含求值器代码，则无法将其切换出文本模式。求值器代码无法转换成传统的过滤器定义。
        * 代码可以使用与求值器列相同的变量（如名称、picwidth 等）（请参阅发行说明中的其它地方）。
        * 代码应该返回 true 表示匹配，返回 false 表示跳过文件。
        * //示例 1：// <ib:inline-code><code>=ext(name) == ".jpg" && picwidth >= 1920</code></ib:inline-code>\
* 还支持子文件夹递归。当求值器查询是否应该进入文件夹时，<ib:inline-code><code>subfolder</code></ib:inline-code> 变量将为 true。返回 true 以进入，返回 false 以跳过。默认搜索所有子文件夹。
        * //示例 2:// <ib:inline-code><code>=subfolder ? (left(name, 1) == "a") : (ext(name) == ".jpg")</code></ib:inline-code> -- 在名称以“a”开头的文件夹下查找 JPG 文件。
    * 命令：
      * <ib:inline-code><code>Find FILTERDEF</code></ib:inline-code> -- 允许以文本形式传递过滤定义。还允许采用求值器代码。请参见上述“高级模式”。
      * <ib:inline-code><code>Find HERE</code></ib:inline-code> -- 指定查找操作应从当前文件夹开始工作。
      * <ib:inline-code><code>Find UAC=yes</code></ib:inline-code> -- 启用在需要提升权限才能查看其内部的文件夹中进行搜索。 
      * <ib:inline-code><code>Find PRESET="My Preset"</code></ib:inline-code> -- 立即将指定的预设应用于运行。
      * <ib:inline-code><code>Find PRESET="My Preset" NOAUTORUN</code></ib:inline-code> -- 使用已加载的预设打开查找面板。
      * <ib:inline-code><code>Find PRESET=!list</code></ib:inline-code> -- 生成查找预设列表。由“工具”>“查找预设”默认菜单使用。还可以指定“faves”、“nofaves”或“nogroups”。
      * <ib:inline-code><code>Set Utility=Find PRESET="My Preset"</code></ib:inline-code> -- 使用预设打开查找面板的另一种方式。
      * <ib:inline-code><code>Set UTILITY=Find,Toggle</code></ib:inline-code> -- 无论其处于“简单”还是“高级”状态，旧命令现在都将切换查找面板。重新打开时，面板将在上次关闭时所处的模式下打开。
      * <ib:inline-code><code>Set UTILITY=FindSimple,Toggle</code></ib:inline-code> -- 显式切换到“简单”模式下的查找面板。
      * <ib:inline-code><code>Set UTILITY=FindAdvanced,Toggle</code></ib:inline-code> -- 显式切换到“高级”模式下的查找面板。
      * <ib:inline-code><code>Go NEW=FindPanel</code></ib:inline-code> -- 类似地，在上次使用的“简单”或“高级”模式下打开新窗口的查找面板。
      * <ib:inline-code><code>Go NEW=FindSimple</code></ib:inline-code> -- 显式使用“简单”模式在新窗口中打开查找面板。
      * <ib:inline-code><code>Go NEW=FindAdvanced</code></ib:inline-code> -- 显式使用“高级”模式在新窗口中打开查找面板。
      * <ib:inline-code><code>Find SHOWRESULTS=tab,left</code></ib:inline-code> -- 将结果发送到左侧（或右侧）的新标签页上。
      * 查找命令的其它新参数：EXCLUDEHIDDEN、EXCLUDESYSTEM、IGNOREDIACRITICS、REGEXP、CASE、CONTREGEXP、CONTIGNOREDIACRITICS、CONTNOPARTIAL、CONTUTF8、QUERYENGINE。
      * <ib:inline-code><code>DOpusRT.exe /col /engine=everything setquery...</code></ib:inline-code> -- 请参见主手册中的 //外部操作文件集合//。