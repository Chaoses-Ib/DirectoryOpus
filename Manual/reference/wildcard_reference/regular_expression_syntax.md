# Regular Expression Syntax

Regular expressions are a more powerful (and therefore complicated) form of wildcard pattern matching. Like [standard pattern matching](pattern_matching_syntax.md), they can be used throughout Opus. Generally, you have to specifically enable the use of regular expressions in a given situation - by default, Opus will assume standard pattern matching. For example, the **[Advanced Rename](/Manual/file_operations/renaming_files/advanced_rename/README.md)** dialog has a regular expression mode that you must select before regular expressions can be used.

One advantage regular expressions have over standard pattern matching is they can enable a form of search and replace in certain functions. As an example, this is used in the **Rename** command. The "search" string is specified as a pattern to match against the original names of files. That pattern can indicate *capture groups* - expressions in the source string that are captured, and can be carried over to the new string (which acts as the "replace" string). As an example, imagine the **Rename** dialog is set to regular expression mode, with the following patterns supplied:

**Old Name**: The (.\*) Backup\\(.\*)  
**New Name**: \1.\2

  
The two **(.\*)** tokens in the *old name* string are capture groups - they "capture" whatever is matched by the expression within the parentheses. In this case, the expression inside the brackets is **.\*** which simply means "match anything". So what this pattern will do is match any filename beginning with *The* and ending in *Backup*, and it will capture the middle of the filename for later use. The second **(.\*)** will capture the file extension. The *new name* string can then re-use the captured text, and this is indicated with the **\1** and **\2** markers. So as an example, the original filename *The Lord Of The Rings Backup.avi* would be renamed to *Lord Of The Rings.avi*. **\1** refers to the first capture group, **\2** to the second, and so on.

If you need the *new name* string to contain a literal \\ use two together. For example, *abc\\xyz* will turn into *abc\xyz*.

When used with the **Rename** command only, the *old name* pattern can be followed with a **\#** character to indicate that the search and replace operation should be repeated multiple times. For example, the following regular expression rename will remove all spaces from the filename:

**Old Name**: (.\*)\s(.\*)#  
**New Name**: \1\2

  
The **\#** causes the search and replace to be repeated until the new name no longer changes. You can also specify a maximum repetition count by appending a number, for example **\#5** at the end would repeat the operation no more than five times.

There are many different variants of regular expression; by default Opus uses what's called *TR1 ECMAScript*. Microsoft has a [page on TR1](http://www.gpsoft.com.au/DScripts/redirect.asp?page=regex) that goes into far more detail than this help file can.

<table>
<thead><tr><th>
Token</th><th>
Description
</th></tr></thead><tbody><tr><td>

**^**</td><td>

**Start of a string**.  
The caret is used to "anchor" the search to the start of the string. If the search is not anchored to either end, the pattern can match a sub-string of the target.

For example:  
**^abc** matches *abc*, *abcdefg*, *abc123*, but not *123abc*  
**abc** also matches// 123abc//
</td></tr><tr><td>

**\$**</td><td>

**End of a string**.  
The dollar sign is used to "anchor" the search to the end of the string. If the search is not anchored to either end, the pattern can match a sub-string of the target.

For example:  
**abc\$** matches *abc*, *endsinabc*, *123abc*, but not *abc123*  
**^abc(.\*)123\$** matches *abc123*, *abcxyz123*, but not *abcxyz123def*
</td></tr><tr><td>

**.**</td><td>

**Any single character**.  
The period (full stop) is used to match any single character.

For example:  
**a.c** matches *abc*, *aac*, *acc*, *adc* but not *acd*
</td></tr><tr><td>

\*</td><td>

**0 or more of previous expression**.  
Matches zero or more occurrences of the previous expression. Combine with **.** to form the "match anything" token (**.\***).

For example:  
**ab\*c** matches *ac*, *abc*, *abbc*, *abbbc*, ...  
**a.\*c** matches *ac*, *abc*, *a123456c*, *aanythingc*, ...  
**.\*** matches anything
</td></tr><tr><td>

**+**</td><td>

**1 or more of previous expression**.  
Matches one or more occurrences of the previous expression.

For example:  
**ab+c** matches *abc*, *abbc*, *abbbc* but not *ac*
</td></tr><tr><td>

**?**</td><td>

**0 or 1 of previous expression**.  
Matches either zero or one occurrence of the previous expression.

For example:  
**ab?c** matches *ac*, *abc* but not *abbc* or *abbbc*
</td></tr><tr><td>

