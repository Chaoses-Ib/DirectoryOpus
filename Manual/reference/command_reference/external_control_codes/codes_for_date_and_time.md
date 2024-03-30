# Codes for date and time

The following codes are used to pass formatted date and time strings to external programs. They are also quite often used to pass date strings to the internal commands - for example, to create a folder named after the current date, you might use a command like **CreateFolder {date\|yyyyMMdd}**.

<table>
<thead><tr><th>
Code</th><th>
Description
</th></tr></thead><tbody><tr><td>

**{date\|***\<format\>***}**</td><td>
Current date (local time).
</td></tr><tr><td>

**{dateu\|***\<format\>***}**</td><td>
Current date (UTC).
</td></tr><tr><td>

**{time\|***\<format\>***}**</td><td>
Current time (local time).
</td></tr><tr><td>

**{timeu\|***\<format\>***}**</td><td>
Current time (UTC).
</td></tr></tbody>
</table>

The *\<format\>* value is a string consisting of various *tokens* that are used to format the date and time strings. If no format is specified, your default system date and time format is used.

As an example, **{date\|yyyy-MM-dd}** would format the date like *2016-09-22*, and **{time\|HHmmss}** would format the time like *084450*.

While this page is primarily about the **{date}**, **{dateu}**, **{time}** and **{timeu}** codes, the syntax described below is also used in other places where date and time formats are used. The syntax is based on the one Windows uses, with some additions, and should be familiar if you have ever customized your Windows date-time format.

**D#, T# and A# prefixes:** Date formats may begin with **D#**. Time formats may begin with **T#**. Unified formats (those with both date and time fields in them) may begin with **A#**. While these prefixes are optional for **{date}**, **{dateu}**, **{time}** and **{timeu}**, where the format type is implicit, the prefixes are required in situations where a code returns both a date and a time together. For example, when renaming files the **{modified}** code, a file's modified year could be inserted with **{modified\|D#yyyy}**.

**Special flags:** A handful of special flags can appear at the start of the format string, after any **D#**, **T#** or **A#** prefix, to modify how the formatting is performed. Like the main format flags, these are **case sensitive**. If two or more special flag are used at once, their order is not important.

- **I** - **System Invariant Locale:** Your system's language settings (locale) affect date and time formats. For example, the **MMM** and **MMMM** date codes will produce month names in your spoken language. The **tt** time code outputs your locale's versions of "AM" and "PM", which may even be completely missing in places which do not use them (e.g. France). You can override this and use the **system invariant locale** by placing an **I** (capital-i) at the start of the format string. The system invariant locale is similar to the North American locale and produces identical results on all machines and setups. This can be used with both date and time formats. For example, running **{date\|Idd-MMM} {time\|Ihh:mm tt}** on June 23rd at 10:52 PM will always output "23-Jun 10:52 PM".

- **N** - **Day Names:** If you wish for dates within one week to be replaced by day names ("Monday", "Today", "Tomorrow", etc.), similar to the *Show Friendly Dates* Preferences option, begin the date format with an **N** (capital-n). This can only be used with date formats. For example, **{date\|Ndd-MMM-yyyy}** will output "Today", if Opus is running in English. You're unlikely to want day names with **{date}**, but they also work with file timestamps when renaming; e.g. **{modified\|D#Nyyyy-MM-dd}** in the Rename dialog. While you can combine the **I** and **N** flags, they do not interact with each other; day names are always output in the language you have Opus configured to use.

- **M** - **Milliseconds:** If you wish for milliseconds to be included, similar to the *Show Milliseconds* Preferences option, begin the time format with an **M** (capital-m) character. This can only be used with time formats. Milliseconds, when included, will always be added after seconds and padded to three digits. For example, **{time\|MHH:mm:ss}** will return a time similar to "08:45:32.021". If a time value does not have millisecond precision, the milliseconds portion will be zero.

