# nirubar-dwm

**nirubar-dwm** is a customizable status bar script designed for [dwm](https://dwm.suckless.org/), a minimalist window manager. The script is designed to provide a clear and functional status bar with useful system information and tools, making your workspace both efficient and informative.

## Features

- **Audio Volume**: Displays the current audio volume level and mute status with symbols or text.
- **Brightness**: Shows the current screen brightness level.
- **Battery Status**: Displays battery level and charging status, if a laptop is detected.
- **CMUS**: Integrated with CMUS music player to show the current song, artist, and player status.
- **Spotify**: Shows information about the ongoing playback in Spotify or Spotifyd, including song, artist, and player status.
- **System Resources**: Displays RAM and disk usage.
- **Updates**: Shows the number of available system and AUR updates.
- **Nextcloud**: Displays synchronization status for the Nextcloud client if installed.
- **Date and Time**: Shows the current date and time.

## Installation

1. **Clone the Repository**: Clone this repository to your local machine.
    ```sh
    git clone https://github.com/nirucon/nirubar-dwm
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

- `xsetroot` to update the status bar
- `amixer` for audio control
- `xbacklight` to adjust screen brightness
- `cmus`, `playerctl`, `spotify`, `spotifyd` for music player integration
- `curl` to fetch the public IP address
- `nextcloud-client` for Nextcloud status (optional)
- `checkupdates` and `yay` for updates (for Arch Linux and derivatives)

## License

Do what you want!
