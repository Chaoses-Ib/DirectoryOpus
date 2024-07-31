# Var

**Var** 对象代表单个用户或脚本定义的变量。可以从 **[Vars](vars.zh.md)** 对象访问或枚举单个 **Var** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*variant*  
或 *string*</td><td>

**Var** 对象的默认值返回变量本身的值，只有一个例外。如果 **Var** 对象正在作为 **[Vars](vars.zh.md)** 集合枚举的一部分被访问，则默认值返回变量名称。

例如：

For Each Var in DOpus.Vars  
DOpus.Output("变量名称 = " & Var)  
Next

与：

Set Var = DOpus.Vars("myvar")  
DOpus.Output("变量值 = " & Var)
</td></tr><tr><td>
name</td><td>

*string*</td><td>

返回变量的名称。一旦变量被分配，您就无法更改它的名称 - 相反，请将其从其集合中删除并添加一个新的变量。
</td></tr><tr><td>
persist</td><td>

*bool*</td><td>

如果变量是持久性的（保存的），则返回 **True**，否则返回 **False**。您可以设置此属性来更改持久性状态。
</td></tr><tr><td>
value</td><td>

*variant*</td><td>

返回变量的值。您可以设置此属性来更改变量的值。

您可以在 **Var** 对象中存储任何类型的变量，但并非所有类型都可以保存到磁盘。如果您希望您的变量是持久的，您应该只使用 *bool*、*int*、*string*、*date*、*currency* 或 **[Vector](vector.zh.md)** 中的这些类型。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Delete</td><td>

*无*</td><td>

*无*</td><td>
从其父集合中删除此变量。
</td></tr></tbody>
</table>