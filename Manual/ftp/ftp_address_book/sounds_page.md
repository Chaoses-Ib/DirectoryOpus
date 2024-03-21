# Sounds Page

The **Sounds** page lets you enable sound effects to be played for various FTP-related events when connected to a site in the [FTP Address Book]().

The events that you can assign sound effects to are:

- **Login success**: This sound is played whenever a successful connection to the site is established.
- **Login failure**: This sound is played when a connection to the site fails for some reason.
- **Copy success**: This sound is played whenever a file copy operation succeeds.
- **Copy failure**: This is played when a file copy operation fails for some reason.
- **Error**: This sound is played whenever any other error occurs (i.e. not one of the other error conditions with a specific sound).
- **Lose connection**: This sound is played whenever the connection to a site is lost.
- **Timeout**: This sound is played when a network timeout occurs.

Some of the sound effects also let you configure an **Activation Time** value. This lets you specify a minimum time threshold for the event. If the event occurs (either completes or fails, as appropriate) in less than the configured number of seconds, the sound won't be played. So you can for example have a sound played at the end of a long copy operation, but short file copies wouldn't play anything.

The actual sound files that are used for these events are configured in the [Miscellaneous / Sounds](/Manual/preferences/preferences_categories/miscellaneous/sounds.md) page in [Preferences](/Manual/preferences/README.md).
