# Appearance

This page lets you configure the appearance of specific columns when the Lister is in Details or Power mode. For example, you could have the **Type** field displayed with a different background color, or the **Size** field in bold. For each column (if it's enabled), you can specify text and background colors, and select from bold, italic and underline styles.

The **Current sort column** entry is a special set of colors and styles that applies to whichever field the file list is currently sorted by (or if multiple sort fields are defined, the primary sort field). While you can set its font styles here, its colors are set on the [Directory Opus Colors](../colors_and_fonts/directory_opus_colors.md) page.

### Custom color and font settings

Turn on the **Custom color and font settings** to enable color and font style overrides for the selected column.

The list of fields allows you to see the field colors and styles at a glance. If the checkbox is not set for a field then its colors, while visible in the list itself, are not currently enabled and will not affect the colors used to display files. If an arrow appears on the right of a field's name then that field is set to sort in reverse. The checkboxes and arrows are independent of each other; that is, you can enable reverse sorting without having to turn on special colors, and vice versa.

### Other per-column options

- **Default width**: Lets you configure a default width for every field. This is especially useful in configuring the default width of the *Thumbnail* column. Note that some columns have their default width set in pixels, and some in characters.
- **Middle ellipsis**: Normally when the text in a column doesn't fit, its end is truncated and an ellipsis (...) displayed at the end. If you turn this option on, the truncation happens in the middle of the string, so you will see the beginning and the end instead of just the beginning.
- **Reverse graph meaning**: This option is available for columns that display bar graphs, and lets you invert the meaning of the graph (e.g. instead of the widest graph indicating the oldest file, it would indicate the newest file).
- **Reverse initial sort direction**: Lets you change the way each field sorts by default. When the option is off, as is the case for most fields, the field will sort from smallest (at the top) to largest (at the bottom) the first time you click its column header. The same field will sort from largest to smallest if you click its column header a second time. For example, the filename field defaults to sorting A-to-Z on the first click and Z-to-A on the second.
  When **Reverse initial sort direction** is turned on for a field, you get the opposite: Largest to smallest on the first click; smallest to largest on the second.

  Note that date fields default to reverse sorting, giving you the most recent (largest date) files at the top on your first click. Size fields also do this, giving you the largest files at the top on your first click.
