# nirubar-dwm

This script dynamically updates the status bar of the DWM (Dynamic Window Manager) with various system information. It uses `xsetroot` to set the status text and supports the following modules:

- **ALSA Volume**: Displays the current volume level and mute status.
- **Backlight**: Shows the screen brightness level (if uncommented).
- **Battery**: Indicates battery status and charge level for laptops.
- **CMUS**: Shows the currently playing track in the CMUS music player.
- **Spotify**: Displays the current track and status from Spotify or Spotifyd.
- **Load Average**: Displays the system load average (if uncommented).
- **Network**: Shows the current network connection and public IP address (if uncommented).
- **PulseAudio**: Displays PulseAudio volume and mute status (if uncommented).
- **Resources**: Shows RAM and disk usage.
- **Updates**: Checks for available system and AUR updates.
- **Date**: Displays the current date and time.

## Laptop vs. Workstation Detection

The script automatically detects if the system is a laptop or a workstation by checking for battery information. Battery status modules are only displayed on laptops.

## Dependencies

- `xorg-xsetroot`
- `alsa-utils`
- `xbacklight`
- `cmus`
- `curl`
- `playerctl`
- `ttf-font-awesome`
- `pamixer` (for PulseAudio)

## Usage

Make the script executable and run it:

```sh
chmod +x nirubar-dwm
./nirubar-dwm
```
Start it in your .xinitrc or autostart script.

Customize the modules displayed by commenting/uncommenting the respective lines in the script.

## License

Do what you want!
