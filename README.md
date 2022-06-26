<h1 align="center">HYPRLAND</h1>

[![Hyprland Video](screenshots/dark/hypr_dark_2.png)](https://youtu.be/t6Zd2F7rtPw)

<p align="center">The ultimate Hyprland configuration (A Desktop Environment Like Experience)</p>

---

## Overview

[Hyprland](https://github.com/vaxerski/Hyprland) is a dynamic tiling Wayland compositor based on wlroots that doesn't sacrifice on its looks.

- **Operating System** : `Archcraft`
- **Window Manager** : `Hyprland`
- **Status Bar** : `Waybar`
- **Launcher** : `Wofi`
- **Session Manager** : `Wlogout`
- **Notifications** : `Mako`
- **Terminal** : `Foot`
- **File Manager** : `Thunar`
- **Text Editor** : `Geany`
- **Web Browser** : `Firefox`

## Installation
- **Get the files from** : [Ko-fi :coffee:](https://ko-fi.com/s/71d0e298d9)
- Extract The file **hyprland.tar.gz** with : `tar -xzvf hyprland.tar.gz`
- If you are using **`Archcraft`** as your OS, You can just install one of the provided package with : `sudo pacman -U archcraft-hyprland-1.0-1-any.pkg.tar.zst` or `sudo pacman -U archcraft-hyprland-catppuccin-1.0-1-any.pkg.tar.zst` whichever style you like.
- If you want to install this setup on _Arch Linux_ or on any _other distro_, follow the points below :
  - Install the following programs on your computer: [`hyprland`](https://github.com/vaxerski/Hyprland), `swaybg` `swayidle` `swaylock` `wlroots` `wl-clipboard` `waybar` `wofi` `foot` `mako` `grim` `slurp` `wf-recorder` `light` `yad` `thunar` `geany` `mpv` `mpd` `mpc` `viewnior` `imagemagick` `xfce-polkit` `xorg-xwayland`
  - After installing programs above, Create hypr directory in **`~/.config`** : `mkdir -p ~/.config/hypr`
  - Copy Everything from _`dotfiles/STYLE`_ to **`~/.config/hypr`** : `cp -r ./dotfiles/dark/* ~/.config/hypr/` 
  - Logout and login to your amazingly configured Hyprland WM.

> If you don't want to build hyprland, You can install **compiled hyprland binaries** provided in `dotfiles/hypr-bin`
>```
>sudo install -Dm 755 dotfiles/hypr-bin/hyprctl /usr/bin/hyprctl
>sudo install -Dm 755 dotfiles/hypr-bin/Hyprland /usr/bin/Hyprland
>sudo install -Dm 755 dotfiles/hypr-bin/libwlroots.so.11032 /usr/lib/libwlroots.so.11032
>sudo install -Dm 644 dotfiles/hypr-bin/hyprland.desktop /usr/share/wayland-sessions/hyprland.desktop
>```

### Appearance

Install the following `theme`, `icon pack`, `cursors` and `fonts` for overall appearance.

- GTK Theme : [Manhattan gtk theme](https://github.com/archcraft-os/archcraft-themes/tree/main/archcraft-gtk-theme-manhattan)
- Icon Theme : [Luv icon theme](https://github.com/Nitrux/luv-icon-theme)
- Cursor Theme : [Qogir cursor theme](https://www.gnome-look.org/p/1366182/)
- Fonts : [JetBrainsMono Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/JetBrainsMono.zip), [Iosevka Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/Iosevka.zip), [Icomoon Feather](https://github.com/archcraft-os/archcraft-packages/blob/main/archcraft-fonts/files/icon-fonts/Icomoon-Feather.ttf), [Archcraft](https://github.com/archcraft-os/archcraft-packages/blob/main/archcraft-fonts/files/icon-fonts/archcraft.ttf)

## Config Structure
```
~/.config
└── hypr              : Hyprland config directory
    ├── foot          : Terminal config
    ├── mako          : Notification daemon config
    │   └── icons     : Notification icons
    ├── scripts       : Various scripts for functionality
    ├── wallpapers    : Wallpapers
    ├── waybar        : Statusbar config
    ├── wlogout       : Wlogout config
    │   └── icons     : Session icons
    ├── wofi          : Launcher config
    └── hyprland.conf : Hyprland config file
```

## Keybindings

| Keys | Action |
| --- | --- |
| <kbd>super + Return</kbd> | Open terminal |
| <kbd>super + shift + Return</kbd> | Open floating terminal |
| <kbd>super + alt + Return</kbd> | Open terminal with selected geometry |
| <kbd>super + T</kbd> | Open full-screen terminal with big fonts |
| <kbd>super + shift + F</kbd> | Open file manager |
| <kbd>super + shift + E</kbd> | Open text editor |
| <kbd>super + shift + W</kbd> | Open web browser|
| <kbd>super + D</kbd> | Run app launcher |
| <kbd>super + X</kbd> | Run powermenu |
| <kbd>super + N</kbd> | Open network manager |
| <kbd>super + P</kbd> | Run colorpicker |
| <kbd>super + C/Q</kbd> | Kill active window |
| <kbd>ctrl + alt + L</kbd> | Run lockscreen |
| <kbd>ctrl + alt + Delete</kbd> | Exit Hyprland instantly |
| <kbd>super + F</kbd> | Toggle fullscreen mode |
| <kbd>super + Space</kbd> | Toggle floating mode |
| <kbd>super + S</kbd> | Toggle pseudo mode |
| <kbd>super + Left</kbd> | Change focus to the left container |
| <kbd>super + Right</kbd> | Change focus to the right container |
| <kbd>super + Up</kbd> | Change focus to the upper container |
| <kbd>super + Down</kbd> | Change focus to the lower container |
| <kbd>super + shift + Left</kbd> | Move container to the left side |
| <kbd>super + shift + Right</kbd> | Move container to the right side |
| <kbd>super + shift + Up</kbd> | Move container to the upper side |
| <kbd>super + shift + Down</kbd> | Move container to the lower side |
| <kbd>super + 1,2..9</kbd> | Change workspace/tag from 1 to 9 |
| <kbd>super + shift + 1,2..9</kbd> | Move active container to repective workspace/tag |

## Screenshots

**`Dark Version`**
| Desktop (wofi) | Floating | Tiled | Thunar, Geany | Wlogout |
| --- | --- | --- | --- | --- |
|![hypr](screenshots/dark/hypr_dark_1.png)|![hypr](screenshots/dark/hypr_dark_2.png)|![hypr](screenshots/dark/hypr_dark_3.png)|![hypr](screenshots/dark/hypr_dark_4.png)|![hypr](screenshots/dark/hypr_dark_5.png)|

**`Catppuccin Version`**
| Desktop (wofi) | Floating | Tiled | Thunar, Geany | Wlogout |
| --- | --- | --- | --- | --- |
|![hypr](screenshots/catppuccin/hypr_catppuccin_1.png)|![hypr](screenshots/catppuccin/hypr_catppuccin_2.png)|![hypr](screenshots/catppuccin/hypr_catppuccin_3.png)|![hypr](screenshots/catppuccin/hypr_catppuccin_4.png)|![hypr](screenshots/catppuccin/hypr_catppuccin_5.png)|


## FYI
- May or may not work on [**`Nvidia`**](https://wiki.archlinux.org/title/Sway#Installation), See [wayland requirements](https://wiki.archlinux.org/title/wayland#Requirements).
- Thank you for your support.

---

### See Also

| [**`archcraft-sway`**](https://github.com/archcraft-os/archcraft-sway) | [**`archcraft-wayfire`**](https://github.com/archcraft-os/archcraft-wayfire) | [**`archcraft-river`**](https://github.com/archcraft-os/archcraft-river) | [**`archcraft-newm`**](https://github.com/archcraft-os/archcraft-newm) |
| --- | --- | --- | --- |
|[![Sway](https://raw.githubusercontent.com/archcraft-os/archcraft-sway/main/screenshots/sway_6.png)](https://github.com/archcraft-os/archcraft-sway)|[![Wayfire](https://raw.githubusercontent.com/archcraft-os/archcraft-wayfire/main/screenshot.png)](https://github.com/archcraft-os/archcraft-wayfire)|[![River](https://raw.githubusercontent.com/archcraft-os/archcraft-river/main/screenshots/River_4.png)](https://github.com/archcraft-os/archcraft-river)|[![Newm](https://raw.githubusercontent.com/archcraft-os/archcraft-newm/main/screenshots/solid/newm_5.png)](https://github.com/archcraft-os/archcraft-newm)|
