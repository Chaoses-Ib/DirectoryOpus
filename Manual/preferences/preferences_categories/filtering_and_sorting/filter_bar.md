# Filter Bar

These options affect the [Filter Bar](/Manual/basic_concepts/searching_and_filtering/filter_bar.md), the bar that can be displayed at the bottom of a file display to filter the displayed contents of the current folder.

- **Display Filter Bar**: Lets you choose when the Filter Bar displayed.
  - **Always**: The bar is always displayed, whether a filter is active or not.
  - **Whenever a filter is set**: The bar is displayed when a filter is active, and hidden otherwise.
  - **Only when editing the filter**: The bar will only be displayed when you activate it to edit the filter - it will close again when you finish editing, whether a filter is active or not.

- **Automatically type <kbd>\*</kbd> when activating the filter bar**: When turned on, a <kbd>\*</kbd> will be typed into the filter bar if the activation key is pushed and no filter is currently set. Since the activation key is usually <kbd>\*</kbd> this means you can type things like `*.txt` directly into the file display to do common filters on suffixes. With the option turned off, you would have to type `**.txt` instead. (One <kbd>\*</kbd> to activate the filter bar, another to type the wildcard.) This option is particularly useful when **Partial matching** is turned off.

- **Clear the filter automatically when changing folders**: If this option is turned off, any filter you assign via the filter bar will remain in effect when you change to another folder.

- **Real-time filtering**: When turned on, the file display will be filtered in real-time, as you edit the filter. If turned off, you must press the <kbd>Enter</kbd> key to activate the filter you have typed.

##### Default settings

The following options adjust the default filter settings of the filter bar. You can use the ![](/Manual/images/media/13/button_edit.png) button on the filter bar itself to change these options on-the-fly.

- **Ignore diacritics**: Diacritics, or accent symbols, will be ignored when filtering. So for example a plain `e` would be treated the same as `é`.

- **Match any word:** This option treats all words you enter as separate patterns. For example, you can type `moo cow` and it would automatically match a file called "moo" or a file called "cow". This saves you having to build up complex *OR* wildcards (the equivalent wildcard would be `(moo|cow)`). You can also use `+` and `-` to specifically include or exclude words - see the page on the [filter bar](/Manual/basic_concepts/searching_and_filtering/filter_bar.md) for more details.

- **Partial matching**: When turned on, the filtering will automatically match on sub-strings, so typing `og` would match any file containing those letters, e.g. "dog.txt" or "google.png". When off, the pattern you enter must match exactly - so you would need to type `*og*` for the same effect. Note that if you explicitly add a `*` at the start or end of the pattern then Opus will assume you do not wish to use partial matching even if it is switched on. This allows you the convenience of partial matching most of the time while still being able to filter by the start or end of things when you need to.

- **Use regular expression**: When turned on, the pattern you enter into the will be treated as a [regular expression](/Manual/reference/wildcard_reference/regular_expression_syntax.md) rather than a simple wildcard.

- **Evaluator**: (Opus 13.3.4 and above) In evaluator mode, the quick filter expression is passed to the [Evaluator](/Manual/evaluator/README.md) for each item in the list. The expression should return **true** if the item should be shown, or **false** if it should be hidden. You can use evaluator code directly, and you can also invoke a pre-defined [filter](/Manual/file_operations/filtered_operations/README.md) using `?filtername`. If the pre-defined filter also uses evaluator code, arguments can be passed through to it following the name. For example, `?bigfiles:5` would invoke a pre-defined filter called "bigfiles" and pass the value "5" to it as a variable. See [evaluator filters and find](/Manual/evaluator/applicable_contexts/filters_and_find.md) for more information.
