# Scripting Reference

The Directory Opus scripting interface is built around ActiveX. The advantage of this is that Opus scripting is *language neutral* - you can use any ActiveX scripting language you have installed on your machine. Windows ships with **VBScript** and **JScript** interpreters, and you can add additional languages from third-party providers (e.g. Perlscript, Python, etc).

The scripting interface is presented as a number of *Objects* and *Events*.

- *[Objects](/Manual/reference/scripting_reference/scripting_objects/README.md)* are created by a script, or provided to a script by Opus, and have defined methods and properties that allow you to interact with Opus.
- *[Events](/Manual/reference/scripting_reference/scripting_events/README.md)* are functions provided by a script, that Opus will invoke under certain conditions. For example, the *OnBeforeFolderChange* event is fired before the folder is changed in a Lister.
