<h1 align="center">HYPRLAND</h1>

[![Hyprland Video](screenshots/dark/hypr_4.png)](https://youtu.be/t6Zd2F7rtPw)

<p align="center">The ultimate Hyprland configuration (A Desktop Environment Like Experience)</p>

---

## Overview

[Hyprland](https://github.com/vaxerski/Hyprland) is a dynamic tiling Wayland compositor based on wlroots that doesn't sacrifice on its looks.

- **Operating System** : `Archcraft`
- **Window Manager** : `Hyprland (0.30.0)`
- **Status Bar** : `Waybar`
- **Launcher** : `Rofi` / `Wofi`
- **Session Manager** : `Rofi` / `Wlogout`
- **Notifications** : `Mako`
- **Terminal** : `Foot`
- **File Manager** : `Thunar`
- **Text Editor** : `Geany`
- **Web Browser** : `Firefox`

## Installation
- **Get the files from** : [Ko-fi :coffee:](https://ko-fi.com/s/71d0e298d9) <sup>[**`Why Paid`**](https://github.com/adi1090x/adi1090x/blob/master/WHY.md)</sup>
- Extract The file **hyprland.tar.gz** with : `tar -xzvf hyprland.tar.gz`
- If you are using **`Archcraft`** (`Required: 2023 or later`) as your OS, You can just install one of the provided package with : `sudo pacman -U archcraft-hyprland-5.0-1-any.pkg.tar.zst` or `sudo pacman -U archcraft-hyprland-catppuccin-5.0-1-any.pkg.tar.zst` whichever style you like.
- If you want to install this setup on _Arch Linux_ or on any _other distro_, follow the points below :
  - Install the following programs on your computer: [`hyprland`](https://github.com/vaxerski/Hyprland), `swaybg` `swayidle` `swaylock` `wlroots` `wl-clipboard` `waybar` `wofi` `foot` `mako` `grim` `slurp` `wf-recorder` `light` `yad` `thunar` `geany` `mpv` `mpd` `mpc` `viewnior` `imagemagick` `xfce-polkit` `xorg-xwayland` `xdg-desktop-portal-wlr` `playerctl` `pastel` `python-pywal` `alacritty` `rofi` `pulsemixer`
  - After installing programs above, Create hypr directory in **`~/.config`** : `mkdir -p ~/.config/hypr`
  - Copy Everything from _`dotfiles/STYLE`_ to **`~/.config/hypr`** : `cp -r ./dotfiles/dark/* ~/.config/hypr/` 
  - Logout and login to your amazingly configured Hyprland WM.

> Hyprland now available in Arch Linux Repos, So Arch Linux users can install it via pacman.
>
> For other distro, If you don't want to build hyprland, You can install **compiled hyprland binaries** from [hyprland releases](https://github.com/hyprwm/Hyprland/releases)
>```
>sudo install -Dm 755 dotfiles/hypr-bin/hyprctl /usr/bin/hyprctl
>sudo install -Dm 755 dotfiles/hypr-bin/Hyprland /usr/bin/Hyprland
>sudo install -Dm 755 dotfiles/hypr-bin/libwlroots.so.12032 /usr/lib/libwlroots.so.12032
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
└── hypr               : Hyprland config directory
    ├── alacritty     : Alacritty Terminal config
    ├── foot          : Foot Terminal config
    ├── mako           : Notification daemon config
    │   └── icons      : Notification icons
    ├── rofi           : Rofi config files
    ├── scripts        : Various scripts for functionality
    ├── theme         : Current Theme and Pywal Themes
    ├── wallpapers     : Wallpapers
    ├── waybar         : Statusbar config
    ├── wlogout        : Wlogout config
    │   └── icons      : Session icons
    ├── wofi           : Launcher config
    ├── hyprland.conf  : Hyprland config file
    └── hyprtheme.conf : Colors and theme elements file
```

> By default, **[rofi](https://github.com/lbonn/rofi)** is used as app launcher.
>
> But, If you want to use **wofi** instead of **rofi**, Edit the config file `~/.config/hypr/hyprland.conf` and uncomment wofi keybindings (and, comment the rofi stuff as well).

> By default, **`MPD`** is used on waybar for music.
>
> But, If you want to use **Spotify** instead of **MPD**, Edit the config file `~/.config/hypr/waybar/config` and uncomment the spotify module (and, comment the MPD module as well).

## Nvidia
If you're on `Archcraft` and install the provided package, There's nothing else you need to do in order to run it on Nvidia machine. The package's post_installation script does it all, And the compositor should work fine.

If you're running any other distribution and want to install this setup on your Nvidia machine, You need to do some tweaking. In this guide, I'm assuing you're using **Arch Linux**. Follow the steps below to make this wayland compositor work on Nvidia :

- Install **Nvidia Drivers** on your system. [NVIDIA](https://wiki.archlinux.org/title/NVIDIA) 
- Edit `/etc/mkinitcpio.conf` file and add **`nvidia`** kernel modules
```
MODULES="nvidia nvidia_modeset nvidia_uvm nvidia_drm"
```

- In the same file, Remove `kms` hook from hooks array if present.
- Rebuild your initrd file with : `sudo mkinitcpio -P linux`
- Edit `/etc/default/grub` file and add **`nvidia_drm.modeset=1`** kernel parameter for Nvidia
```
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash nvidia_drm.modeset=1 ..."
```

- Update your grub config file with : `sudo grub-mkconfig -o /boot/grub/grub.cfg`
- Reboot your Nvidia Machine and login to your wayland compositor, It should work now.

More Information: [NVIDIA#Installation](https://wiki.archlinux.org/title/NVIDIA#Installation), [NVIDIA#DRM_kernel_mode_setting](https://wiki.archlinux.org/title/NVIDIA#DRM_kernel_mode_setting)

## Keybindings

| Keys | Action |
| --- | --- |
| <kbd>super + Return</kbd> | Open terminal (alacritty)|
| <kbd>super + shift + Return</kbd> | Open floating terminal (alacritty)|
| <kbd>super + T</kbd> | Open fullscreen terminal (alacritty)|
| <kbd>super + Return</kbd> | Open terminal (foot)|
| <kbd>super + shift + Return</kbd> | Open floating terminal (foot)|
| <kbd>super + alt + Return</kbd> | Open terminal with custom geometry (foot)|
| <kbd>super + T</kbd> | Open fullscreen terminal (foot)|
| <kbd>super + shift + F</kbd> | Open file manager |
| <kbd>super + shift + E</kbd> | Open text editor |
| <kbd>super + shift + W</kbd> | Open web browser|
| <kbd>super</kbd>, <kbd>super + D</kbd> | App launcher (rofi)|
| <kbd>super + R</kbd> | Command Runner (rofi)|
| <kbd>super + N</kbd> | Network Menu (rofi)|
| <kbd>super + B</kbd> | Bluetooth Menu (rofi)|
| <kbd>super + X</kbd> | Power Menu (rofi)|
| <kbd>super + M</kbd> | Music Player (rofi)|
| <kbd>super + A</kbd> | Screenshot Applet (rofi)|
| <kbd>super</kbd>, <kbd>super + D</kbd> | Run app launcher (wofi)|
| <kbd>super + N</kbd> | Open network manager |
| <kbd>super + X</kbd> | Run session manager (wlogout)|
| <kbd>super + P</kbd> | Run colorpicker |
| <kbd>super + C/Q</kbd> | Kill active window |
| <kbd>ctrl + alt + L</kbd> | Run lockscreen |
| <kbd>ctrl + alt + Delete</kbd> | Exit Hyprland instantly |
| <kbd>super + F</kbd> | Toggle fullscreen mode |
| <kbd>super + Space</kbd> | Toggle floating mode |
| <kbd>super + S</kbd> | Toggle pseudo mode |
| <kbd>super + Left / Right / Up / Down</kbd> | Change focus of the container |
| <kbd>super + shift + Left / Right / Up / Down</kbd> | Move active container directionally |
| <kbd>super + ctrl + Left / Right / Up / Down</kbd> | Resize active container |
| <kbd>super + alt + Left / Right / Up / Down</kbd> | Move floationg container directionally |
| <kbd>super + Tab</kbd> | Cycle between container |
| <kbd>super + 1,2..8</kbd> | Change workspace/tag from 1 to 8 |
| <kbd>super + shift + 1,2..8</kbd> | Move active container to repective workspace/tag |
| <kbd>super + ctrl + F</kbd> | Toggle All floating mode |
| <kbd>super + ctrl + S</kbd> | Toggle All pseudo mode |
| <kbd>super + shift + P</kbd> | Pin floating container |
| <kbd>super + shift + S</kbd> | Swap next container |
| <kbd>super + G</kbd> | Toggle Group Mode |
| <kbd>super + H</kbd> | Change active group container to left |
| <kbd>super + L</kbd> | Change active group container to right |

## Screenshots

**`Dark Version`**
| Screenshot 1 | Screenshot 2 | Screenshot 3 | Screenshot 4 |
| --- | --- | --- | --- |
|![hypr](screenshots/dark/hypr_1.png)|![hypr](screenshots/dark/hypr_2.png)|![hypr](screenshots/dark/hypr_3.png)|![hypr](screenshots/dark/hypr_4.png)|

**`Catppuccin Version`**
| Screenshot 1 | Screenshot 2 | Screenshot 3 | Screenshot 4 |
| --- | --- | --- | --- |
|![hypr](screenshots/catppuccin/hypr_1.png)|![hypr](screenshots/catppuccin/hypr_2.png)|![hypr](screenshots/catppuccin/hypr_3.png)|![hypr](screenshots/catppuccin/hypr_4.png)|

---

### See Also

| [**`archcraft-sway`**](https://github.com/archcraft-os/archcraft-sway) | [**`archcraft-wayfire`**](https://github.com/archcraft-os/archcraft-wayfire) | [**`archcraft-river`**](https://github.com/archcraft-os/archcraft-river) | [**`archcraft-newm`**](https://github.com/archcraft-os/archcraft-newm) |
| --- | --- | --- | --- |
|[![Sway](https://raw.githubusercontent.com/archcraft-os/archcraft-sway/main/screenshots/sway_4.png)](https://github.com/archcraft-os/archcraft-sway)|[![Wayfire](https://raw.githubusercontent.com/archcraft-os/archcraft-wayfire/main/screenshots/wayfire_4.png)](https://github.com/archcraft-os/archcraft-wayfire)|[![River](https://raw.githubusercontent.com/archcraft-os/archcraft-river/main/screenshots/river_4.png)](https://github.com/archcraft-os/archcraft-river)|[![Newm](https://raw.githubusercontent.com/archcraft-os/archcraft-newm/main/screenshots/solid/newm_5.png)](https://github.com/archcraft-os/archcraft-newm)|