The **date codes** use the following tokens - note that these tokens are case sensitive! The *ISO week* and *ISO year* tokens refer to the [ISO week date system](http://en.wikipedia.org/wiki/ISO_week_date).

<table>
<thead><tr><th>
Date token</th><th>
Description
</th></tr></thead><tbody><tr><td>
d</td><td>
Day of month as a number, with no leading zero for single-digit days.
</td></tr><tr><td>
dd</td><td>
Day of month as a number, with a leading zero for single-digit days.
</td></tr><tr><td>
D</td><td>
Day of week as a number (1 = Sunday, 7 = Saturday).
</td></tr><tr><td>
DD</td><td>
Day of week as a number (1 = Monday, 7 = Sunday).
</td></tr><tr><td>
ddd</td><td>

Day of week as a three-letter abbreviation (e.g. *Wed*).
</td></tr><tr><td>
dddd</td><td>

Day of week as its full name (e.g. *Wednesday*).
</td></tr><tr><td>
w</td><td>
ISO week number, no leading zero.
</td></tr><tr><td>
ww</td><td>
ISO week number, leading zero.
</td></tr><tr><td>
W</td><td>
Simple week number, no leading zero.
</td></tr><tr><td>
WW</td><td>
Simple week number, leading zero.
</td></tr><tr><td>
M</td><td>
Month as a number, no leading zero.
</td></tr><tr><td>
MM</td><td>
Month as a number, leading zero.
</td></tr><tr><td>
MMM</td><td>

Month as a three-letter abbreviation (e.g. *Jan*).
</td></tr><tr><td>
MMMM</td><td>

Month as its full name (e.g. *January*).
</td></tr><tr><td>
y</td><td>

Year as last two digits, but with no leading zero for years less than 10 (e.g. *2009* -\> *9*).
</td></tr><tr><td>
yy</td><td>

Year as last two digits, with a leading zero (e.g. *2009* -\> *09*).
</td></tr><tr><td>
yyyy</td><td>
Year as a four digit number.
</td></tr><tr><td>
Y</td><td>
ISO year as last two digits, no leading zero. (Generally only makes sense in conjunction with ISO week. Do not use if you just want the normal year.)
</td></tr><tr><td>
YY</td><td>
ISO year as last two digits, leading zero. (Generally only makes sense in conjunction with ISO week. Do not use if you just want the normal year.)
</td></tr><tr><td>
YYYY</td><td>
ISO year as four digit number. (Generally only makes sense in conjunction with ISO week. Do not use if you just want the normal year.)
</td></tr><tr><td>
gg</td><td>

Period/era string - ignored if the date to be formatted does not have an associated era.
</td></tr></tbody>
</table>

The **time codes** use the following tokens - these are also case sensitive.

<table>
<thead><tr><th>
Time token</th><th>
Description
</th></tr></thead><tbody><tr><td>
h</td><td>
Hours with no leading zero for single-digit hours, 12 hour clock.
</td></tr><tr><td>
hh</td><td>
Hours with leading zero for single-digit hours, 12 hour clock.
</td></tr><tr><td>
H</td><td>
Hours with no leading zero, 24 hour clock.
</td></tr><tr><td>
HH</td><td>
Hours with leading zero, 24 hour clock.
</td></tr><tr><td>
m</td><td>
Minutes with no leading zero.
</td></tr><tr><td>
mm</td><td>
Minutes with leading zero.
</td></tr><tr><td>
s</td><td>

Seconds with no leading zero. (Includes milliseconds, if the special **M** flag is specified. See above.)
</td></tr><tr><td>
ss</td><td>

Seconds with leading zero. (Includes milliseconds, if the special **M** flag is specified. See above.)
</td></tr><tr><td>
t</td><td>

One-character AM/PM string (e.g. *A* or *P*). See note about locales, above.
</td></tr><tr><td>
tt</td><td>
Multiple-character AM/PM string. See note about locales, above.
</td></tr></tbody>
</table>

