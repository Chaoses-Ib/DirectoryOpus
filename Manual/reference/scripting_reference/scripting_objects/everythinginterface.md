# EverythingInterface

If [Everything](/Manual/additional_functionality/everything_integration.md) by voidtools is installed, this provides an interface that lets you easily communicate with Everything from a script. You can start and stop Everything, query its status, send it arbitrary commands and query its database.

Create an **EverythingInterface** object via the **[DOpus](dopus.md).Create** factory method.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
autorun</td><td>

*bool*</td><td>

Returns True if Everything is configured to auto-start (via the **[Miscellaneous / Advanced Options](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** Preferences page).
</td></tr><tr><td>
indexed</td><td>

*int*</td><td>

Returns a value indicating which attributes Everything is configured to index. This is a bitmask made up of the following values:

|     |               |
|-----|---------------|
| 2   | File sizes    |
| 4   | Folder sizes  |
| 8   | Created date  |
| 16  | Modified date |
| 32  | Accessed date |
| 64  | Attributes    |
</td></tr><tr><td>
isrunning</td><td>

*bool*</td><td>
Returns True if Everything is currently running.
</td></tr><tr><td>
roots</td><td>

*object:***[StringSet](stringset.md)**</td><td>
Returns a set representing the drive roots that Everything has indexed.
</td></tr><tr><td>
version</td><td>

*string*</td><td>
Returns Everything's version number.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Indexed</td><td>

\<string:path\></td><td>

*bool*</td><td>
Returns True if the specified path is indexed by Everything.
</td></tr><tr><td>
Query</td><td>

\<query\>  
\<search_flags\>  
\<request_flags\>  
\<sort_type\>  
\<max_results\>  
\<offset\>  
\<timeout\></td><td>

**[Vector](vector.md)** of **[EverythingResult](everythingresult.md)**</td><td>

Sends the specified query string to Everything. Returns the results as a [Vector](vector.md) of [EverythingResult](everythingresult.md) objects.

All arguments after the query string are optional, and represent flags provided by the Everything API.

*search_flags* should be a bitmask representing the `EVERYTHING_IPC_xxx` search flags, or a string containing one or more of the following characters. Defaults to `0` if not provided.

|     |                                                                                           |
|-----|-------------------------------------------------------------------------------------------|
| c   | match case (`EVERYTHING_IPC_MATCHCASE`)              |
| w   | match whole words (`EVERYTHING_IPC_MATCHWHOLEWORDS`) |
| p   | match path (`EVERYTHING_IPC_MATCHPATH`)              |
| r   | regex (`EVERYTHING_IPC_REGEX`)                       |
| a   | match accents (`EVERYTHING_IPC_MATCHACCENTS`)        |

*request_flags* should be a bitmask representing the `EVERYTHING_IPC_QUERY2_REQUEST_xxx` request flags, or a string containing one or more of the following characters. Defaults to `EVERYTHING_IPC_QUERY2_REQUEST_FULL_PATH_AND_NAME` if not provided.

|     |                                                                                                                                      |
|-----|--------------------------------------------------------------------------------------------------------------------------------------|
| n   | name (`EVERYTHING_IPC_QUERY2_REQUEST_NAME`)                                                     |
| p   | path (`EVERYTHING_IPC_QUERY2_REQUEST_PATH`)                                                     |
| f   | full path and name (`EVERYTHING_IPC_QUERY2_REQUEST_FULL_PATH_AND_NAME`)                         |
| x   | extension (`EVERYTHING_IPC_QUERY2_REQUEST_EXTENSION`)                                           |
| s   | size (`EVERYTHING_IPC_QUERY2_REQUEST_SIZE`)                                                     |
| c   | created (`EVERYTHING_IPC_QUERY2_REQUEST_DATE_CREATED`)                                          |
| m   | modified (`EVERYTHING_IPC_QUERY2_REQUEST_DATE_MODIFIED`)                                        |
| e   | accessed (`EVERYTHING_IPC_QUERY2_REQUEST_DATE_ACCESSED`)                                        |
| a   | attributes (`EVERYTHING_IPC_QUERY2_REQUEST_ATTRIBUTES`)                                         |
| r   | run count (`EVERYTHING_IPC_QUERY2_REQUEST_RUN_COUNT`)                                           |
| R   | date run (`EVERYTHING_IPC_QUERY2_REQUEST_DATE_RUN`)                                             |
| M   | date recently changed (`EVERYTHING_IPC_QUERY2_REQUEST_DATE_RECENTLY_CHANGED`)                   |
| N   | highlighted name (`EVERYTHING_IPC_QUERY2_REQUEST_HIGHLIGHTED_NAME`)                             |
| P   | highlighted path (`EVERYTHING_IPC_QUERY2_REQUEST_HIGHLIGHTED_PATH`)                             |
| F   | highlighted full path and name (`EVERYTHING_IPC_QUERY2_REQUEST_HIGHLIGHTED_FULL_PATH_AND_NAME`) |

*sort_type* should be one of the `EVERYTHING_IPC_SORT_xxx` constants (the numeric value). Defaults to `0` if not provided.

*max_results* lets you limit the number of results returned. Defaults to the *everything_max_results* advanced Preferences value if not provided.

*offset* specifies the result offset. In conjunction with *max_results* this lets you query large datasets without having to deal with all the results at once.

*timeout* specifies a timeout in milliseconds. Defaults to `1000` if not provided.
</td></tr><tr><td>
RunCountGet</td><td>

\<string:file\></td><td>

*int*</td><td>
Returns the run count for the specified file.
</td></tr><tr><td>
RunCountInc</td><td>

\<string:file\></td><td>

*int*</td><td>
Increments the run count for the specified file and returns the new count.
</td></tr><tr><td>
RunCountSet</td><td>

\<string:file\>  
\<int:count\></td><td>

*bool*</td><td>
Sets the run count for the specified file to the value provided. Returns True on success.
</td></tr><tr><td>
SendCmd</td><td>

\<int:command\>  
\[\<int:data\>\]</td><td>

*int*</td><td>

Sends the specified command to Everything and returns its response. The commands are documented in the Everything API SDK (e.g. 401 equates to `EVERYTHING_IPC_IS_DB_LOADED` and returns 1 to indicate Everything's database is loaded).
</td></tr><tr><td>
Start</td><td>

*none*</td><td>

*bool*</td><td>
Starts Everything if it's not already running and Opus has been configured to auto-start it.
</td></tr><tr><td>
Stop</td><td>

*none*</td><td>

*bool*</td><td>
Stops Everything (tells it to quit).
</td></tr></tbody>
</table>

