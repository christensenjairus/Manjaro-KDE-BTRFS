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
cd ..
sudo rm -r yay-bin
```

### Install Quality of Life Packages
```bash
# CLI basics
yay -S base-devel neovim git wget curl zsh tree tmux          \
terminator 

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
timeshift-autosnap kubectl kubectx helm k9s ipinfo-cli docker  \
python-requests 

# Other
yay -S ttf-jetbrains-mono ttf-jetbrains-mono-nerd             \
ttf-meslo-nerd-font-powerlevel10k zsh-theme-powerlevel10k     \
networkmanager-pptp networkmanager-openconnect                \
networkmanager-openvpn networkmanager-vpnc 1pass-autologin

# Not needed anymore?
# v4l2loopback-dkms linux-headers
```

### Install CLI Extensions
```bash
# oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# powerlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
# FYI - need to change theme in .zshrc
#    ZSH_THEME="powerlevel10k/powerlevel10k"

# zsh auto-suggestions
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions

# zsh syntax highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
# FYI - need to add plugins to .zshrc (
#    plugins=(git zsh-autosuggestions zsh-syntax-highlighting)

# terminator themes
mkdir -p $HOME/.config/terminator/plugins
wget https://git.io/v5Zww -O $HOME"/.config/terminator/plugins/terminator-themes.py"
```

### KDE Settings

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

