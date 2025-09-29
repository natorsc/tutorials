# Como instalar a linguagem de programação Python no Linux

[Python](https://www.python.org/) é uma linguagem de programação popular e versátil, que pode ser usada para diversos fins, como desenvolvimento web, análise de dados, automação de tarefas e muito mais.

Neste post, vamos aprender como realizar a instalação da linguagem de programação Python no Linux, um sistema operacional livre e de código aberto.

Existem duas formas principais de instalar a linguagem de programação Python no Linux: usando o **gerenciador de pacotes** da sua distribuição Linux ou **baixando o código fonte** do site oficial do Python.

Neste post vamos ver cada uma delas em detalhes.

## Usando o gerenciador de pacotes

A maioria das distribuições Linux já vem com uma versão do Python pré-instalada, mas pode ser que a instalação não esteja completa ou não seja a versão que você deseja usar.

> ⚠️ Para instalar um versão específica da linguagem de programação Python utilize a função de pesquisa do gerenciador de pacotes da sua distribuição.

### Arch Linux

Site oficial da distribuição Linux [Arch Linux](https://archlinux.org/).

Digite no terminal:

```bash
sudo pacman -S \
python \
python-pip \
python-lsp-server \
tk
```

> ⚠️ Se o `sudo` não estiver configurado utilize a conta de **root** (sem `sudo`) para a instalação dos pacotes.

### Chromebook (ChromeOS)

> ⚠️ Para realizar a instalação da linguagem de programação Python no [ChromeOS](https://chromeenterprise.google/intl/pt_br/os/) é necessário que o suporte a Linux esteja ativo:

Assim que o suporte a Linux estiver ativo no Chrome OS abra o aplicativo de terminal e execute o comando:

```bash
sudo apt install \
python3 \
python3-dev \
python3-venv \
python3-pip \
python3-tk \
build-essential \
libssl-dev \
libffi-dev \
python3-pylsp \
python-is-python3 \ 
idle3
```

> ⚠️ Dependendo da versão do Debian que está sendo executada no contêiner, é possível utilizar o pacote `python3-full`.

### Fedora

Site oficial da distribuição Linux [Fedora](https://getfedora.org/).

> ⚠️ Comando testado no Fedora 41.

Digite no terminal:

```bash
sudo dnf install \
python3 \
python3-devel \
python3-tools \
python3-idle \
python3-pip \
python3-tkinter \
python-lsp-server \
python-unversioned-command
```

### openSUSE Tumbleweed

Site oficial da distribuição Linux [openSUSE Tumbleweed](https://www.opensuse.org/#Tumbleweed).

Digite no terminal:

```plaintext
sudo zypper install \
python312 \
python312-tk \
python312-idle \
python-python-lsp-server
```

### Ubuntu e derivados

Site oficial da distribuição Linux [Ubuntu](https://ubuntu.com/).

> ⚠️ Comando testado no Ubuntu 24.04.

Digite no terminal:

```bash
sudo apt install \
python3 \
python3-dev \
python3-venv \
python3-pip \
python3-tk \
python3-pylsp \
python-is-python3 \
idle3
```

> ⚠️ Dependendo da versão do Ubuntu é possível utilizar o pacote `python3-full`.

## Como instalar a linguagem Python através do código fonte

A instalação da linguagem de programação Python através do código fonte é bem simples, contudo são necessárias a ferramentas de compilação que veremos a seguir.

### Arch Linux

```bash
sudo pacman -S \
base-devel
```

### Fedora

```bash
sudo dnf group install \
"C Development Tools and Libraries" \
"Development Tools"
```

### openSUSE Tumbleweed

```bash
sudo zypper install \
-t pattern \
devel_basis
```

### Ubuntu

```bash
sudo apt install \
build-essential
```

Para baixar o código fonte da linguagem de programação Python, acesse [https://www.python.org/downloads/](https://www.python.org/downloads/).

Em seguida, faça o download do arquivo `*.tar.xz` e salve-o em um diretório de sua preferência.

Abra um terminal e navegue até o diretório onde o arquivo foi salvo e extraia o conteúdo do arquivo com o comando:

```bash
tar -xvf \
Python-3.x.x.tar.xz
```

> ⚠️ Isso vai criar uma pasta chamada `Python-3.x.x`, onde `x.x` é a versão que você baixou.

Acesse a pasta com o comando:

```bash
cd Python-3.x.x
```

Agora, você precisa configurar o código fonte para que ele seja compatível com o seu sistema.

Para isso, digite:

```bash
./configure
```

Esse comando vai verificar as dependências necessárias para compilar o Python e criar um arquivo Makefile com as instruções adequadas.

Depois que o comando terminar, você pode iniciar a compilação do Python com o comando:

```bash
make
```

Aguarde até que o comando `make` termine (**sem erros**).

Por fim, você pode instalar a linguagem de programação Python com o comando:

```bash
sudo make install
```

O comando irá copiar os arquivos, binários e as bibliotecas da linguagem de programação Python para os locais apropriados da sua distribuição Linux.

Para verificar a instalação feche o terminal, abra novamente e digite o comando:

```bash
python3 --version
```

Caso tenha mais de uma versão da linguagem de programação Python instalada execute:

```bash
python3.x --version
```

> ⚠️ Substitua o `x` pela versão que você instalou. **Exemplo** 3.13, 3.14, etc.

Pronto! Agora você já sabe como realizar a instalação da linguagem de programação Python no Linux.
