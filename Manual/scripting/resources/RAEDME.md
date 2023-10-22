# Resources

You may have noticed in the section on [Script dialogs](script_dialogs/RAEDME.md) that scripts can have “resources” associated with them. This is XML-formatted data that provides resources to the script but doesn’t actually form part of the script code.

There are two types of script resource currently in use, dialogs and strings. When you use the command editor to design your script, the resources are split out onto a separate tab to make it easier to work with. For a *Script Add-in*, or when using the *CLI* in script mode, there is no Resources tab. Instead, script resources can be defined in two ways:

- Script resources can be included at the end of the script code itself. A separator line marks the boundary between script code and resources, like this:  `If BlahBlah Then
  BlahBlah Blah
  End If
  ==SCRIPT RESOURCES
  <resources>
  <resource name="blah1" type="dialog">
  <dialog blah blah>
  </dialog>
  </resource>
  <resource name="blah2" type="dialog">
  <dialog blah blah>
  </dialog>
  </resource>
  <resource type="strings">
  <strings lang="blah">
  <string id="blah" text="Blah!" />
  </strings>
  </resource>
  </resources>`

Everything before the line ==SCRIPT RESOURCES is considered part of the script code, and everything after it is the XML-formatted resources.

- Script resources can be loaded from an external file, or a raw XML string, using the **[Script](/Manual/reference/scripting_reference/scripting_objects/script.md).LoadResources** method. Note that if the script is included in a package the resource file must have *.odxml* as a file extension.

More:

[String Resources](/Manual/scripting/resources/string_resources.md)  
