# Virtual File System

As you would know, the *file system* is the technology provided by the operating system that manages files and folders on your disks. It keeps track of where on the physical disk the data that represents a file is stored, maintains a list of filenames and information about files, and generally provides all services relating to creating and accessing disk files.

As well as managing standard files and folders stored on hard drives, flash disks, etc, Opus also provides several *virtual* file systems that are used to access and manage files that aren't stored (at least directly) on traditional media. For example, a Zip archive is a single file stored in the traditional file system, but Opus provides a virtual file system that represents all the files contained within that Zip file. So instead of the traditional way of accessing the contents of an archive (extracting the contents to a folder), you can use the virtual file system to access the contents directly. In general, virtual file systems in Opus behave the same as real ones, and you don't really need to be aware of the distinction between them - other than to know that the functionality exists.

The virtual file systems provided by Opus include:

- **[System virtual folders](/Manual/basic_concepts/virtual_file_system/system_virtual_folders.md)**: Folders like *Computer* and *Desktop* folders are handled natively in Opus.
- **[File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md)**: File Collections are virtual folders that let you create collections of files and folders that are not necessarily located in the one physical location.
- **[Libraries](/Manual/basic_concepts/virtual_file_system/libraries.md)**: Libraries let you join multiple folders together (virtually) and presents a unified view of their contents.
- **[Archives](/Manual/basic_concepts/virtual_file_system/archives.md)**: Opus supports many different archive formats (Zip, RAR, 7-zip, etc) and lets you treat them as if they were normal folders.
- **[FTP](/Manual/basic_concepts/virtual_file_system/ftp.md)**: Lets you access remote FTP sites as if they were local folders.
- **[MTP](/Manual/basic_concepts/virtual_file_system/mtp.md)**: Lets you view the contents of MTP (*Media Transfer Protocol*) compatible devices like phones, tablets and cameras.

Opus has a [plugin system](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_and_vfs_plugins.md) that allows third-party developers to add their own virtual file systems. For example, a plugin might let you access the system registry as if it were a real folder.

More:

[System virtual folders](/Manual/basic_concepts/virtual_file_system/system_virtual_folders.md)  
[File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md)  
[Libraries](/Manual/basic_concepts/virtual_file_system/libraries.md)  
[Archives](/Manual/basic_concepts/virtual_file_system/archives.md)  
[FTP](/Manual/basic_concepts/virtual_file_system/ftp.md)  
[MTP](/Manual/basic_concepts/virtual_file_system/mtp.md)  
[Compatibility Files](/Manual/basic_concepts/virtual_file_system/compatibility_files.md)  
