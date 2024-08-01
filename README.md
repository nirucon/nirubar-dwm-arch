# nirubar-dwm

**nirubar-dwm** is a customizable status bar script designed for [dwm](https://dwm.suckless.org/), a lightweight window manager. This script provides a clean and informative status bar by displaying various system metrics and tools, tailored to enhance your workflow.

## Features

### Audio Volume

- **Function**: Displays the current audio volume level and mute status.
- **How It Works**: Uses `amixer` to get the volume level and mute status. Depending on the volume level, it shows different icons or text:
  - **Muted**: Shows a mute icon.
  - **Low Volume**: Displays a low volume icon with percentage.
  - **Medium/High Volume**: Shows a high volume icon with percentage.

### Brightness

- **Function**: Shows the current screen brightness level.
- **How It Works**: Uses `xbacklight` to retrieve and display the current brightness setting.

### Battery Status

- **Function**: Displays battery level and charging status if a laptop is detected.
- **How It Works**: Checks the presence of battery directories (`BAT0` and `BAT1`) in `/sys/class/power_supply/`. Uses these directories to read battery capacity and status, displaying relevant icons and information.

### CMUS

- **Function**: Displays information about the currently playing song in the CMUS music player.
- **How It Works**: Queries CMUS using `cmus-remote` to get details such as artist, title, position, and duration. Displays the playback status and optionally, shuffle status.

### Spotify

- **Function**: Shows information about the ongoing playback in Spotify or Spotifyd.
- **How It Works**: Checks if Spotify or Spotifyd is running. Uses `playerctl` to retrieve metadata about the currently playing track, including artist, title, position, and duration. Displays playback status and shuffle state.

### System Resources

- **Function**: Displays RAM and disk usage.
- **How It Works**: Uses `free` to get RAM usage and `df` to get disk usage information. Outputs usage stats with appropriate icons.

### Updates

- **Function**: Shows the number of available system and AUR updates.
- **How It Works**: Uses `checkupdates` to count the number of available system updates and `yay` to count AUR updates. Checks for updates at a regular interval (30 minutes) and caches the result to minimize update checks.

### Date and Time

- **Function**: Displays the current date and time.
- **How It Works**: Uses the `date` command to get and format the current date and time.

## Installation

1. **Clone the Repository**: Clone this repository to your local machine.
    ```sh
    git clone https://github.com/nirubar-dwm/
    ```

2. **Make the Script Executable**:
    ```sh
    chmod +x nirubar-dwm/nirubar-dwm
    ```

3. **Edit `dwm` Configuration**: Add the script to your `dwm` configuration to run it at startup.

## Usage

1. **Run the Script**: Execute the script in the background. You can add it to your `.xinitrc` or similar startup file.
    ```sh
    ./nirubar-dwm/nirubar-dwm &
    ```

2. **Configure Modules**: Customize what is displayed on your status bar by commenting or uncommenting relevant modules in the script.

## Requirements

- `xsetroot` to update the status bar.
- `amixer` for audio control.
- `xbacklight` to adjust screen brightness.
- `cmus`, `playerctl`, `spotify`, `spotifyd` for music player integration.
- `curl` to fetch the public IP address.
- `checkupdates` and `yay` for updates (for Arch Linux and derivatives).

## License

Feel free to use and modify, donate if you want :) https://www.paypal.com/paypalme/nicklasrudolfsson