**\|**</td><td>

**Alternation (logical *or*).**  
The vertical bar is used to separate two or more characters or expressions, any of which may match.

For example:  
**a\|b** matches *a* or *b*  
**a(b\|c)d** matches *abd* or *acd*  
**(bill\|ted)** matches *bill* or *ted*
</td></tr><tr><td>

**{}**</td><td>

**Quantifier**.  
Braces are used to indicate that the preceding expression must match an exact number of times.

For example:  
**ab{2}c** matches *abbc*, but not *abc* or *abbbc*  
**a.{4}z** matches *abcdez*, *a1234z*, *afourz*, *aaaaaz*, etc.
</td></tr><tr><td>

**\[\]**</td><td>

**Character set**.  
Matches any single character in the set of specified characters.  
You can specify the character set as individual characters (e.g. **\[abdfg\]**) or as a range of characters (e.g. **\[a-j\]**) or as multiple ranges.

For example:  
**\[abc\]** matches either *a*, *b* or *c*  
**\[af-j\]** matches either *a*, *f*, *g*, *h* or *j*  
**\[a-dh-kq-\]** matches *a*, *b*, *c*, *d*, *h*, *i*, *j*, *k*, or any character from *q* onwards  
**IMGP\[0-9\]{4}.jpg** matches *IMGP0158.jpg* (or any other four-digit number).
</td></tr><tr><td>

**\[^\]**</td><td>

**Negative character set**.  
Matches any character **not** in the set of specified characters. See **\[\]** for information on how the set is defined.

For example:  
**\[^pqr\]** matches any character except *p*, *q* or *r*
</td></tr><tr><td>

**()**</td><td>

**Expression / capture group**.  
Parentheses are used to combine multiple characters into an expression. When used in a "search and replace" like Advanced Rename, they also mark capture groups - see above for a discussion of these.

For example:  
**a\|bc** matches *ac* or *bc*, whereas  
**a\|(bc)** matches *a* or *bc*
</td></tr><tr><td>

**\\**</td><td>

**Escape character**.  
The backslash is used to escape token characters in order to match those characters literally.  
When used before a non-token character, it is used to indicate the following special escape characters:  
\<WRAP\>

|        |                                                                                                            |
|--------|------------------------------------------------------------------------------------------------------------|
| **\t** | tab character (\$09)                                                                                       |
| **\r** | carriage return (\$0d)                                                                                     |
| **\v** | vertical tab (\$0b)                                                                                        |
| **\f** | form feed (\$0c)                                                                                           |
| **\n** | new line (\$0a)                                                                                            |
| **\e** | escape (\$1b)                                                                                              |
| **\x** | matches an ASCII character specified as a two-digit hexadecimal number, e.g. **\x20** matches a space      |
| **\u** | matches a Unicode character specified as a four-digit hexadecimal number, e.g. **\u0020** matches a space. |

\</WRAP\>\<wrap clear/\>

It is also used to mark several character classes, which are shorthand ways to specify various common **\[\]** character sets (see below).

For example:  
**a\|b** matches *a* or *b*, whereas  
**a\\b** matches *a\|b\\* **a\t** matches *a* followed by a tab character, whereas  
**a\\t** matches *a\t*
</td></tr><tr><td>

**\w**</td><td>

**Word character**.  
Matches any word character. Equivalent to **\[a-zA-Z_0-9\]**.

For example:  
**^\w+\[0-9\]{4}.jpg** matches *IMGP0158.jpg* (or any other four-digit number preceded by at least one other word character).
</td></tr><tr><td>

**\W**</td><td>

**Non-word character**.  
Matches any non-word character, equivalent to **\[^a-zA-Z_0-9\]**.
</td></tr><tr><td>

**\s**</td><td>

**Space character**.  
Matches any whitespace character. Equivalent to **\[ \f\n\r\t\v\]**.
</td></tr><tr><td>

**\S**</td><td>

**Non-space character**.  
Matches any non-whitespace character. Equivalent to **\[^ \f\n\r\t\v\]**.
</td></tr><tr><td>

**\d**</td><td>

**Digit character**.  
Matches any decimal digit. Equivalent to **\[0-9\]**.
</td></tr><tr><td>

**\D**</td><td>

**Non-digit character**.  
Matches any non-decimal digit. Equivalent to **\[^0-9\]**.

For example:  
**^\D+\d{4}.jpg** matches *IMGP0158.jpg* (or any other four-digit number preceded by at least one non-digit character).
</td></tr></tbody>
</table>

