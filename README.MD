# Diinki Aero

This is Diinki's frutiger aero themed rice, wich I modified a bit. I'm going to keep it up to date with the main repo.
Check ou the original Diinki video here!:
https://www.youtube.com/watch?v=Tx9dHc0MyHs

![alt text](./wallpapers/aquarium.png)

# Installation Steps 🖥️

You need to install the following dependencies on your system:

- `eww` for widgets
- `hyprland` the tiling window manager
- `caja` the file explorer
- `waybar` the taskbar
- `wofi` the application launcher.
- I use the `kitty` terminal, but you can use whichever terminal emulator that you are comfortable with.

On arch, you can install some of the above with `sudo pacman -S hyprland caja waybar wofi kitty`, installing `eww` has to
be done separately, easiest way is from the AUR with yay.

To install, copy all the folders in the `config` directory, to the `~/.config` directory on your system; make sure to backup your previous configs if you have them.

The `.config` directory is where most applications will store their config files.

You will need to make edits to config files, as not all configs are drag & drop, the files are commented in
order to help.

## Weather Widget ☁️

The weather widget uses `openweathermap.org` as a backend. They give you 2000 free api calls / day, which is more than enough.

You need to create an account there, get an API key, and then edit
the `eww/scripts/weather.sh` file with the following details. I've commented more specific instructions in that bash file.

The bash file stores the weather data in `~/.cache/eww/weather` every time `weather.sh --getdata` is called; as such, I recommend creating a
cronjob for calling `~/.config/eww/scripts/weather.sh --getdata` every 30 minutes.

## GTK theme & Icon Pack 🖌️

To install the icon theme, copy the `crystal-remix-icon-theme-diinki-version` directory in `IconTRheme` to your `~/.local/share/icons` or `/usr/share/icons` directories
and then set the theme to the one in use either with `gsettings` or the `dconf` applications; which you can download with most linux package managers.

To install the GTK theme, copy the `diinki-aero` folder in `GTKTheme` to your `~/.themes` directory,
and then set the GTK theme to "diinki-aero" with either `gsettings` or the `dconf` application.

# The Default Keybinds ⌨️

You can edit the keybinds in the hyprland config file as needed to match your preference, by default the most important ones:

- `MOD` is the super key/windows key by default in this config.
  - `MOD + Enter` = opens terminal (by default, kitty, you need to have it installed or edit the config file).
  - `MOD + F` = Toggle maximize of a window
  - `MOD + D` = Open the Wofi application launcher
  - `MOD + E` = open the file explorer (you need caja, or edit the config file)
  - `MOD + SHIFT + SPACE` = Toggle a window from tiling to floating.
  - `MOD + mouse1 drag` = Move a window
  - `MOD + mouse2 drag` = Resize a window
  - `MOD + Q` = Exit/Close an application
  - `MOD + SHIFT + (number, 1 to 9)` = Move the window to a workspace with that ID.

# Updates & Changes

Aspects and components of this rice will change with time, until I have a finalized design, I'll make specific releases on the github releases page.
