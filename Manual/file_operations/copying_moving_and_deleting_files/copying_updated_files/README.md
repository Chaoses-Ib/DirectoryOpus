# Copying Updated Files

There are two different ways to copy updated files (that is, copy newer files over the top of older ones) automatically:

- The **Update All** and **Update Existing** commands offer a simple one-way form of file synchronization
- The **[Synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md)** tool offers a full, two-way synchronization system, that lets you see and control which files are going to be copied or deleted

### The "Update" commands

The **Update All** and **Update Existing** commands are found in the drop-down menu attached to the **Copy Files** button on the default toolbar.

These two commands are variants of the standard **Copy Files** command, and rely on the [source and destination](/Manual/basic_concepts/source_and_destination.md) concept. Selected files will be copied from the current source file display to the destination folder, under the following conditions:

- **Update All**: Files will be copied if they
  - Don't already exist in the destination, **or**
  - Do exist in the destination, but are a different size or older than the files being copied

- **Update Existing**: Files will be copied if they
  - Do exist in the destination, **and**
  - Are a different size or older than the files being copied (this rule can be modified, see below).

Files that don't match those conditions are skipped. You can modify the test conditions using the arguments for the internal **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command:

- Update All: The **UPDATETOLERANCE** argument can be used to control how different a timestamp can be before it is considered as "older".
- Update Existing: As well as **UPDATETOLERANCE**, the **UPDATEEXISTING** argument can be used to ignore file size or date for the comparison

See the description of the internal **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command for details on these arguments, and the [Customize](/Manual/customize/README.md) section for information on configuring toolbar buttons.

More:

[Synchronize](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md)  
