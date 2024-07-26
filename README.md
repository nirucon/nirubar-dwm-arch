# nirubar-dwm

# dwm bar script

This script provides a customizable status bar for the **dwm** window manager. It leverages various system tools and utilities to display real-time information about system resources, audio, battery status, and more. 

## Features

- **Audio Status**: Displays volume levels and mute status using icons or text.
- **Backlight**: Shows the current screen backlight level.
- **Battery Information**: Provides charge levels and status for up to two batteries.
- **Music Player**: Displays information for `cmus` or Spotify, including playback status, artist, and track details.
- **System Resources**: Shows memory and disk usage.
- **Date and Time**: Provides current date and time.
- **Network Information**: Displays network connection details and public IP address.
- **CPU Load Average**: Monitors the system's load average.

## Dependencies

Ensure the following packages are installed on your system:
- `xorg-xsetroot`
- `alsa-utils` (for audio status)
- `xbacklight` (for backlight control)
- `cmus` (for music playback)
- `curl` (for fetching IP address)
- `playerctl` (for controlling media players)
- `ttf-font-awesome` (for additional icons, if used)

## Configuration

You can customize the script by modifying the following variables:

- `IDENTIFIER`: Change between "unicode" for icons or "text" for text representation.
- `SEP1` and `SEP2`: Customize the characters used to separate modules in the status bar.

## Functions

- `dwm_alsa()`: Displays the current audio volume and mute status.
- `dwm_backlight()`: Shows the screen backlight level.
- `dwm_battery1()` and `dwm_battery0()`: Display battery status for two batteries.
- `dwm_cmus()`: Provides current playback information from `cmus`.
- `dwm_date()`: Shows the current date and time.
- `dwm_loadavg()`: Displays the system's load average.
- `dwm_networkmanager()`: Shows network connection details and public IP address.
- `dwm_pulse()`: Displays audio volume and mute status for PulseAudio.
- `dwm_resources()`: Provides memory and disk usage statistics.
- `dwm_spotify()`: Displays playback information for Spotify or Spotifyd.

## Usage

1. Make sure the script is executable:
    ```bash
    chmod +x /path/to/nirubar-dwm
    ```

2. Add the script to your `dwm` configuration to run it on startup, or run it manually from your terminal:
    ```bash
    /path/to/nirubar-dwm
    ```

3. Customize the status bar modules by uncommenting or commenting out the relevant lines in the `while true` loop.

## Example

To include all modules in the status bar, you can modify the `while true` loop in the script like this:

```bash
while true; do
    STATUS_OUTPUT=""
    STATUS_OUTPUT+=$(dwm_alsa)
    STATUS_OUTPUT+=" | $(dwm_backlight)"
    STATUS_OUTPUT+=" | $(dwm_battery1)"
    STATUS_OUTPUT+=" | $(dwm_battery0)"
    STATUS_OUTPUT+=" | $(dwm_cmus)"
    STATUS_OUTPUT+=" | $(dwm_spotify)"
    STATUS_OUTPUT+=" | $(dwm_loadavg)"
    STATUS_OUTPUT+=" | $(dwm_networkmanager)"
    STATUS_OUTPUT+=" | $(dwm_pulse)"
    STATUS_OUTPUT+=" | $(dwm_resources)"
    STATUS_OUTPUT+=" | $(dwm_date)"

    # Set the root window text
    xsetroot -name "$STATUS_OUTPUT"

    sleep 2
done
```

## License

Do what you want!
