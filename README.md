# Manjaro-KDE-BTRFS

# Install
Install Manjaro
* Open-Source drivers
* BTRFS
* Swap to file
* Encrypt system (hard pw)

# Setup
### Pamac repos and update
* Pamac -> system preferences
  * Enable third party AUR and Flatpak
  * Update system
 
### Yay
Run as user NOT ROOT!
```bash
git clone https://aur.archlinux.org/yay-bin
cd yay-bin
makepkg -si
```

### Install Quality of Life Packages
```bash
# CLI basics
yay -S base-devel vim git wget curl zsh tree tmux terminator 

# Background services
yay -S qemu-guest-agent dropbox tlp

# Desktop apps
yay -S discord slack-desktop joplin-desktop firefox zoom      \
nextcloud-client brave-bin teams-for-linux jetbrains-toolbox  \
pithos spotify plexamp-appimage google-chrome tlpui gimp      \
visual-studio-code-bin plex-media-player github-desktop-bin   \
onedrivegui-git onedrive_tray-git obs-studio burpsuite        \
remmina timeshift wireshark-qt piavpn-bin 1password deja-dup

# CLI apps
yay -S docker docker-compose grub-btrfs pianobar metasploit    \
postgresql lolcat neofetch bpytop lf downgrade thefuck nmap    \
timeshift-autosnap kubectl kubectx helm

# Other
yay -S ttf-jetbrains-mono ttf-jetbrains-mono-nerd             \
ttf-meslo-nerd-font-powerlevel10k zsh-theme-powerlevel10k     \
networkmanager-pptp networkmanager-openconnect                \
networkmanager-openvpn networkmanager-vpnc 1pass-autologin

# Not needed anymore?
# v4l2loopback-dkms linux-headers
```

### KDE Theme Settings
* Install Plasma Style
   * Breeze AlphaBlack
 
* Install Color theme
   * Atrium Dark (use `from current wallpaper` to get colors right)
    
* Install Widgets
   * Aesthetic Clock
   * Plasma Customization Saver
   * Event Calendar
   * MediaController_Plus
   * Plasma Drawer
   * System Load Viewer
   * Simple System Monitor
   * Tiled Menu
 
### KDE Window Rules
* No titlebar and frame (force)
   * Spotify
   * Terminator

### KDE Keyboard Shortcuts
* Navigator > Quit (disable from ctrl+q)
* Kwin > Close (ctrl+q)
* Terminator (meta+return)

### KDE AutoStart
* 1Password
* Firefox
* Slack
* Terminator

