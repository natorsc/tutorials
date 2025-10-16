# Arch Linux

```bash
sudo pacman -S \
noto-fonts-emoji \
noto-fonts-cjk \
git \
python-pipx
```

## Flatpak

> A versão Gnome já vem com Flatpak e Flathub.

```bash
sudo pacman -S flatpak
```

```bash
flatpak install flathub \
org.gnome.Boxes \
org.gnome.Builder \
com.spotify.Client \
com.google.Chrome \
net.cozic.joplin_desktop \
org.sqlitebrowser.sqlitebrowser
```

## Pipx

> `pipx ensurepath`.

```bash
pipx install \
poetry \
pdm \
uv \
ruff
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
