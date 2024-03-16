# Evaluator Grammar

The grammar of the evaluator is similar to that of JScript (Javascript) and C++.

##### Brief introduction

Generally, evaluation of an expression proceeds from left-to-right. Standard BODMAS rules apply to mathematical operators - you can use parentheses \<ib:inline-code\>`()`\</ib:inline-code\> to change the order of evaluation. If an evaluation expression contains more than one clause, each clause must end with a semi-colon \<ib:inline-code\>`;`\</ib:inline-code\> character.

You can use \<ib:inline-code\>`if`\</ib:inline-code\>, \<ib:inline-code\>`elseif`\</ib:inline-code\> and \<ib:inline-code\>`else`\</ib:inline-code\> to test conditions and perform different evaluations based on the results. The condition to test must appear inside parentheses \<ib:inline-code\>`()`\</ib:inline-code\>. You can also use the \<ib:inline-code\>`?:`\</ib:inline-code\> *ternary operator* (also known as the *conditional operator*).

You can open a *scope* after an \<ib:inline-code\>`if`\</ib:inline-code\>, \<ib:inline-code\>`elseif`\</ib:inline-code\> or \<ib:inline-code\>`else`\</ib:inline-code\> using a \<ib:inline-code\>`{`\</ib:inline-code\> character and close it with a \<ib:inline-code\>`}`\</ib:inline-code\>. Scopes are used to allow for more than one clause to be evaluated as the result of the test.

You can assign variables using \<ib:inline-code\>`=`\</ib:inline-code\>. Variables do not need to be declared in advance. Variables are [typed](variable_types.md) but not strongly-typed - the type will be inferred and conversion between types is automatic. You can also use the \<ib:inline-code\>`as`\</ib:inline-code\> operator for explicit conversion.

The evaluator provides a number of [functions](/Manual/reference/evaluator/RAEDME.md). To call a function, the function name needs to be followed by parentheses \<ib:inline-code\>`()`\</ib:inline-code\>. If the function takes any arguments these must be comma-separated and appear inside the parentheses - but the parentheses are needed even if the function takes no arguments.

You can use comments, which are ignored by the evaluator - they must begin with a \<ib:inline-code\>`//`\</ib:inline-code\>.

##### Return values

Most contexts that invoke the evaluator expect a return value. For example, an evaluation expression to modify a button label would return a string to use as the label of the button.

You can return the result of an evaluation expression to the caller using the \<ib:inline-code\>`return`\</ib:inline-code\> keyword.

    return "The Button Label";

Evaluation expressions also have an *implicit return value* if the \<ib:inline-code\>`return`\</ib:inline-code\> keyword isn't used - the value of the last referenced function, operator or variable will be returned if one is not stated explicitly. This is a convenience to save space.

For example, you can insert the value of the evaluator variable "source" directly into a command line with the code \<ib:inline-code\>`{=source=}`\</ib:inline-code\>. This is equivalent to \<ib:inline-code\>`{=return source;=}`\</ib:inline-code\>.

##### Operators

The following mathematical operators are supported:

|     |                          |
|-----|--------------------------|
| \+  | Addition / concatenation |
| \-  | Subtraction              |
| \*  | Multiplication           |
| /   | Division                 |
| Mod | Modulus                  |

The following assignment operators are supported:

|     |                           |
|-----|---------------------------|
| =   | Direct assignment         |
| +=  | Addition assignment       |
| -=  | Subtraction assignment    |
| \*= | Multiplication assignment |
| /=  | Division assignment       |

Pre- and post-increment and decrement operators are supported:

|     |           |
|-----|-----------|
| ++  | Increment |
| --  | Decrement |

(Pre-increment, e.g. \<ib:inline-code\>`++a`\</ib:inline-code\>, returns the incremented value; post-increment, e.g. \<ib:inline-code\>`a++`\</ib:inline-code\>, returns the previous value).

The following relational (comparison) operators are supported:

<table>
<tbody>
<tr class="odd">
<td>==</td>
<td>Is equal to</td>
</tr>
<tr class="even">
<td>!=<br />
&lt;&gt;</td>
<td>Is not equal to</td>
</tr>
<tr class="odd">
<td>&gt;</td>
<td>Is greater than</td>
</tr>
<tr class="even">
<td>&lt;</td>
<td>Is less than</td>
</tr>
<tr class="odd">
<td>&gt;=</td>
<td>Is greater than or equal to</td>
</tr>
<tr class="even">
<td>&lt;=</td>
<td>Is less than or equal to</td>
</tr>
</tbody>
</table>

The following logical operators are supported:

<table>
<tbody>
<tr class="odd">
<td>And<br />
&amp;&amp;</td>
<td>Logical AND</td>
</tr>
<tr class="even">
<td>Or<br />
||</td>
<td>Logical OR</td>
</tr>
<tr class="odd">
<td>Not<br />
!</td>
<td>Logical NOT</td>
</tr>
</tbody>
</table>

