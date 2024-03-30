# Argument Types

The following qualifiers are used in the internal command templates to indicate the type of each argument. Remember that you **never** type the qualifiers when using arguments - they are merely a clue as to the argument type.

<table>
<thead><tr><th>
Qualifier</th><th>
Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
/S</td><td>
Switch</td><td>
Indicates a switch argument (a Boolean option that can either be on or off).
</td></tr><tr><td>
/K</td><td>
Keyword</td><td>
Indicates a value argument (a value must be provided following the argument keyword).
</td></tr><tr><td>
/O</td><td>
Optional</td><td>
Indicates an optional argument (can be used either by itself as a switch, or with a following value).
</td></tr><tr><td>
/N</td><td>
Numeric</td><td>
The value of the argument must be a number.
</td></tr><tr><td>
/M</td><td>
Multiple</td><td>
The argument can accept multiple values (e.g. a list of files).
</td></tr><tr><td>
/R</td><td>
Raw</td><td>

The argument accepts a "raw" value. For these arguments, the rest of the command line following the argument name is taken as the value.  
Arguments of this type are the only ones that do not require quotes around values which contain spaces.
</td></tr></tbody>
</table>

See the [Internal Command Arguments](/Manual/customize/creating_your_own_buttons/internal_command_arguments.md) page for a full description of the various argument types.
