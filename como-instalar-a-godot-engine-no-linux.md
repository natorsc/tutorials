# Como instalar a Godot engine no Linux

A [**Godot Engine**](https://godotengine.org/) é uma ferramenta poderosa e de código aberto para o desenvolvimento de jogos 2D e 3D.

Se você está procurando criar seus próprios jogos no Linux, este guia vai te mostrar como instalar a Godot em diferentes distribuições.

## O Que é a Godot Engine?

A Godot é um **motor de jogos** altamente flexível, projetado para permitir o desenvolvimento de jogos de forma intuitiva e eficiente.

Com ela, você pode criar jogos tanto em 2D quanto em 3D, utilizando uma interface amigável e um sistema de script poderoso.

Sendo de código aberto, ela é gratuita e continuamente atualizada pela comunidade.

## Instalando a Godot no Linux

A instalação da Godot no Linux pode variar dependendo da distribuição que você usa.

Abaixo, estão instruções para algumas das distribuições Linux mais populares, além de uma opção geral de instalação usando o site oficial da Godot.

### Arch Linux

Para usuários de Arch Linux, a instalação da Godot pode ser feita diretamente a partir do gerenciador de pacotes `pacman`.

Abra o terminal e execute o seguinte comando:

```bash
sudo pacman -S \
godot
```

### openSUSE Tumbleweed

Se você está usando o [openSUSE Tumbleweed](https://get.opensuse.org/tumbleweed/), pode instalar a Godot usando o gerenciador de pacotes `zypper` com o comando abaixo:

```bash
sudo zypper install \
godot
```

### Instalação via Flathub

Caso a sua distribuição Linux tenha suporte a [Flatpak](https://flatpak.org/), você pode utilizar o [Flathub](https://flathub.org/) para realizar a instalação da Godot engine:

- [https://flathub.org/apps/org.godotengine.Godot](https://flathub.org/apps/org.godotengine.Godot).

Também é possível realizar a instalação através do comando:

```bash
flatpak install flathub \
org.godotengine.Godot
```

### Instalação via site oficial

Caso sua distribuição Linux não tenha um pacote oficial da Godot ou você prefira usar a versão mais recente disponível no site oficial, siga os passos abaixo:

1. Acesse o [site oficial da Godot](https://godotengine.org/).
2. Baixe o binário da Godot.
3. Renomeie o arquivo baixado para `godot`.
4. Abrar um terminal e execute o comando `echo $PATH` para verificar os diretórios que aceitam arquivos binário.
5. Os diretórios mais comuns são `~/bin` e `~/.local/bin`.
6. Copie o binário para um desses diretórios.

#### 4 Configurando o ícone da Godot

Para tornar a Godot acessível diretamente do seu menu de aplicativos com um ícone dedicado, siga estas etapas adicionais:

Baixe o ícone da Godot [aqui](https://godotengine.org/press/), renomeie-o para `godot` e mova-o para um dos seguintes diretórios:

- `~/.icons`
- `~/.local/share/icons`

#### Configurando o lançador da Godot

Crie um arquivo de atalho no diretório `~/.local/share/applications` com o nome `godot.desktop`. O conteúdo do arquivo deve ser o seguinte:

```bash
[Desktop Entry]
Categories=Development;
Comment=Godot engine.
Exec=godot
Icon=godot
Name=Godot
Path=~/.local/share/applications
StartupNotify=true
Terminal=false
Type=Application
Version=1.0
```

Isso permitirá que você inicie a Godot diretamente do menu de aplicativos do seu ambiente gráfico.

## Conclusão

A instalação da Godot engine no Linux é simples e rápida, seja utilizando os repositórios oficiais da sua distribuição ou baixando diretamente do site da Godot.

Com este guia, você já pode começar a desenvolver seus jogos no Linux com facilidade.

Seja para projetos em 2D ou 3D, a Godot é uma escolha sólida e acessível.

Boa sorte no desenvolvimento dos seus jogos!

## Extra

### Visual Studio Code

- [godot-tools](https://marketplace.visualstudio.com/items?itemName=geequlim.godot-tools).
- [C# Tools for Godot](https://marketplace.visualstudio.com/items?itemName=neikeq.godot-csharp-vscode).
- [Godot Files](https://marketplace.visualstudio.com/items?itemName=alfish.godot-files).
