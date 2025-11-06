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
bluez-utils
```

### Flatpak

```bash
flatpak install flathub \
com.spotify.Client \
com.google.Chrome \
org.sqlitebrowser.sqlitebrowser \
org.kde.ktorrent \
org.kde.gwenview \
org.kde.okular \
org.kde.kalk \
org.kde.optiimage \
org.kde.alligator \
org.libreoffice.LibreOffice \
org.videolan.VLC \
org.localsend.localsend_app
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
kdeconnect \
spectacle \
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

## Pipx

> `pipx ensurepath`.

```bash
pipx install \
poetry \
pdm \
uv
```

## Zed

```bash
curl -f https://zed.dev/install.sh | sh
```

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

