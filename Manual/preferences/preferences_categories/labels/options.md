# Options

This page contains general options relating to [labels](/Manual/file_operations/labels.md).

##### Enable label storage in the file system

There are two ways that Opus can store labels that are assigned to a specific file or folder (as opposed to a wildcard or filter-based label).

- In the file system: On an NTFS-formatted drive (which is the most common type of file system these days) the label information is stored in an alternate data stream with the actual file itself. The advantage of this is that when you copy, move or rename the file, the label goes with it.
- In your configuration: On other file systems, or if the option to store labels in the file system is turned off, the full filename and path of labeled files is stored in your Opus configuration. That means that if you move a labeled file, the label will not go with it.

If **Enable label storage in the file system** is turned on, Opus will try to store labels in NTFS data streams, and only fall back on your configuration if necessary. The **Warn if labels can't be stored in the file system** will make Opus show you a warning if this happens.

##### Apply wildcard and filter labels to explicitly labelled files

By default explicitly applied labels override wildcard labels, but this option lets wildcard labels stack on top of explicitly-assigned ones.
