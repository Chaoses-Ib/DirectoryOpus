# Network Servers

This page affects the servers that appear in the *Network* branch of the folder tree.

- You can enable a server cache, which makes getting a list of servers quicker once it's been done once.
- You can specify servers which should always appear even if Windows fails to find them.
- You can specify servers which should never appear, and also disable the server list altogether in the tree if desired.

The options on this page are:

- **Populate the Network folder with computers found on your network**: Turn this on to enable the enumeration of network servers in the tree.
- **Cache computer list across restarts**: The server list will be cached and saved to disk, to be reloaded next session.
- **Cache computer list until shutdown**: The server list will be cached in memory but not saved to disk.
- **Do not cache computer list**: The server list won't be cached at all; Opus will always ask Windows to enumerate the servers.
- **Exclude these computers**: You can add server names to this field to exclude them from the tree.
- **Always add these computers**: You can add server names to this field to have them always added to the tree.
