## Args

The **Args** object is passed to a script when it is invoked via a command, via the **[Func](func.md).args** property. It is used when a command added by a script has a [command line template](../../command_reference/argument_types.md) and provides access to any arguments provided on the command line.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<argument name\>*</td><td>

*variant*</td><td>

The **Args** object will have one property corresponding to each of the arguments in the command line template.

For example, if the command line template is **NAME/K,SIZE/N**, the **Args** object would have two properties, called **name** and **size**.

The type returned by each property is also defined by the template. In the above example, **name** would return a *string* and **size** an *int*.  
A **/S** argument returns a *bool*, a **/N** argument returns an *int*, and all other argument types return a *string*. Note that a **/O** argument will also return a *bool* if no string value is provided on the command line.  
If an argument is marked in the template as **/M** (multiple) then it returns a **[Vector](vector.md)** containing elements of the appropriate type.

If an argument was not provided on the command line by the user, its property will either return *bool* (for a **/S** or **/O** argument), or an empty variant otherwise.
</td></tr><tr><td>

**got_arg**</td><td>

*object*</td><td>

The **got_arg** property returns an object with a *bool* child property for each argument in the template. It lets you test if a particular argument was provided on the command line, before you actually query for the value of the argument. For example, ***If Args.got_arg.size Then...***
</td></tr></tbody>
</table>

