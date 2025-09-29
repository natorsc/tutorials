# Como instalar a ferramenta de linha de comando pipX

[Pipx](https://github.com/pypa/pipx) é uma ferramenta para gerenciar pacotes [Python](https://www.python.org/) que têm comandos de terminal.

Ela permite instalar e rodar pacotes Python de forma isolada, sem interferir com as dependências de outros pacotes ou com as dependências do sistema.

Aqui estão algumas das principais funcionalidades do pipx:

1. **Instalação e Execução Isolada**: Instala cada pacote em um ambiente virtual separado, garantindo que as dependências não conflitem.
2. **Gerenciamento de Pacotes**: Facilita a instalação, atualização e remoção de pacotes Python que têm comandos de terminal.
3. **Execução de Comandos**: Permite executar comandos de pacotes Python sem a necessidade de instalação prévia, usando `pipx run`.
4. **Ambientes Virtualizados**: Cria e gerencia automaticamente ambientes virtuais para cada pacote instalado.

## Como instalar o pipX

### macOS

```bash
brew install pipx
```

Para atualizar o pipX utilize o comando:

```bash
brew update && \
brew upgrade pipx
```

### Distribuições Linux

#### Ubuntu

```bash
sudo apt install \
pipx
```

#### Fedora:

```bash
sudo dnf install \
pipx
```

#### Arch:

```bash
sudo pacman -S \
python-pipx
```

#### Outras distribuições Linux

```bash
python3 -m pip install \
--user pipx
```

Para atualizar o pipX utilize o comando:

```bash
python3 -m pip install \
--user --upgrade pipx
```

### Microsoft Windows

#### [Scoop](https://scoop.sh/)

```bash
scoop install pipx
```

Para atualizar o pipX utilize o comando:

```bash
scoop update pipx
```

#### Pip (pip 19.0 ou superior)

```bash
python -m pip install pipx
```

Para atualizar o pipX utilize o comando:

```bash
python -m pip install --user --upgrade pipx
```

### Como usar o pipX

- Instalação de um pacote com pipX:

```bash
pipx install nome-do-pacote
```

- Execução de um comando sem instalação:

```bash
pipx run nome-do-pacote comando
```

- Atualização de um pacote:

```bash
pipx upgrade nome-do-pacote
```

- Desinstalação de um pacote:

```bash
pipx uninstall nome-do-pacote
```

### Exemplos de Uso

- Instalar e usar o formatador de código [black](https://github.com/psf/black):

```bash
pipx install black

# Para formatar um script Python:
black nome-do-script.py
```

- Executar [httpie](https://httpie.io/) sem instalá-lo permanentemente:

```bash
pipx run httpie https://example.com
```

## Conclusão

Pipx é uma ferramenta poderosa para desenvolvedores Python que frequentemente trabalham com diferentes ferramentas de linha de comando e querem manter um ambiente de desenvolvimento limpo e organizado.
