# 资源

你可能已经注意到 [脚本对话框](script_dialogs/README.zh.md) 部分中的脚本可以具有与其关联的“资源”。这是一个提供资源给脚本的 XML 格式化数据，但实际上它并不构成脚本代码的一部分。

### 定义资源

有两种方式可以定义脚本：

- 脚本资源可以包含在脚本代码本身的末尾。一条分隔线指示了脚本代码和资源之间的边界，如下所示：

  

      If BlahBlah Then
      BlahBlah Blah
      End If
      ==SCRIPT RESOURCES
      <resources>
      <resource name="blah1" type="dialog">
      <dialog blah blah>
      </dialog>
      </resource>
      <resource name="blah2" type="dialog">
      <dialog blah blah>
      </dialog>
      </resource>
      <resource type="strings">
      <strings lang="blah">
      <string id="blah" text="Blah!" />
      </strings>
      </resource>
      </resources>

  `==SCRIPT RESOURCES` 行之前的任何内容都被视为脚本代码的一部分，而其之后的所有内容都是 XML 格式化的资源。

- 可以使用 **[Script](/Manual/reference/scripting_reference/scripting_objects/script.zh.md).LoadResources** 方法从外部文件或原始 XML 字符串加载脚本资源。 请注意，如果脚本包含在包中，则资源文件必须具有 *.odxml* 作为文件扩展名。

### 资源类型

当前正在使用的两种类型的脚本资源是对话框和字符串。你通常不需要直接编辑资源：

- 在脚本编辑器中，使用对话框或字符串编辑器以图形方式编辑资源，并且隐藏 XML 定义
- 在按钮编辑器中，将资源定义拆分到单独的标签页上，以便于使用。 可以使用 GUI 编辑器来编辑对话框 - 按钮中的字符串资源只需要以 XML 形式编辑。