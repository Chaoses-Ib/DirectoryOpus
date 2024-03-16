# Virtual Folders

This section lets you configure how Opus handles certain [virtual folders](/Manual/basic_concepts/virtual_file_system/system_virtual_folders.md). These are folders that do not relate to a physical location on a disk - that is, they can not be represented by a traditional path like *C:\Users\\* There are many virtual folders provided by Windows - some common examples are *This PC* (or *Computer* under Windows 7), the *Desktop*, *Network* and so on. Third parties can also implement virtual folders via so-called "namespace shell extensions".

For most virtual folders, Opus provides a display of the folder by "hosting" Explorer within the file display. This lets you see the folder and interact with it in the same way as you would in Explorer itself (primarily via drag and drop, cut and paste, and context menus).

For the two most commonly used virtual folders - *This PC* and *Desktop* - Opus has the option of providing its own display (known as "native display") instead of hosting Explorer. The advantage of this is that then the full gamut of Opus functionality is available, including folder formats, configurable colors and images, and (for *Desktop*) Opus commands like Advanced Rename, etc. For the most part the Opus-provided displays of these folders will look exactly the same as the hosted form, so you may not even realise it is Opus and not Explorer providing the display.

##### When hosting Explorer

- **Enable background images**: With this option on, Opus will try to use your background image settings when it is displaying a [virtual folder](virtual_folders/RAEDME.md) that's implemented by Explorer. As these folders are provided by the operating system and Opus merely hosts them as a container, it won't necessarily work!
- **Enable custom fonts**: With this option on, your choice of File Display font will be applied to virtual folders in addition to the normal folders which Opus handles itself. Virtual folders are handled by Windows, or sometimes third-party components, and are largely outside of Opus's control. Opus can ask them to use a different font, but this can result in cosmetic issues or even crashes. If you run into problems using virtual folders, or when opening new windows or tabs, you should turn this option off again.