The following bitwise operators are supported:

|     |             |
|-----|-------------|
| &   | Bitwise AND |
| \|  | Bitwise OR  |
| ~   | Bitwise NOT |
| ^   | Bitwise XOR |

Other operators:

|       |                                                                                                                                                                                                                                                                                                                                                                              |
|-------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ?:    | The ternary operator returns a value based on a condition, e.g. \<ib:inline-code\>`x = a ? b : c;`\</ib:inline-code\> would set \<ib:inline-code\>`x`\</ib:inline-code\> to the value of \<ib:inline-code\>`b`\</ib:inline-code\> if \<ib:inline-code\>`a`\</ib:inline-code\> were true, otherwise it would be set to the value of \<ib:inline-code\>`c`\</ib:inline-code\>. |
| As    | The conversion operator. Lets you convert a variable to an explicit type. Can also be used to format numbers, sizes and dates.                                                                                                                                                                                                                                               |
| :     | When used by itself (and not as part of the ternary operator), this provides a way to initialise a variable as an explicit type.                                                                                                                                                                                                                                             |
| \[ \] | Used to define a *value container*. A value container is a variable that can contain other variables - kind of like a *struct* in C++ or a Javascript object array.                                                                                                                                                                                                          |
| .     | Used to access a member variable of a *value container*.                                                                                                                                                                                                                                                                                                                     |

##### If / ElseIf / Else

The main form of flow control in the evaluator begins with an \<ib:inline-code\>`if`\</ib:inline-code\> clause. The condition to test must appear inside parentheses. The condition (which can include function calls and mathemetical operations) is evaluated as either true or false. If the result is true, the code branch immediately following the \<ib:inline-code\>`if`\</ib:inline-code\> is entered. If that code branch needs to contain more than a single clause, you must open a scope using a \<ib:inline-code\>`{`\</ib:inline-code\> brace character.

    // Simple test, if x equals 5 we return the string "five" to whoever called us
    if (x == 5) return "five";

    // More complex test, if x plus y is greater than 20...
    if (x + y > 20)
    {
        // we've opened a scope so we can have more than one clause
        Output("yes it's more than 20!");
        return "more than twenty";
    }

If the condition tested by the \<ib:inline-code\>`if`\</ib:inline-code\> clause evaluates to false, the evaluator skips over the next clause (or the next scope, if a scope is opened). It then looks for an \<ib:inline-code\>`elseif`\</ib:inline-code\> or \<ib:inline-code\>`else`\</ib:inline-code\> keyword. \<ib:inline-code\>`Elseif`\</ib:inline-code\> lets you provide another condition to test - the same behavior applies to that as with \<ib:inline-code\>`if`\</ib:inline-code\>.

    if (x + y > 20)
        return "more than twenty";
    elseif (x == 5)
        return "five";

You can have as many \<ib:inline-code\>`elseif`\</ib:inline-code\> clauses as you like. The evaluator will continue evaluating the conditions for each one in order, until it finds one that evaluates as true.

If an \<ib:inline-code\>`else`\</ib:inline-code\> clause is provided then the code following it is only executed if none of the preceding conditions evaluated as true.

    if (x + y > 20)
        return "more than twenty";
    elseif (x == 5)
        return "five";
    else
        return "something else";

Note that only one (at most) of the \<ib:inline-code\>`if`\</ib:inline-code\>, \<ib:inline-code\>`elseif`\</ib:inline-code\> or \<ib:inline-code\>`else`\</ib:inline-code\> clauses in a block will have its code executed. If the block does not end with an \<ib:inline-code\>`else`\</ib:inline-code\> then its possible that none of the code within the block would be executed (i.e. if all conditions evaluate to false).

##### Ternary Operator

The *ternary* or *comparison* operator is the only operator that takes three parameters rather than two. It's basically a shorthand form of \<ib:inline-code\>`if`\</ib:inline-code\>/\<ib:inline-code\>`else`\</ib:inline-code\>.

    return (x == 5) ? "five" : "something else";

The expression immediately to the left of the \<ib:inline-code\>`?`\</ib:inline-code\> is evaluated as true or false. If it evaluates to true, the value immediately to the right of the \<ib:inline-code\>`?`\</ib:inline-code\> is returned - otherwise, the value to the right of the \<ib:inline-code\>`:`\</ib:inline-code\> is returned instead.

You can string multiple ternary operators together if desired:

    return (x + y > 20) ? "more than twenty" : (x == 5) ? "five" : "something else";

Remembering that evaluation proceeds from left-to-right, in the above example:

- Is the result of \<ib:inline-code\>`x + y`\</ib:inline-code\> greater than 20? If so, return "more than twenty"
- Otherwise, is \<ib:inline-code\>`x`\</ib:inline-code\> equal to 5? If so, return "five"
- Otherwise, return "something else"
