# Time Shifting

A time shift string can be used in various places to perform relative changes to dates and times. Some places you can use these include:

- In the [metadata editor](../.md), in various timestamp properties such as **Date created**, **Date modified**, **Date digitized** and **Date taken**.
- In the [Change Attributes and Timestamps](../changing_attributes.md) dialog.
- Programmatically with the `SetAttr` command.

The format of the time shift string is either:

- `<date-shift> <time-shift>` when you want to adjust both date and time, or
- `<time-shift>` when you only want to modify the time.

When only one string is given it's assumed to be the `<time-shift>` string, which means you can't adjust just the date without specifying a time value as well (although the time value given can be 0 which means the time won't actually change).

The `<date-shift>` portion has three allowable formats:

- `[+-]Y:M:D` - year:month:day, with an optional positive or negative modifier
- `[+-]M:D` - month:day, with an optional positive or negative modifier
- `[+-]D` - day, with an optional positive or negative modifier

The `<time-shift>` portion has three allowable formats as well:

- `[+-]H:M:S` - hours:minutes:seconds, with an optional positive or negative modifier
- `[+-]H:M` - hours:minutes, with an optional positive or negative modifier
- `[+-]H` - hours, with an optional positive or negative modifier

What this means is that you can add or subtract years, months, days, hours, minutes and seconds to or from the current date value.

For example, say you had just taken 100 digital photos, when you suddenly realize you'd forgotten to adjust your camera's clock for the beginning of daylight savings. You could fix this by specifying `+1` (or just `1`, since **+** is the default) for the time shift string. By the above rules,

- Only one string (`+1`) is supplied, which means it's the `<time-shift>` value
- Only one number (`1`) is supplied, which means it's the **H** value - for hour

This would add one hour to the current timestamp of the selected images.

Here are a few other examples:

- `-1:0:0 0` - subtract one year from the timestamps
- `+8:30` - add eight and a half hours to the timestamp
- `+3 -0:45` - add three days, subtract 45 minutes from the timestamp
