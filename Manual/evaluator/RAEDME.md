# Evaluator

The evaluator is a simple parsing engine that understands basic mathematical operations, boolean logic and provides a number of functions to perform number, string and date manipulations and to query information. Because it is much simpler than a full scripting language like JScript, it can be used in a number of places in Directory Opus to provide customisability where full scripting would be too slow.

The evaluator is not (currently) a full-blown programming language - for example, there are no loops, no user-definable functions, no flow control other than *if/elseif/else* type-constructs. Most evaluation expressions will be quite small - often no more than one or two lines.

As an example, imagine you have a file naming system that embeds a job ID, date and a two letter code, and you'd like to view those in separate columns.

    Job-19230-20230605-XE.xlsx

A reasonably simple [script add-in](/Manual/scripting/example_scripts/adding_a_new_column.md) could add columns to show that information, but there are three main disadvantages to that approach:

- Complexity. Even a simple script requires a certain amount of boilerplate code to intialise it and add the columns to Opus, as well as code to actually generate the column data.
- Speed. Full-blown scripts have a certain amount of overhead every time they're called, and when you're calling a script multiple times for potentially hundreds of files, the time overhead can start to become noticeable.
- Locality. Script add-ins reside in external files, and while they can be backed up as part of your Opus configuration, you still have to make sure they're created with the right file extension and placed in the right folder.

Using the evaluator, the above problem can be solved right in the Preferences UI, using the [Evaluator Columns](/Manual/preferences/preferences_categories/file_display_columns/evaluator_columns.md) feature. Columns configured in there use the evaluator to provide their data. Information about each file is provided to the evaluator expression, which can use various functions and operations to manipulate the data and return a result for display to the user.

For example, the evaluation expression to extract the date from the above filename might look like this:

    jobdate = RegEx(name, "Job-(.+)-(.+)-(..).xlsx", "\2");
    jobdate = Left(jobdate, 4) + "-" + Mid(jobdate, 4, 2) + "-" + Right(jobdate, 2);
    return jobdate As date;

Each of the various contexts the evaluator can be used in provides it with a number of values that it can use to calculate a result - in the above example, the value **name** provides the filename of the file in question.

The evaluator provides a number of functions that expressions can call on. In the first line above, the **RegEx()** function is being used to extract the date from the filename.

The result of the expression is returned to the caller as a date (using the **As** operator) - but to convert from a string to a date, the string needs to be in a particular format. The second line of the expression above uses three more functions (**Left()**, **Mid()** and **Right()**) to split up the date string into years, months and days. It then reconstructs it with hyphens between the three parts, leaving it in a format that can be converted to a date.
