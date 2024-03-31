# Var

**Var** 对象标识单个用户或脚本定义的变量。各个 **Var** 对象可以从 **[Vars](vars.zh.md)** 对象进行访问或枚举。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*variant*  
或 *string*</td><td>

**Var** 对象的默认值返回变量本身的值，有一个例外。如果 **Var** 对象在 **[Vars](vars.zh.md)** 集合的枚举中被访问，则默认值返回变量名称。

因此，例如：

For Each Var in DOpus.Vars  
DOpus.Output("变量名称 = " & Var)  
Next

与：

Set Var = DOpus.Vars("myvar")  
DOpus.Output("变量值 = " & Var)
</td></tr><tr><td>
name</td><td>

*string*</td><td>

返回变量的名称。一旦变量被赋值，你就不能更改它的名称，而是从其集合中删除该变量并添加一个新变量。
</td></tr><tr><td>
persist</td><td>

*bool*</td><td>

如果变量是持久的（已保存），则返回 **True**；否则，则返回 **False**。可以设置该属性来更改持久性状态。
</td></tr><tr><td>
value</td><td>

*variant*</td><td>

返回变量的值。可以设置该属性来更改变量的值。

可以在 **Var** 对象中存储任何类型的变量，但不能将所有类型保存到磁盘。如果希望变量持久，则只能使用 *bool*、*int*、*string*、*date*、*currency* 或这些类型的 **[Vector](vector.zh.md)**。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
Delete</td><td>

*无*</td><td>

*无*</td><td>
从其父集合中删除此变量。
</td></tr></tbody>
</table>