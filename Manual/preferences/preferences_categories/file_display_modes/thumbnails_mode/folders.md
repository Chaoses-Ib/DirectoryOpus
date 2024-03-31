# Folders

Contains options relating to thumbnails generated for folders (rather than for files).

### Folder thumbnails

- **Display thumbnails for folders**: This option enables the display of thumbnails for folders as well as for files.
- **Use Windows folder thumbnails where possible**: If turned on, Opus will try to retrieve folder thumbnails from Explorer before generating its own. You may want this on if you want thumbnails in Opus to match what you see in Explorer.

### Directory Opus folder thumbnails

These options are used when Opus generates its own folder thumbnails, rather than retrieving them from Explorer.

- **Exclude folders with custom icons**: If a folder has a custom icon set for it, that icon will be used rather than a generated thumbnail.
- **Include images of folder contents**: If this option is turned off, folder thumbnails will show a generic image representing a folder. With this option on, Opus will display miniature thumbnails for the first few files it finds within the folder, in the actual folder thumbnail itself.
- **Choose most recent images**: When Opus is generating its own folder thumbnails, this option makes it use the most recent images in the folder to generate the thumbnail. When turned off the contents of the folder will be looked at alphabetically.
- **Resize mode**: Let's you choose how images are resized to fit into the thumbnail.
- **Match wildcard**: Lets you provide a [standard wildcard pattern](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) to control the filenames that Opus will look for when generating folder thumbnails. If this is turned off, any files within the folder that Opus can generate thumbnails for can be used.

     * **Use first matching file only**: Opus will only use a single image (the first one found) rather than multiple images to generate the thumbnail.
