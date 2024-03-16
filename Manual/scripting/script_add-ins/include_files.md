# Include Files

There are two ways to split a large (often unwieldy) single script file into multiple files.

- Script include files
- Script [Modules](modules.md)

The two are similar in concept, however where a module is designed as a way to split an individual script into multiple files, include files are designed more for sharing code between multiple scripts.

Say you have a bunch of utility functions that you like to use repeatedly. You could copy them into every individual script that uses them, but that means your script files are larger (and more complicated) than they need to be, and keeping them all updated is difficult.

If instead you keep your utility functions in an include file, you can then *include* that file into other scripts - automatically gaining access to the functions within it, but with only one copy of the code needed.

##### Include file requirements

The easiest way to create an include file is using the [script editor](../script_editor/RAEDME.md).

While include files are just script files like any other, there are a few important differences to normal scripts:

- Their filename must begin with **inc\_** (e.g. *inc_myutils.js*).
- They must be in the same language as the scripts that will use them (you can't include a .js file from a .vbs script, for example).
- The [OnInitIncludeFile](/Manual/reference/scripting_reference/scripting_events/oninitincludefile.md) event can be implemented to provide information about the include file to Opus, although this is optional.

Include files can be *private* or *shared*. Private include files, when bundled into a [script package](script_package.md), can only be used by scripts in that package. Shared include files can be used by all installed Opus scripts. To mark an include file as shared, the `OnInitIncludeFile` event must be implemented.

##### Using include files

To use an include file from another script, use the `@include` directive at the top of the script file, For example,

`@include inc_myutils.js`

You can also specify a minimum version for the include file. This only works if the include file has specified a version by implementing the `OnInitIncludeFile` event.

`@include inc_myutils.js:1.2`

You can also select include files from the [script editor](/Manual/scripting/script_editor/RAEDME.md).
