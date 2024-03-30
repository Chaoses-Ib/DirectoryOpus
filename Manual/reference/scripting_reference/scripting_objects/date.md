# Date

The **Date** object is provided to make it easier to deal with variables representing dates. It converts automatically to an ActiveX *VT_DATE* value and so can function as a drop-in replacement for a scripting language's native date variables. The main advantage is that it retains milliseconds, unlike *VT_DATE* which has a one second resolution. It also provides some utility methods to manipulate dates. The **[Item](item.md)** object** **has a number of properties that returns **Date** objects.

You can create a new **Date** object using the **[DOpusFactory](dopusfactory.md).Date** method.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*date*</td><td>

Returns a *VT_DATE* representing the value of this **Date** object (excluding the milliseconds).
</td></tr><tr><td>
day</td><td>

*int*</td><td>

Get or set the *day* value of the date.
</td></tr><tr><td>
hour</td><td>

*int*</td><td>

Get or set the *hour* value of the date.
</td></tr><tr><td>
min</td><td>

*int*</td><td>

Get or set the *minute* value of the date.
</td></tr><tr><td>
month</td><td>

*int*</td><td>

Get or set the *month* value of the date.
</td></tr><tr><td>
ms</td><td>

*int*</td><td>

Get or set the *milliseconds* value of the date.
</td></tr><tr><td>
sec</td><td>

*int*</td><td>

Get or set the *seconds* value of the date.
</td></tr><tr><td>
wday</td><td>

*int*</td><td>

Get the *day-of-the-week* value of the date.
</td></tr><tr><td>
year</td><td>

*int*</td><td>

Get or set the *year* value of the date.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Add</td><td>
\<int:value\>  
\<string:type\></td><td>

*none*</td><td>

Adds the specified value to the date. The interpretation of the specified value is controlled by the *type* string:

|       |              |
|-------|--------------|
| **l** | milliseconds |
| **s** | seconds      |
| **m** | minutes      |
| **h** | hours        |
| **d** | days         |
| **w** | weeks        |
| **M** | months       |
| **y** | years        |
</td></tr><tr><td>
Clone</td><td>

*none*</td><td>

*object:***Date**</td><td>

Returns a new **Date** object set to the same date as this one.
</td></tr><tr><td>
Compare</td><td>

\<date:other\>  
\[\<string:type\>\]  
\[\<int:tolerance\>\]</td><td>

*int*</td><td>

Compares this date against the *other* date. The return value will be **0** (equal), **1** (greater) or **-1** (less).

The optional *type* string controls how the comparison is performed:

|        |                                                                                                                |
|--------|----------------------------------------------------------------------------------------------------------------|
| **s**  | ignore seconds. If specified, the optional *tolerance* argument specifies the comparison tolerance in seconds. |
| **sD** | ignore seconds, and compensate automatically for daylight savings.                                             |
| **t**  | compare times only                                                                                             |
| **d**  | compare dates only                                                                                             |
</td></tr><tr><td>
Format</td><td>

\[\<string:format\>\]  
\[\<string:flags\>\]</td><td>

*string*</td><td>

Returns a formatted date or time string. The *format* and *flags* arguments are both optional.

If you do not give a *format*, the result will include both date and time, formatted the same as date-time columns in the file display.

If you give a *format* of just **"d"** or **"t"** then the result will be just the date or time part, formatted the same as date or time columns in the file display.

The file display's formats depend on the user's locale and Windows settings. You should use those options if you wish to present a date/time to the user in the way they expect them to look, but not if you need to store them in a specific format.

When using the file display's format (that is, the *format* argument is empty, **"d"** or **"t"**), you can optionally pass one or more case-sensitive flags in the second *flags* argument to override a few settings:

|       |                                                                                                                    |
|-------|--------------------------------------------------------------------------------------------------------------------|
| **N** | Force day names on in dates within the last week. "Today", "Monday", etc.                                          |
| **n** | Force day names off.                                                                                               |
| **S** | Force seconds on in times.                                                                                         |
| **s** | Force seconds off.                                                                                                 |
| **M** | Force milliseconds on in times. (Milliseconds will be zero if the stored time does not have millisecond accuracy.) |
| **m** | Force milliseconds off.                                                                                            |
| **P** | Force time hours to be padded to two digits.                                                                       |
| **p** | Do not force time hours to be padded.                                                                              |

For example, to get just the date, using the user's locale, but with day names forced off:

    myDate.Format("d","n")

To get the date and time, using the user's locale, but with day names forced on and seconds forced off:

    myDate.Format("","Ns")

The *format* can also use the syntax shown in [Codes for date and time](../../command_reference/external_control_codes/codes_for_date_and_time.md), allowing for arbitrary formats. For example,

    myDate.Format("D#yyyy-MM-dd T#HH:mm:ss")

This would return a string like **2023-07-28 15:45:26**.

When explicitly specifying a format, the *flags* argument should not be used and will be ignored.
</td></tr><tr><td>
FromUTC</td><td>

*none*</td><td>

*object:***Date**</td><td>

Returns a new **Date** object with the date converted from UTC (based on the local time zone).
</td></tr><tr><td>
Reset</td><td>

*none*</td><td>

*none*</td><td>
Resets the date to the current local date/time.
</td></tr><tr><td>
Set</td><td>
\<date:newdate\></td><td>

*none*</td><td>

Sets the value of this **Date** object to the supplied date. *newdate* can be:

- Another **Date** object
- A string in the form "yyyymmdd"
- A string in the form "yyyy-mm-dd hh:mm:ss.mmm" (or part thereof)
- A JScript **Date** object
- A unix epoch time value (seconds since 1/1/1970).
- The string "now" (sets to the current time)
</td></tr><tr><td>
Sub</td><td>
\<int:value\>  
\<string:type\></td><td>

*none*</td><td>

Subtracts the specified value from the date. The parameters are the same as for the **Add** method.
</td></tr><tr><td>
ToUTC</td><td>

*none*</td><td>

*object:***Date**</td><td>

Returns a new **Date** object with the date converted to UTC (based on the local time zone).
</td></tr></tbody>
</table>

