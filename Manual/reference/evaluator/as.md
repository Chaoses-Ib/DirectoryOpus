\<pageheader\>\<i\>varname\</i\> As \<i\>type / format\</i\>\</pageheader\>

The **As** operator performs two functions - conversion and formatting.

##### Conversion: varname As type

Converts the variable *varname* to the specified *type*. Valid types are:

|        |                                 |
|--------|---------------------------------|
| bool   | boolean (true or false)         |
| int    | signed 32-bit integer           |
| uint   | unsigned 32-bit integer         |
| int64  | signed 64-bit integer           |
| uint64 | unsigned 64-bit integer         |
| double | double-precision floating point |
| date   | date/time                       |
| str    | string                          |
| path   | path                            |

When converting from a string to a date, valid input formats are:

- YYYY-MM-DD
- YYYY-MM-DD HH:MM:SS
- HH:MM:SS

Times must be in 24-hour format, minutes and seconds are optional. If a time is specified on its own, today's date is assumed.

##### Formatting: varname As format

Formats the variable *varname* using the specified formatting code.

Various formatting operations are available.

- Date/time values can be formatted using the **D#**, **T#** and **A#** [prefix codes](../command_reference/external_control_codes/codes_for_date_and_time.md)
- File size values using the codes shown below
- Zero-padding to *p* places using **\#p** or **%0p**
- Right-justify to *p* places using **%p**
- Left-justify to *p* places using **%-p**
- Internal-justify:
  - For negative numbers to *p* places using **%\_p**
  - For positive numbers **%+p**
- Limit to *p* decimal places using **%.p**
- Zero-pad to *p* decimal places with **%.0p**
- Convert to hexadecimal using **%x** (lowercase) or **%X** (uppercase)

Where it makes sense the above codes can be combined, e.g. **%\_+8** would internal-justify a number to 8 places whether it was positive or negative.

#### File size format

Use ***value* as size** to automatically format a number as a file size using the default settings. You can also use the following keywords to control the units:

|       |                                                                             |
|-------|-----------------------------------------------------------------------------|
| size  | Automatic (bytes/KB/MB etc) with user-configured decimal/binary unit option |
| szt   | Automatic with traditional units (1 KB = 1024 bytes)                        |
| szi   | Automatic with binary units (1 KiB = 1024 bytes)                            |
| szd   | Automatic with decimal units (1 KB = 1000 bytes)                            |
| bytes | Bytes                                                                       |
| kb    | Kilobytes, traditional units                                                |
| mb    | Megabytes, traditional units                                                |
| gb    | Gigabytes, traditional units                                                |
| tb    | Terabytes, traditional units                                                |
| pb    | Petabytes, traditional units                                                |
| kib   | Kilobytes, binary units                                                     |
| mib   | Megabytes, binary units                                                     |
| gib   | Gigabytes, binary units                                                     |
| tib   | Terabytes, binary units                                                     |
| pib   | Petabytes, binary units                                                     |
| kbd   | Kilobytes, decimal units                                                    |
| mbd   | Megabytes, decimal units                                                    |
| gbd   | Gigabytes, decimal units                                                    |
| tbd   | Terabytes, decimal units                                                    |
| pbd   | Petabytes, decimal units                                                    |

- You use **%.*x*** to specify the number of decimal places, e.g. **%.3mib**. or **%.03kb** to zero-pad
- Use **%^** to round up to the nearest kilobyte, e.g. **%^kb**.
- Use **%0** in front of the "automatic" keywords to force 0 bytes to be formatted as kilobytes

  
//<Example://>

    d = "2023-09-23" as date;
    Output(d as "D#dd-MMM-yyyy");
    --> 23-Sep-2023

    i = 1 as double / 3;
    Output(i as "%-.3");
    --> 0.333

    i = 183743933;
    output(i as "%.3kb");
    --> 179,437.435 KB

*See also:* [format](format.md)
