# Metadata Editor

These options affect the behaviour of the [metadata pane](/Manual/basic_concepts/the_lister/metadata_pane.md).

- **Add to multi-value fields by default**: When you select multiple files, the metadata pane displays *Multiple values* for fields that contain different data. If you make changes to one of these fields, the new value will usually replace the existing value in all selected files. If this option is enabled, for fields such as tags (which can contain multiple values), the new values you input will be appended to the existing values for all selected files, rather than replacing them.\<WRAP\>

Note that even if this option is turned off, you can add new values by prefixing them with a \<ib:inline-code\>`+`\</ib:inline-code\> character (and remove values using a \<ib:inline-code\>`-`\</ib:inline-code\> character).\</WRAP\>

- **Apply changes automatically**: Any changes you make to the metadata of a file via the panel will be saved automatically when a new file is selected or the panel is closed.
- **Decimal geocoordinate editing**: When editing fields like *latitude* and *longitude*, the expected input will be a decimal value rather than degrees/minutes/seconds.
- **Show popup tag history**: When editing the *tags* field, a popup history of previously used tags will be shown that you can select from.
  - **Include read tags as well as written**: If turned on, the popup history will include tags that have been read from files. If turned off, only tags you have explicitly written through Opus will appear in the history list.
