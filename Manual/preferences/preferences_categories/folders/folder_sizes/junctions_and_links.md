# Junctions And Links

This page lets you configure how junctions (and softlinks) are handled when calculating folder sizes.

- **Ignore junctions below a folder when calculating its size**: When calculating the size of a folder (either automatically or manually), this option causes Opus to ignore any junctions or softlinks within the folder.
- **Don't calculate size of junctions themselves**: Stops Opus automatically calculating the size of any links or junctions that point to folders - only "real" folders would have their size calculated automatically. You can always manually calculate a junction's size using the \<ib:inline-code\>`GetSizes`\</ib:inline-code\> command.
