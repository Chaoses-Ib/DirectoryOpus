\<evalcmd\> URLEncode && string && Encoded/decoded version of *string*. && string && string && Input string to encode or decode. && \[flags\] && string && Optional flags are:

|       |                                                                           |
|-------|---------------------------------------------------------------------------|
| **d** | decode: decode string rather than encode                                  |
| **g** | google: encode for use with Google (space is converted to a **+** symbol) |
| **r** | rfc: encode compliant with RFC (**~.-\_** characters are not encoded)     |

\</evalcmd\>

Encodes or decodes a string using URL-encoding.

//<Example://>

    Output( URLEncode("File Name") );
    --> File%20Name

    Output( URLEncode("File Name", "g") );
    -> File+Name

    Output( URLEncode("File%20Name", "d") );
    -> File Name
