# FTP

These options let you (sort of) edit files directly on FTP sites. When you double-click on a file (say, a Word document) on an FTP site, Opus will download it to a local temporary copy, and then open the local copy in Word. If you make changes to the file and save it to disk, Opus can detect this and re-upload the new version of the file to the FTP site automatically.

- **Re-upload modified files to FTP sites**: Turn this on to enable automatic re-uploading.
- **Change detection**: There are a number of different options for this monitoring:
  - **Check for changes when process exits**: This involves the lowest system overhead. Opus waits for the program it launched to exit, and then checks the temporary file for changes. Unfortunately this option is not always reliable - many programs when run simply send a message to an existing instance of themselves and then exit immediately. If you have this option on and you find Opus isn't detecting your changes, try one of the other options.
  - **Monitor file until it changes (once)**: With this option, Opus will continually monitor the temporary file until it changes exactly once. Subsequent changes will not be detected.
  - **Monitor file for...**: When you select this option a time field appears next to it. Opus will monitor the file for any changes that occur within the specified time. When the timer expires, Opus will stop monitoring the file.
  - **Monitor indefinitely**: Opus will monitor the file for any changes, and keep monitoring it until Opus itself exits (or you restart or shutdown the computer).

- **Ask before uploading**: With this option on, Opus will ask you before it re-uploads a file it has noticed a change in. If this is turned off the file will be uploaded automatically.

- **Use file checksum to detect modifications**: Normally Opus detects a file has changed by comparing its timestamp against the original, but with this option on Opus will also calculate "before" and "after" checksums and compare those. This prevents unnecessary uploads of files that may have been re-saved but haven't actually changed.
