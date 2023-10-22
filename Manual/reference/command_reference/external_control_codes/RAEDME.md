# External control codes

The external control codes are used to pass information like the names of selected files to external programs. For example, the command **notepad.exe {f}** would launch Notepad, and pass the name of the first selected file as an argument on its command line.

External control codes can (despite the name) also be used with the internal commands. For example, the command **CreateFolder {date\|yyyyMMdd}** will create a new folder automatically named after the current date.

Most control codes have both a short and a long form. The short form requires less typing and produces a smaller function definition, while the long form is more descriptive and may make the function more understandable. Note that, unlike the arguments for internal commands, the external control codes are case-sensitive.

See the page on [passing files to external programs](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md) for more information about the external control codes.

More:

[Codes for passing filenames](/Manual/reference/command_reference/external_control_codes/codes_for_passing_filenames.md)  
[Codes for passing paths](/Manual/reference/command_reference/external_control_codes/codes_for_passing_paths.md)  
[Codes to display dialogs](/Manual/reference/command_reference/external_control_codes/codes_to_display_dialogs.md)  
[Codes for date and time](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.md)  
[Codes for clipboard and variables](/Manual/reference/command_reference/external_control_codes/codes_for_clipboard_and_variables.md)  
