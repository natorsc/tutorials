# Arch Linux

## KDE

```bash
sudo pacman -S \
noto-fonts-emoji \
noto-fonts-cjk \
git \
python \
python-pip \
python-pipx \
python-lsp-server \
pyside6 \
kirigami \
flatpak-builder \
qqc2-desktop-style \
appstream \
podman-compose \
podman \
flatpak \
kdeconnect \
spectacle \
power-profiles-daemon \
speech-dispatcher \
firefox \
firefox-i18n-pt-br \
partitionmanager \
dosfstools \
exfatprogs \
ntfs-3g \
bluez \
bluez-utils \
btrfs-progs \
krdc \
krfb
```

### Flatpak

```bash
flatpak install flathub \
org.kde.alligator \
org.kde.gwenview \
org.kde.kalk \
org.kde.ktorrent \
org.kde.okular \
org.kde.optiimage \
com.google.Chrome \
com.spotify.Client \
org.libreoffice.LibreOffice \
org.localsend.localsend_app \
org.sqlitebrowser.sqlitebrowser \
org.videolan.VLC \
net.cozic.joplin_desktop
```

---

## GTK

```bash
sudo pacman -S \
noto-fonts-emoji \
noto-fonts-cjk \
git \
flatpak \
python \
python-pip \
python-pipx \
python-lsp-server \
cairo \
pkgconf \
gobject-introspection \
gtk4 \
libadwaita \
blueprint-compiler \
podman-compose \
podman \
flatpak \
power-profiles-daemon \
speech-dispatcher \
firefox \
firefox-i18n-pt-br \
dosfstools \
exfatprogs \
ntfs-3g \
bluez \
bluez-utils
```

### Gnome Boxes

```bash
sudo pacman -S --needed \
gnome-boxes \
qemu-full \
libvirt \
virtiofsd \
spice-gtk \
spice-protocol \
dnsmasq
```

```bash
sudo usermod -aG libvirt,kvm $(whoami)
sudo systemctl enable --now libvirtd
```

### Flatpak

```bash
flatpak install flathub \
org.gnome.Boxes \
org.gnome.Builder \
com.spotify.Client \
com.google.Chrome \
org.libreoffice.LibreOffice \
org.localsend.localsend_app
```

---

## Bluetooth

```bash
sudo systemctl enable bluetooth.service
sudo systemctl start bluetooth.service
```

---

## Pipx

> `pipx ensurepath`.

```bash
pipx install \
poetry \
pdm \
uv
```

---

## Zed

```bash
curl -f https://zed.dev/install.sh | sh
```

## Visual Studio Code

```bash
sudo pacman -S \
code
```

---

## AUR

### Yay

```bash
sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay-bin.git
cd yay-bin
makepkg -si
```

### Paru

```bash
sudo pacman -S --needed base-devel
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
```

