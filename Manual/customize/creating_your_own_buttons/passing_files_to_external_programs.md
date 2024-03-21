# Passing files to external programs

Using Opus as a simple program launcher is nice, but even more useful is the ability to pass the names of files through to programs that you launch. For example, you could configure a button to automatically run Photoshop, passing the names of selected files on the command line. If you then select six image files and click your Photoshop button, they would all open in Photoshop automatically.

![](/Manual/images/media/passing_files.png) 

In the screenshot above, **{allfilepath}** is a special code responsible for passing the names of all selected files on the command line when the program is launched. With this command on a toolbar, you can select one or more image files and click the button to have them loaded into Photoshop - alternatively, you can drag-and-drop the files directly to the button.

Opus lets you pass several different types of information through to external programs, including the names of selected files, the name of the current source folder, strings representing the current date and time, and more. See the [External control codes](/Manual/reference/command_reference/external_control_codes/README.md) section for a full list.
