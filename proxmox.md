# Como instalar os drivers do convidado no ProxMox

## Arch Linux

```bash
sudo pacman -S qemu-guest-agent
sudo systemctl enable --now qemu-guest-agent
```

## Fedora

```bash
sudo dnf install qemu-guest-agent
sudo systemctl enable --now qemu-guest-agent
```

## openSUSE

```bash
sudo zypper install qemu-guest-agent
sudo systemctl enable --now qemu-guest-agent
```

## Ubuntu

```bash
sudo apt install qemu-guest-agent
sudo systemctl enable --now qemu-guest-agent
```

## Microsoft Windows

https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/archive-virtio/

> Executar o arquivo msi.
