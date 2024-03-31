# Metadata

These options define what happens when Opus saves certain metadata to files (via the [Metadata Pane](/Manual/basic_concepts/the_lister/metadata_pane.md) or the [Edit Metadata](/Manual/file_operations/editing_metadata/README.md) command).

- **Update file dates when setting metadata inside files**: Normally the modification date of a file is unchanged when Opus saves metadata - if this option is on, the timestamp will be set to the current time. This option deals with metadata changes which are written into the files themselves, where the file format has inherent support for it, such as ID3 tags in MP3 files and EXIF tags in JPG files.
- **Update file dates when setting metadata in NTFS ADS**: If this option is on, file timestamps will be set to the current time when metadata changes are saved into NTFS ADS (alternate data streams). With this option on, a file's date will change if you place or modify a label on it (if labels are stored in the filesystem rather than a central configuration file). Changes to file descriptions, ratings, and the general "tags" field will also bump a file's date, for file formats where Opus does not have a way to store them in the main file itself (e.g. text files). You would normally want this option off unless you are using a backup tool which preserves NTFS ADS and uses the modified timestamp to decide what to back-up.
- **Warn when setting metadata that won't sync via cloud storage**: If you try to edit metadata in a cloud folder, Opus will warn you that the metadata may not sync to other devices.

### Descriptions

Opus lets you assign descriptions to files using the **Set Description** (and **Edit Metadata**) commands. Descriptions can be stored in three ways:

- Inside some file formats (they become part of the file)
- In an alternate data stream attached to the file (only on NTFS file systems)
- In a separate 'descript.ion' file

The options here control which methods Opus will use.

- **Save decriptions to internal file metadata if possible**: If the file format supports it, Opus will save the description inside the file itself. If turned off, or if the file format doesn't support it, Opus will use NTFS ADS unless the following option is turned on.
- **Fallback to *descript.ion* files instead of NTFS comments**: If this option is turned on, and descriptions can't be stored inside the file itself, they'll be stored using the semi-standard DESCRIPT.ION system, where a file called "descript.ion" is created in the folder to hold the descriptions.
  - **Hide 'descript.ion' comment files when marked as Hidden**: In conjunction with the above option, when the DESCRIPT.ION files have their **H** attributes set, Opus will hide them from the file display (even if other **H**-marked files are not hidden).

### MP3 Files

- **Write APE tags**: When writing metadata to MP3 files, Opus will save tags in APE format as well as ID3v2.
- **Write ID3v1 tags**: When writing metadata to MP3 files, Opus will save an ID3v1 tag as well as ID3v2.
