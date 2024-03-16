# Grouping

The **Grouping** tab in the *Folder Format* dialog lets you choose which column (if any) the file list is [grouped](../../sorting_and_grouping/RAEDME.md) by.

- **Group by**: Select the column to group the list by, from the dropdown list. This column doesn't have to be displayed.
- **Scheme**: If multiple [grouping schemes](/Manual/preferences/preferences_categories/file_display_columns/evaluator_groups.md) have been defined for the group, you can pick the scheme from this dropdown.
- **Sort groups**: Choose whether groups should be sorted in ascending or descending order.
- **Combine**: Choose how to handle similar values:
  - **Combine similar values**: A range of similar values will be put in a single group (e.g. A-H).
  - **Never combine values**: Instead of A-H you would have A, B, C, D, E, F, G, H, etc. This is only really useful for text fields like *User description*.
  - **Singletons in 'Other' group**: Similar values won't be combined, except for groups with only one member (which will be combined into a group called 'Other').
- **Collapse all groups initially**: File groups will start out as collapsed instead of expanded.
- **Put folders in their own group**: No matter how files are grouped, all folders will be placed into their own group.
