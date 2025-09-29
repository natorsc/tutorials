Como instalar a linguagem de programação Go (Golang)

Hoje veremos como realizar a instalação da linguagem de programação Go (Golang) no **Linux**, **macOS** e **Microsoft Windows**.

## O que é Golang?

[Golang](https://go.dev/), também conhecida como **Go**, é uma linguagem de programação de código aberto criada pelo Google.

Ela foi projetada por Robert Griesemer, Rob Pike e Ken Thompson e lançada pela primeira vez em 2009.

Go é conhecida por sua simplicidade, eficiência e suporte robusto para programação concorrente. Aqui estão alguns pontos-chave sobre a linguagem.

### Características principais

1. **Sintaxe simples**: Go foi projetada para ser fácil de ler e escrever, com uma sintaxe clara e minimalista.
2. **Desempenho elevado**: Compila para código de máquina, proporcionando desempenho comparável ao **C** ou **C++**.
3. **Concorrência**: Go tem suporte nativo para concorrência através das **goroutines**, que são leves e eficientes, permitindo a execução de múltiplas tarefas simultaneamente.
4. **Bibliotecas padrão ricas**: Inclui um conjunto abrangente de bibliotecas padrão, cobrindo uma ampla gama de funcionalidades comuns.
5. **Compilação rápida**: Go foi projetada para compilar rapidamente, o que facilita a construção de grandes sistemas.
6. **Gerenciamento de memória automático (Garbage Collection)**: Go gerencia automaticamente a memória, ajudando a prevenir vazamentos de memória e outros problemas comuns em linguagens que requerem gerenciamento manual da memória.

### Utilização

Go é amplamente utilizado em várias áreas da tecnologia, com destaque para as seguintes aplicações:

- **Desenvolvimento web**: Muitas bibliotecas e frameworks foram desenvolvidos para suportar a construção de aplicativos web com Go, como **Gin** e **Echo**.
- **Serviços de backend**: Ideal para construir servidores web e serviços de backend devido ao seu desempenho e capacidade de lidar com múltiplas conexões simultâneas.
- **Ferramentas de sistema**: Adequada para construir ferramentas de linha de comando e software de sistema pela sua eficiência e capacidade de acessar diretamente a API do sistema operacional.

### Ecossistema e comunidade

Go tem uma **comunidade ativa e crescente**, com contribuições de desenvolvedores de todo o mundo. Sua popularidade continua a aumentar devido ao seu foco em desempenho e simplicidade.

## Instalação

### macOS

#### Homebrew

```bash
brew install \
go
```

### Linux

#### Arch Linux

Site oficial da distribuição Linux [Arch Linux](https://archlinux.org/).

```bash
sudo pacman -S \
go \
go-tools
```

#### Fedora

Site oficial da distribuição Linux [Fedora](https://fedoraproject.org/).

```bash
sudo dnf install \
golang \
golang-x-tools
```

#### Ubuntu

Site oficial da distribuição Linux [Ubuntu](https://ubuntu.com/download).

```bash
sudo apt install \
golang \
golang-golang-x-tools
```

##### Snap

```bash
sudo snap install \
go --classic
```

### Microsoft Windows

#### MSYS2

```bash
pacman -S \
mingw-w64-x86_64-go
```

#### Winget

```bash
winget install --id=GoLang.Go  -e
```

## Instalando a linguagem de programação Go a partir do binário

Para ter acesso a versão mais recente da linguagem de programação [Go](https://go.dev/dl/) (golang) pode ser necessário realizar a instalação através do binário que é fornecido no site oficial.

Faça download da versão compatível com o seu sistema operacional.

> ⚠️ No [Microsoft Windows](https://www.microsoft.com/windows/) e no [macOS](https://www.apple.com/br/macos/), de 2 clique no arquivo que foi baixado e a instalação será iniciada.

Em distribuições Linux descompacte o arquivo que foi baixado e copie o conteúdo para o diretório `/usr/local`:

```bash
rm -rf /usr/local/go && \
tar -C /usr/local -xzf go1.22.4.linux-amd64.tar.gz
```

Agora **abra um** dos seguintes arquivos:

- `~/.bashrc`.
- `~/.bash_profile`.
- `~/.bash_login`.
- `~/.profile`.

E adicione o caminho `/usr/local/go` ao `PATH` do sistema operacional:

```bash
export PATH=$PATH:/usr/local/go/bin
```

## Exemplo básico

Para iniciar um projeto com a linguagem de programação Go acesse a pasta do seu projeto e execute:

```bash
go mod init nome-do-projeto
```

Com o seu editor de texto ou IDE preferida crie um arquivo chamado `main.go` e digite o seguinte código.

```go
package main

import "fmt"

func main() {
    fmt.Println("Olá, Mundo!")
}
```

Para executar o programa que foi criado:

```bash
go run main.go
```

Para compartilhar o programa na forma de um binário executável utilize o comando:

```bash
go build nome-do-arquivo.go
```

> ⚠️ Será gerado um binário para o sistema operacional em que o comando foi executado.

Para gera um binário para outro sistema operacional (cross-compile) utilize o comando:

```bash
GOOS=darwin GOARCH=arm64 go build nome-do-arquivo.go
```

No caso, o comando acima está gerando um binário para os computadores da Apple que possuam arquitetura de processador `ARM` (M1, M2, etc).

Outros valores válidos para os parâmetros `GOOS` e `GOARCH` são:

| **GOOS** | **GOARCH** |
| --- | --- |
| aix | ppc64 |
| android | 386 |
| android | amd64 |
| android | arm |
| android | arm64 |
| darwin | amd64 |
| darwin | arm64 |
| dragonfly | amd64 |
| freebsd | 386 |
| freebsd | amd64 |
| freebsd | arm |
| freebsd | arm64 |
| freebsd | riscv64 |
| illumos | amd64 |
| ios | amd64 |
| ios | arm64 |
| js | wasm |
| linux | 386 |
| linux | amd64 |
| linux | arm |
| linux | arm64 |
| linux | loong64 |
| linux | mips |
| linux | mips64 |
| linux | mips64le |
| linux | mipsle |
| linux | ppc64 |
| linux | ppc64le |
| linux | riscv64 |
| linux | s390x |
| linux | sparc64 |
| netbsd | 386 |
| netbsd | amd64 |
| netbsd | arm |
| netbsd | arm64 |
| openbsd | 386 |
| openbsd | amd64 |
| openbsd | arm |
| openbsd | arm64 |
| openbsd | mips64 |
| openbsd | ppc64 |
| openbsd | riscv64 |
| plan9 | 386 |
| plan9 | amd64 |
| plan9 | arm |
| solaris | amd64 |
| wasip1 | wasm |
| windows | 386 |
| windows | amd64 |
| windows | arm |
| windows | arm64 |

---

## Extra

### Plugins para editores de texto e IDEs

* [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=golang.go).
* [GoLand (JetBrains)](https://www.jetbrains.com/go).
* [Vim](https://github.com/fatih/vim-go).
