# Hyprland + Waybar config (Arch Linux)

Personal modular Hyprland setup with Hyprlock, Hypridle, Swww, Hyprsunset and a dual Waybar setup (top + bottom).

## Screenshot

![Screenshot](assets/screen.jpg)

## Tree

```bash
~/.config/hypr
├── hypridle.conf
├── hyprland.conf
├── hyprlock.conf
├── hyprsunset.conf
└── modules
    ├── animation.conf
    ├── autostart.conf
    ├── input.conf
    ├── keybind.conf
    ├── rules.conf
    └── theme.conf
```

## Waybar [dans le repo waybar-config](https://github.com/grayTerminal-sh/waybar-config) :

```bash
~/.config/waybar
├── config
├── style.css
├── config-bottom.jsonc
└── style-bottom.css
```

## Hyprland

hyprland.conf :

```text
monitor= eDP-1,1920x1080@60,0x0,1

env = XDG_CURRENT_DESKTOP,Hyprland
env = XDG_SESSION_TYPE,wayland
env = QT_QPA_PLATFORM,wayland
env = GDK_BACKEND,wayland
env = MOZ_ENABLE_WAYLAND,1

source = ~/.config/hypr/modules/keybind.conf
source = ~/.config/hypr/modules/autostart.conf
source = ~/.config/hypr/modules/input.conf
source = ~/.config/hypr/modules/animation.conf
source = ~/.config/hypr/modules/theme.conf
source = ~/.config/hypr/modules/rules.conf
```

### Modules :
- animation.conf: window and workspace animations.
- autostart.conf: services and apps at startup (Waybar, cliphist, kitty scratchpad, etc.).
- input.conf: FR keyboard layout, touchpad.
- keybind.conf: keybinds (SUPER + Return for kitty, SUPER + B for Firefox, grim/slurp screenshots, volume, brightness, Waybar scripts…).
- rules.conf: windowrules for Deezer, kitty-dropterm, Blueman, Waypaper.
- theme.conf: gaps, borders, opacity, blur, general theme.


### Extra files :
- hypridle.conf: idle management (lock at 5 min, DPMS off at 10 min).
- hyprlock.conf: custom lock screen (clock, date, battery, wallpaper).
- hyprsunset.conf: color temperature (night light).

### Dépendancies :
- Hyprland
- Hyprlock
- Hypridle
- Hyprpaper
- Hyprsunset

### Bar / notifications / wallpaper
- waybar
- swaync
- swww
- waypaper


### Terminal / apps
- kitty
- firefox
- nautilus
- deezer-desktop
- discord
- google-chrome-stable
- aerc
- yazi
- calcure

### Screenshots / clipboard
- grim
- slurp

### wl-clipboard (wl-copy, wl-paste)
- cliphist
- jq (for activr windows capture)

### Audio / luminosité
- pipewire + wireplumber
- wpctl (pipewire-pulse / wireplumber)
- brightnessctl

### Thèmes / fonts
- Adwaita-dark (GTK)
- Tela-dracula-dark (icônes)
- JetBrains Mono Nerd Font


## Installation
Clone the repo :

```bash
git clone https://github.com/<ton-user>/hyprland-config.git ~/Repo/hyprland-config
```
Backup yout current config :

```bash
mv ~/.config/hypr ~/.config/hypr.bak 2>/dev/null || true
```

Copy ou symlink :
```bash
mkdir -p ~/.config
ln -s ~/Repo/hyprland-config/.config/hypr ~/.config/hypr
# ou
cp -r ~/Repo/hyprland-config/.config/hypr ~/.config/hypr
(Optionnel) Copier votre config Waybar dans ~/.config/waybar.
```
Reload Hyprland :
```bash
hyprctl reload
```

## Open/close bottom waybar
- <leader>space
