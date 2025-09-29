# Como instalar programas no macOS usando o Homebrew

Se você é um usuário do [macOS](https://www.apple.com/br/macos/) e deseja ter mais facilidade na instalação, atualização e remoção de pacote e programas em seu sistema, o [Homebrew](https://brew.sh/) é a ferramenta que você está procurando.

## O que é o Homebrew?

O Homebrew é um gerenciador de pacotes de código aberto escrito em [Ruby](https://www.ruby-lang.org/) por Max Howell em 2009 .

Da mesma forma que outros gerenciadores de pacotes como:

- `apt`.
- `dnf`.
- `pacman`.
- `winget`.

O Homebrew permite a instalação, atualização e remoção de pacotes e aplicativos através do terminal do macOS.

## Como Instalar o Homebrew no macOS

A instalação do Homebrew é simples e rápida.

Siga os passos abaixo para configurar o Homebrew em seu macOS:

1. **Abra o Terminal**: Você pode encontrar o Terminal em `**Aplicativos > Utilitários > Terminal**`.
2. **Instale o Homebrew**: No Terminal que foi aberto execute o seguinte comando:

```bash
/bin/bash -c \
"$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

> ⚠️ Durante a instalação pode ser solicitada a senha do seu usuário.

> ⚠️ Durante a instalação nenhum erro deve ser retornado no terminal.

Após finalizar a instalação precisamos adicionar o Homebrew ao PATH do sistema operacional:

```bash
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') \
>> /Users/$USER/.zprofile
```

Agora devemos recarregar as variáveis de ambiente do sistema operacional:

```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Para confirmar a instalação pode ser executado o comando:

```bash
brew --version
```

Se tudo ocorreu bem, você verá a versão do Homebrew que está instalada no seu sistema operacional.

## Utilizando o Homebrew

### Instalando pacotes (formulae)

Agora que o Homebrew está instalado, você pode começar a utilizar seus recursos para instalar novos pacotes.

Por exemplo, podemos utilizar o comando `search` para procurar pelas versões da linguagem de programação [Python](https://www.python.org/) que estão disponíveis:

```bash
brew search \
python@3.1
```

Também é possível realiza a pesquisa de pacotes de forma visual através do site:

- [https://formulae.brew.sh/formula/](https://formulae.brew.sh/formula/).

Após localizar o pacote basta realizar a instalação do mesmo com o comando:

```bash
brew install \
python@3.12
```

### Instalando aplicativos (cask)

Para realizar a instalação de aplicativos no Homebrew devemos utilizar a flag `--cask`.

Por exemplo, para realizar a instalação do navegador de internet [Firefox](https://www.mozilla.org/firefox/new/) no macOS devemos utilizar o `search` para verificar se o pacote existe o mesmo as versões do mesmo:

```bash
brew search \
--cask \
firefox
```

Sim, você também pode realizar a consulta através do site:

- [https://formulae.brew.sh/cask/](https://formulae.brew.sh/cask/).

Após localizar a versão desejada, basta executar no terminal:

```bash
brew install \
--cask \
firefox
```

## Outro comandos

Atualizar os pacotes e aplicativos instalados:

```bash
brew update && \
brew upgrade
```

Atualizar um determinado pacote:

```bash
brew update \
nome-do-pacote
```

Remover um determinado pacote:

```bash
brew uninstall \
nome-do-pacote
```

Ou:

```bash
brew remove \
nome-do-pacote
```
