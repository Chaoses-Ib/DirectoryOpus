# Args

**Args** 对象在脚本通过命令行调用时，或通过 **[Func](func.zh.md).args** 属性被传递给脚本。当脚本添加的命令拥有 [命令行模板](../../command_reference/argument_types.zh.md) 时，它用于访问命令行上提供的任何参数。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<参数名称\>*</td><td>

*variant*</td><td>

**Args** 对象将拥有与命令行模板中的每个参数相对应的属性。

例如，如果命令行模板是 **NAME/K,SIZE/N**，**Args** 对象将拥有两个属性，名为 **name** 和 **size**。

每个属性返回的类型也由模板定义。在上面的例子中，**name** 将返回一个 *string*，而 **size** 将返回一个 *int*。  
**/S** 参数返回一个 *bool*，**/N** 参数返回一个 *int*，所有其它参数类型返回一个 *string*。请注意，**/O** 参数如果命令行上没有提供字符串值，也将返回一个 *bool*。  
如果模板中标记了一个参数为 **/M**（多个），则它将返回一个包含适当类型元素的 **[Vector](vector.zh.md)**。

如果用户在命令行上没有提供某个参数，则它的属性将返回 *bool*（对于 **/S** 或 **/O** 参数），或者返回一个空变体。
</td></tr><tr><td>

**got_arg**</td><td>

*object*</td><td>

**got_arg** 属性返回一个对象，该对象对模板中的每个参数都有一个 *bool* 子属性。它允许您在实际查询参数的值之前，测试某个特定参数是否在命令行上提供。例如，***If Args.got_arg.size Then...***
</td></tr></tbody>
</table>