# Security

Options that control file permissions and security settings when copying files. These options can be overridden by various arguments for the `Copy` command. Turning them on may impose an extra per-file overhead in some cases.

- **Copy file ownership**: This option copies file owner information, assuming the source and destination filesystems support the Windows concept of file owners. Normally, newly copied files will be owned by the user making the copy, but with this option on they would be owned by original file's owner. Because setting the file owner requires administrator permissions, this may cause a UAC prompt to be displayed if the original owner is not the current user. This can be overridden by the `Copy` command's `COPYOWNER` argument.
  - **Local drives only**: File ownership will only be copied on local drives, not for network locations.

- **Copy security permissions when copying, or moving between drives**: This reproduces the security permissions of each file on each respective copy, assuming the source and destination filesystems support Windows file permissions. When turned off, copied files inherit the permissions of the folders they are copied into, which is usually what you want. This can be overridden by the `COPYSECURITY` argument.

##### Update permissions/encryption to match destination when moving on same drive

Normally, when you move a file on the same drive (an operation that doesn't involve a new file being created), it will keep its original permissions. This can cause problems when you move files into a folder with different permissions. For example, if you moved a private file into a shared public folder, the file would keep its original permissions and not be accessible to users of the share. Turning on this option causes Opus to update the permissions of the moved file to match the folder it has been moved into.

Similarly, the moved file will be encrypted or decrypted if needed to match the normal state of the target folder. (This is about filesystem-level encryption, as provided by Windows/NTFS and controlled via a file or folder's standard Properties dialog, and not any other type of encryption.)

This can be overridden by the `Copy` command's `UPDATESECURITY` argument.

- **Update permissions even if it would trigger a UAC prompt**: \<WRAP\>When turned on, if a file was moved without elevation and there is an access-denied error when updating its permissions, Opus will display a UAC prompt and try to update the permissions again with elevation. When turned off, no UAC prompt will be displayed and updating permissions will be skipped if there is an access denied error.

Typically, and especially on network drives, if a folder is permissioned to allow you to move its contents without elevation then it will either allow you to modify the permissions without elevation as well (so no UAC prompt is required) or will block you from modifying permissions at all (so it will still fail even if you elevate, and the UAC prompt is just an annoyance).

If an access-denied error happens when moving the actual file (or one of the previous files), UAC elevation will still always be attempted and the elevation context will be re-used for updating file permissions without requiring a second UAC prompt.\</WRAP\>

- **Change ownership to match destination**: When turned on, Opus will attempt to set the file's owner to the account which owns the destination folder. When turned off, the owner will stay as-is when files are moved on the same drive. If the owner is not changed, extra permissions may be granted to it (e.g. if the destination folder passes rights to *CREATOR OWNER* on child files)

- **Preserve explicit (non-inherited) permissions**: When turned on, Opus will preserve any explicit, non-inherited permissions set on the file, merging them with the new permissions inherited from the destination folder; only old inherited permissions will be removed. When turned off, all old permissions will be removed and replaced by permissions inherited from the destination.
