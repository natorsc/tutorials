# Como instalar as ferramentas de compilação em distribuições Linux

## Ubuntu

O pacote `build-essential` na distribuição Linux Ubuntu é um meta pacote que inclui uma coleção de ferramentas e bibliotecas essenciais para compilar software.

Ele não é um software em si, mas sim um conjunto de dependências necessárias para a compilação de programas escritos em C e C++.

Ao instalar o `build-essential`, você estará instalando pacotes como:

- `gcc` (GNU Compiler Collection).
- `g++` (GNU C++ Compiler).
- `make` (utilitário de construção).
- `libc` (bibliotecas padrão do C).
- `dpkg-dev` (ferramentas de desenvolvimento para pacotes Debian).
- Etc.

### Instalação

Para instalar o `build-essential` na distribição Linux Ubuntu, você pode usar o seguinte comando:

```bash
sudo apt update && \
sudo apt install build-essential
```

## Arch Linux

Na distribuição Linux [Arch Linux](https://archlinux.org/) o equivalente ao pacote `build-essential` é o pacote `base-devel`.

### Instalação

```bash
sudo pacman -S \
base-devel
```

## Fedora

Na distribuição Linux [Fedora](https://fedoraproject.org/) o equivalente ao pacote `build-essential` são os grupos `"C Development Tools and Libraries"` e `"Development Tools"`.

### Instalação

Para instalar os pacotes `"C Development Tools and Libraries"` e `"Development Tools"` na distribuição Linux Fedora, você pode usar o seguinte comando:

```bash
sudo dnf check-update && \
sudo dnf group install \
"C Development Tools and Libraries" \
"Development Tools"
```

## openSuse

Na distribuição Linux [openSuse](https://www.opensuse.org/) o pacote equivalente ao `build-essential` é o pacote `devel_basis`.

### Instalação

Para instalar o `devel_basis` na distribuição Linux openSuse, você pode usar o seguinte comando:

```bash
sudo zypper refresh && \
sudo zypper install \
-t pattern devel_basis
```
