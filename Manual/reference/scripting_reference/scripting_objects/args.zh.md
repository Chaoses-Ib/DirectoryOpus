# Args

**Args** 对象会在脚本通过命令调用时传递给它，通过 **[Func](func.zh.md).args** 属性。会在脚本添加的命令带有一个 [命令行模板](../../command_reference/argument_types.zh.md) 并且允许访问命令行上提供的任何参数时使用。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<参数名称\>*</td><td>

*变体*</td><td>

**Args** 对象将对应于命令行模板中的每个参数提供一个属性。

例如，如果命令行模板是 **NAME/K,SIZE/N**，则 **Args** 对象会提供两个属性，名称为 **name** 和 **size**。

每个属性返回的类型也由模板定义。在上述示例中，**name** 将返回一个 *string*，**size** 将返回一个 *int*。**/S** 参数返回 *bool*，**/N** 参数返回 *int*，所有其它参数类型返回 *string*。请注意，如果命令行上未提供字符串值，**/O** 参数也会返回 *bool*。
如果一个参数在模板中标记为 **/M**（多重），则它会返回一个包含适当类型元素的 **[Vector](vector.zh.md)**。

如果用户未在命令行上提供某个参数，则其属性会返回 *bool*（对于 **/S** 或 **/O** 参数），否则返回一个空变体。
</td></tr><tr><td>

**got_arg**</td><td>

*对象*</td><td>

**got_arg** 属性返回一个对象，该对象针对模板中的每个参数都带有一个 *bool* 子属性。它允许你测试某个参数是否在命令行上提供，然后才实际查询该参数的值。例如，***If Args.got_arg.size Then...***
</td></tr></tbody>
</table>