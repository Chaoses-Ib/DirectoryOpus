# 脚本对话框示例

这是 [脚本对话框](../script_dialogs/README.zh.md) 的一个示例；它实现了 [脚本对话框](../script_dialogs/README.zh.md) 部分开始时所示的对话框。它利用了“标签页控件”来托管两个子对话框，并且还演示了如何向“列表框”控件添加和删除字符串。

![](/Manual/images/media/image057.png)

*标签页控件* 已被配置为托管两个子对话框；“兴趣”和“喜欢的书”。单击标签页可以让您在这两页中来回切换。

对话框的大多数控件实际上并未执行任何操作——只有“喜欢的书”标签页已经实现。如果您切换到该标签页，可以在“输入标题”字段中输入一个字符串，然后单击 **添加** 按钮将其添加到列表中。单击列表中的一个项目并单击 **删除** 按钮以将其移除。

该对话框还提供了一个可调整大小的对话框示例。您可以让任何对话框可调整大小，但使用标签页时它特别有用，因为这意味着*标签页控件*和父对话框可以自动调整大小以适应标签页内显示的内容。

如果您想尝试此示例，创建新的工具栏按钮（类型为*脚本函数*）并将脚本代码粘贴到命令编辑器的 **脚本代码** 标签页中，将资源 XML 粘贴到 **资源** 标签页中。以下所有示例均使用 VBScript 编写。

### 代码

    Function OnClick(ByRef clickData)

    Set dlg = DOpus.Dlg
    dlg.window = clickData.func.sourcetab
    dlg.template = "person"
    dlg.detach = true
    dlg.Show

    Do
    Set msg = dlg.GetMsg()

    Select Case msg.control

    Case "add"

    ' get the string the user has entered
    str = dlg.Control("title", "books").value
    if Len(str) > 0 Then
    ' add to the list box and clear the edit field
    dlg.Control("books", "books").AddItem(str)
    dlg.Control("title", "books").value = "" 
    End If 
    Case "del"
    ' get the selection from the list box
    sel = dlg.Control("books", "books").value
    if sel > -1 Then 
    ' remove it from the list
    dlg.Control("books", "books").RemoveItem(sel)

    End If 
    End Select 
    Loop While msg 
    End Function
     

### 资源

    <resources>
    <resource name="books" type="dialog">
    <dialog fontsize="8" height="100" lang="english" resize="yes"
    title="Favorite Books" width="180">
    <control height="83" name="books" resize="wh" type="listbox" width="176"
    x="2" y="2" />
    <control halign="left" height="12" name="title" resize="yw"
    tip="Enter title and press Add" type="edit" width="101" x="2" y="86" />
    <control height="12" name="add" resize="xy" title="Add" type="button"
    width="34" x="106" y="86" />
    <control height="12" name="del" resize="xy" title="Delete" type="button"
    width="35" x="143" y="86" />
    </dialog>
    </resource>
    <resource name="interests" type="dialog">
    <dialog fontsize="8" height="100" lang="english" resize="yes"
    title="Interests" width="180">
    <control halign="left" height="96" multiline="yes" name="interests"
    readonly="yes" resize="wh" title="Nothing here yet :)\n" type="edit"
    width="176" x="2" y="2" />
    </dialog>
    </resource>
    <resource name="person" type="dialog">
    <dialog fontsize="8" height="201" lang="english" resize="yes"
    standard_buttons="ok,cancel" title="Personal Information" width="153">
    <control halign="left" height="8" name="static1" title="Name:" type="static"
    width="21" x="11" y="7" />
    <control halign="left" height="12" name="name" tip="Enter your name"
    type="edit" width="106" x="39" y="6" />
    <control halign="left" height="8" name="static2" title="Age:" type="static"
    width="15" x="17" y="21" />
    <control halign="center" height="12" name="age" number="yes"
    title="Edit Control" type="edit" updown="yes" val_max="50" val_min="10"
    width="42" x="39" y="20" />
    <control halign="left" height="8" name="static3" title="Sex:" type="static"
    width="14" x="18" y="38" />
    <control height="10" name="f" title="Female" type="radio" width="34"
    x="39" y="37" />
    <control height="10" name="m" title="Male" type="radio" width="26"
    x="39" y="47" />
    <control height="10" name="o" title="Other" type="radio" width="29"
    x="39" y="57" />
    <control halign="left" height="8" name="static4" title="Country:"
    type="static" width="27" x="5" y="76" />
    <control height="40" name="country" type="combo" width="104" x="39" y="75">
    <contents>
    <item text="Australia" />
    <item text="UK" />
    <item text="USA" />
    <item text="Spain" />
    <item text="France" />
    <item text="Germany" />
    <item text="China" />
    <item text="Japan" />
    </contents>
    </control>
    <control height="84" name="tab1" resize="wh" type="tab" width="138"
    x="7" y="94">
    <tabs>
    <tab dialog="interests" />
    <tab dialog="books" />
    </tabs>
    </control>
    </dialog>
    </resource>
    </resources>