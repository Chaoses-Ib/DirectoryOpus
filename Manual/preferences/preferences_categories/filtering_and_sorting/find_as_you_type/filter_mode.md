# Filter Mode

This page contains options relating to the [Find-As-You-Type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field's *Filter* mode. Filter mode lets you filter the currently displayed folder by filename.

- **Allow <kbd>Enter</kbd> key to open selected item**: Pressing the <kbd>Enter</kbd> key will open the item with focus rather than simply closing the FAYT.
- **Select first matching item**: The first item that matches the filter will be automatically selected.

##### Filter Mode

(Opus 13.3.4 and above) These options control the behaviour of the filter.

- **Ignore diacritics**: Diacritics, or accent symbols, will be ignored when filtering. So for example a plain `e` would be treated the same as `é`.

- **Match any word:** This option treats all words you enter as separate patterns. For example, you can type `moo cow` and it would automatically match a file called "moo" or a file called "cow". This saves you having to build up complex *OR* wildcards (the equivalent wildcard would be `(moo|cow)`). You can also use `+` and `-` to specifically include or exclude words - see the page on the [filter bar](/Manual/basic_concepts/searching_and_filtering/filter_bar.md) for more details.

- **Partial matching**: When turned on, the filtering will automatically match on sub-strings, so typing `og` would match any file containing those letters, e.g. "dog.txt" or "google.png". When off, the pattern you enter must match exactly - so you would need to type `*og*` for the same effect. Note that if you explicitly add a `*` at the start or end of the pattern then Opus will assume you do not wish to use partial matching even if it is switched on. This allows you the convenience of partial matching most of the time while still being able to filter by the start or end of things when you need to.

- **Use regular expression**: When turned on, the pattern you enter into the will be treated as a [regular expression](/Manual/reference/wildcard_reference/regular_expression_syntax.md) rather than a simple wildcard.

- **Evaluator**: (Opus 13.3.4 and above) In evaluator mode, the quick filter expression is passed to the [Evaluator](/Manual/evaluator/README.md) for each item in the list. The expression should return **true** if the item should be shown, or **false** if it should be hidden. You can use evaluator code directly, and you can also invoke a pre-defined [filter](/Manual/file_operations/filtered_operations/README.md) using `?filtername`. If the pre-defined filter also uses evaluator code, arguments can be passed through to it following the name. For example, `?bigfiles:5` would invoke a pre-defined filter called "bigfiles" and pass the value "5" to it as a variable. See [evaluator filters and find](/Manual/evaluator/applicable_contexts/filters_and_find.md) for more information.
