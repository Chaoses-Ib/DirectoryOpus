\<evalcmd\> Resolve && path && Resolved path. && path && path && Path to resolve. && \[flags\] && string && The optional flags are:

|       |                                  |
|-------|----------------------------------|
| **j** | Resolve junction/softlink target |
| **s** | Resolve shortcut (.lnk) target   |
| **p** | Resolve paired folder target     |

When resolving a paired folder, the following flags are also available. If specified, a paired folder's options must match the flags.

|       |                                               |
|-------|-----------------------------------------------|
| **d** | Default dual-display folder                   |
| **v** | Default Navigation Lock target                |
| **n** | Turn on Navigation Lock automatically         |
| **y** | Default Synchronize target                    |
| **l** | Always display primary folder at the left/top |
| **u** | Use path even if it doesn't exist             |
| **i** | Ignore the pair                               |
| **g** | Go up to first existing parent                |

\</evalcmd\>

This function primarily resolves aliases and environment variables in the provided *path*.

With the additional flags, it can also resolve the target of shortcuts, junctions and links. It can also be used to find a path's [paired folder](/Manual/basic_concepts/the_lister/navigation/paired_folders.md).

//<Example://>

    Output(Resolve("/onedrive"));
    --> C:\Users\jon\OneDrive

*See also:* [displayname](displayname.md)
