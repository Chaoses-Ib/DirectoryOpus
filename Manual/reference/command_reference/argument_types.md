# Argument Types

The following qualifiers are used in the internal command templates to indicate the type of each argument. Remember that you **never** type the qualifiers when using arguments - they are merely a clue as to the argument type.

| Qualifier | Type | Description |
| --- | --- | --- |
| /S | Switch | Indicates a switch argument (a Boolean option that can either be on or off). |
| /K | Keyword | Indicates a value argument (a value must be provided following the argument keyword). |
| /O | Optional | Indicates an optional argument (can be used either by itself as a switch, or with a following value). |
| /N | Numeric | The value of the argument must be a number. |
| /M | Multiple | The argument can accept multiple values (e.g. a list of files). |
| /R | Raw | The argument accepts a "raw" value. For these arguments, the rest of the command line following the argument name is taken as the value.  <br />Arguments of this type are the only ones that do not require quotes around values which contain spaces. |

See the [Internal Command Arguments](/Manual/customize/creating_your_own_buttons/internal_command_arguments.md) page for a full description of the various argument types.
