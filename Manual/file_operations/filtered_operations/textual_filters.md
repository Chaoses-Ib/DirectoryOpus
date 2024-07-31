# Textual Filters

A textual filter is simply a representation of a [filter clause](defining_a_filter.md) in textual format.

You can use textual filters as arguments for various commands. For example, the `Find` command can be used to search beneath the current folder for files greater than 1mb in size:

    Find HERE FILTERDEF size match > 1 mb

The `FILTERDEF` argument in the above example introduces the textual filter - everything following it is the filter definition.

### Defining a textual filter

The easiest way to create a textual filter is to use the [filter control](../.md) to define the filter using the user interface, and then click the **Edit as text** button. This will convert the UI-based filter into a text based one. You can then copy the text out to use on the command line.

You can also build a textual filter from scratch using the various [keywords](/Manual/reference/textual_filters.md).

### Using a textual filter

Various commands accept a textual filter as an argument - `Find`, `SetAttr`, `Print`, `Copy` and `Delete` all have a `FILTERDEF` argument that lets you provide a filter. The `FILTERDEF` argument is always defined as a `/R` "raw" argument - meaning that it must be the last argument given on the command line.

You can use the multiline command syntax in button definitions to provide a filter definition that spans more than one line. For example,

    Find IN C:\ 
    [[
    FILTERDEF
    size match > 100 kb and
    size match < 200 kb and
    name match *.jpg
    ]]

### Textual filters using the evaluator

If a textual filter beginning with a `=` character it uses the [Evaluator](/Manual/evaluator/README.md) - they aren't traditional filters.

See the [Evaluator Filters and Find](/Manual/evaluator/applicable_contexts/filters_and_find.md) page for more information.
