# File System

These options control how Opus handles [virtual folders](../virtual_folders/README.md) that also have an underlying "real" disk folder behind them. Windows contains several folders like this - the *Desktop* is one, but others include the *Fonts* folder (usually *C:\Windows\Fonts*) and the *Global Assembly Cache* folder (usually *C:\Windows\Assembly*). These folders can be displayed in Opus in two different ways - as the underlying disk folder, in which case you will see all files in that folder, or as a virtual folder, in which case you will see the virtualized view that Windows provides.

*Fonts as a virtual folder*  
![](/Manual/images/media/13/fonts_virtual.png)  

*Fonts as a real folder*  
![](/Manual/images/media/13/fonts_real.png)

The above screenshots show the difference between the virtualized and "real" views of the Fonts folder. You can choose from the following options:

- **Treat all "virtual filesystem folders" as virtual**: All such folders will be displayed in their virtualized forms.
- **Treat all virtual folders as real**: All such folders will be displayed as the real underlying folder. Note that this only applies to virtual folders that actually do have an underlying disk folder - some "purely virtual" folders like *Network* will always be virtual.
- **Treat specific virtual folders as real**: This option lets you specify exactly which folders should be displayed as real. For example, you could set the *Fonts* folder to always show as real but all other such folders will be displayed as virtual.
