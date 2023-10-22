\<evalcmd\> Replace && string && Returns the result of the replace operation. && string && string && Input string to search. && search && string && Sub-string to search for. && replace && string && String to replace the sub-string with. && \[start\] && int && Position to start the search at (default is **0** meaning the beginning of the string). && \[count\] && int && Maximum number of replacements (default is **-1** meaning no limit). && \[case\] && bool && Set to **True** to make the search case-sensitive. \</evalcmd\>

Searches the input *string* for the *search* sub-string and replaces it with *replace* if found.

//<Example://>

    Output( Replace("Hello there!", "e", "a") );
    --> hallo thara!
