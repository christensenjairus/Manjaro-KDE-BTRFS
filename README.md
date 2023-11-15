# Manjaro-KDE-BTRFS

# Install
Install Manjaro
* Open-Source drivers
* Colemak-DH (for laptop only)
* BTRFS
* Swap
    * Desktop -> Swap to file
    * Laptop -> Swap with Hiberntate
* Encrypt system (hard pw)
* FreeOffice Suite

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
yay -S --noconfirm base-devel neovim vim git wget curl zsh tree tmux      \
terminator 

# Background services
yay -S --noconfirm qemu-guest-agent dropbox tlp

# Desktop apps
yay -S --noconfirm discord slack-desktop joplin-desktop firefox zoom      \
nextcloud-client brave-bin teams-for-linux jetbrains-toolbox              \
pithos spotify plexamp-appimage google-chrome tlpui gimp                  \
visual-studio-code-bin plex-media-player github-desktop-bin               \
onedrivegui-git onedrive_tray-git obs-studio burpsuite                    \
remmina timeshift wireshark-qt 1password deja-dup

# CLI apps
yay -S --noconfirm docker docker-compose grub-btrfs pianobar metasploit   \
postgresql lolcat neofetch bpytop lf downgrade thefuck nmap               \
timeshift-autosnap kubectl kubectx helm k9s ipinfo-cli docker             \
python-requests dirbuster kustomize playerctl k3sup-bin kube-dump

# Other
yay -S --noconfirm ttf-jetbrains-mono ttf-jetbrains-mono-nerd             \
ttf-meslo-nerd-font-powerlevel10k zsh-theme-powerlevel10k                 \
networkmanager-pptp networkmanager-openconnect                            \
networkmanager-openvpn networkmanager-vpnc 1pass-autologin                \
manjaro-settings-samba avahi bind cnijfilter2 go-yq pavucontrol qsixmixer
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

### Install Kubectl Extensions
```bash
# download and install krew
(
  set -x; cd "$(mktemp -d)" &&
  OS="$(uname | tr '[:upper:]' '[:lower:]')" &&
  ARCH="$(uname -m | sed -e 's/x86_64/amd64/' -e 's/\(arm\)\(64\)\?.*/\1\2/' -e 's/aarch64$/arm64/')" &&
  KREW="krew-${OS}_${ARCH}" &&
  curl -fsSLO "https://github.com/kubernetes-sigs/krew/releases/latest/download/${KREW}.tar.gz" &&
  tar zxvf "${KREW}.tar.gz" &&
  ./"${KREW}" install krew
)
# Add the following to ~/.zshrc
export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH"
# restart shell
# install neat
kubectl krew install neat
```

### PIA VPN
```bash
# Download AMD64 linux .run file
chmod +x ./pia-linux-x.x.x-xxxxx.run
./pia-linux-x.x.x-xxxxx.run
```

### VirtualBox
```bash
yay -S linux61-headers
pushd ~/
wget https://download.virtualbox.org/virtualbox/7.0.10/VirtualBox-7.0.10-158379-Linux_amd64.run
chmod +x ./VirtualBox-7.0.10-158379-Linux_amd64.run
sudo ./VirtualBox-7.0.10-158379-Linux_amd64.run
popd
```

### HomeLab Repos
```bash
ssh-keygen
# copy key into Gitlab so the git clone with ssh works
mkdir ~/HomeLab
pushd ~/HomeLab
git clone git@gitlab.christensencloud.us:homelab/Kubernetes.git
mkdir ~/.kube
cp ./Kubernetes/kubeconfig.yaml ~/.kube/config
chmod 600 ~/.kube/config
git clone git@gitlab.christensencloud.us:homelab/Splunk.git
git clone git@gitlab.christensencloud.us:homelab/Wazuh.git
popd
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

