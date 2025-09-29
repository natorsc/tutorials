# Como criar um projeto com Golang

## Criando um projeto

```bash
# 1. Crie uma pasta para o seu novo projeto
mkdir meu-primeiro-go-app

# 2. Navegue para dentro dessa pasta
cd meu-primeiro-go-app
```

```bash
# 3. Inicialize o módulo Go
go mod init exemplo.com/meu-primeiro-go-app
```

> Você acabou de criar um arquivo chamado `go.mod` dentro da sua pasta! Se você der uma olhada nele (`cat go.mod` no Linux/macOS ou `type go.mod` no Windows), verá algo parecido com:

```go
module exemplo.com/meu-primeiro-go-app

go 1.24 // A versão do Go pode variar
```

Este arquivo é como a carteira de identidade do seu projeto Go.

Ele é essencial para o Go entender o que seu projeto é e quais pacotes ele usa.

## Olá, Mundo!

Agora que a estrutura está pronta, vamos escrever nosso primeiro programa Go. Por tradição, começaremos com o clássico "Olá, Mundo!".

Crie um novo arquivo chamado `main.go` dentro da pasta `meu-primeiro-go-app`.

Você pode usar seu editor de código favorito ou, se preferir o terminal:

```bash
# No Linux/macOS
touch main.go

# No Windows
echo "" > main.go
```

Agora, edite o arquivo `main.go` e adicione o seguinte código:

```go
package main

import "fmt"

func main() {
    // Exibe uma mensagem no console
    fmt.Println("Olá, Go! Meu primeiro aplicativo está rodando!")
}
```

**Entendendo o Código:**

- `package main`: Indica que este é um programa executável. Todo executável Go precisa do pacote `main`.
- `import "fmt"`: Importa o pacote `fmt` (de "format"), que nos dá funções para formatar e imprimir textos, como o que vamos usar.
- `func main()`: Esta é a função principal do seu programa. Quando você o executa, o Go começa por aqui.
- `fmt.Println(...)`: A função `Println` do pacote `fmt` imprime o texto entre parênteses na tela e adiciona uma nova linha.

## Executando o código Go

Com o código pronto, é hora de ver a mágica acontecer! Certifique-se de que você ainda está no diretório `meu-primeiro-go-app` no seu terminal e execute:

```bash
go run main.go
```

Você deverá ver a mensagem:

```bash
Olá, Go! Meu primeiro aplicativo está rodando!
```

Parabéns! Seu primeiro programa Go está no ar!

## Compilando o projeto (Gerando o Executável)

"Exportar" um projeto Go significa, na verdade, **compilá-lo** em um arquivo executável.

A grande vantagem do Go é que ele cria um **único arquivo binário autônomo**, ou seja, você não precisa se preocupar em levar centenas de arquivos ou bibliotecas junto com seu programa.

O executável já tem tudo o que precisa!

Para compilar, usamos o comando `go build`:

```bash
go build
```

**O que acontece agora?** Após a execução, um novo arquivo será criado na sua pasta:

- No **Linux/macOS**: `meu-primeiro-go-app` (o nome da sua pasta principal)
- No **Windows**: `meu-primeiro-go-app.exe`

Este é o seu programa compilado! Você pode executá-lo diretamente:

```bash
./meu-primeiro-go-app # No Linux/macOS
meu-primeiro-go-app.exe # No Windows
```

Ele produzirá a mesma saída de antes. Incrível, não é?

Você tem um executável independente!

## Cross-compilação em Go!

Aqui é onde o Go realmente brilha!

Uma das suas características mais amadas é a **cross-compilação nativa**.

Isso significa que você pode compilar seu código para diferentes sistemas operacionais (Windows, Linux, macOS) e arquiteturas de processador (32-bit, 64-bit, ARM) a partir do seu próprio computador, sem precisar de máquinas virtuais ou configurações complicadas.

Para fazer isso, usamos duas variáveis de ambiente:

* `GOOS`: Define o sistema operacional alvo (ex: `windows`, `linux`, `darwin` para macOS).
* `GOARCH`: Define a arquitetura do processador alvo (ex: `amd64` para 64-bit, `arm64` para Apple Silicon ou Raspberry Pi).

A sintaxe geral é:

```bash
GOOS=<sistema_operacional_alvo> GOARCH=<arquitetura_alvo> go build -o <nome_do_executavel>
```

### Exemplo 1: Compilando para Linux (64-bit)

Se você quer que seu programa rode na maioria dos servidores Linux:

```bash
# Se você está no Linux/macOS:
GOOS=linux GOARCH=amd64 go build -o meu-programa-linux

# Se você está no Windows (usando PowerShell):
$env:GOOS="linux"; $env:GOARCH="amd64"; go build -o meu-programa-linux
Remove-Item Env:GOOS, Env:GOARCH # Para limpar as variáveis de ambiente

# Se você está no Windows (usando Prompt de Comando):
set GOOS=linux
set GOARCH=amd64
go build -o meu-programa-linux
set GOOS=
set GOARCH=
```

Um arquivo `meu-programa-linux` será criado.

### Exemplo 2: Compilando para Windows (64-bit)

Se seu objetivo é o sistema operacional Windows:

```bash
# Se você está no Linux/macOS:
GOOS=windows GOARCH=amd64 go build -o meu-programa-windows.exe

# Se você está no Windows (usando PowerShell):
$env:GOOS="windows"; $env:GOARCH="amd64"; go build -o meu-programa-windows.exe
Remove-Item Env:GOOS, Env:GOARCH

# Se você está no Windows (usando Prompt de Comando):
set GOOS=windows
set GOARCH=amd64
go build -o meu-programa-windows.exe
set GOOS=
set GOARCH=
```

Um arquivo `meu-programa-windows.exe` será criado.

### Exemplo 3: Compilando para macOS (Apple Silicon - M1/M2/etc)

Se você quer atingir os novos Macs com chips M-series:

```bash
# Se você está no Linux/Windows:
GOOS=darwin GOARCH=arm64 go build -o meu-programa-mac-m1
```

> Para ver todas as combinações `GOOS` e `GOARCH` que o Go suporta, execute no seu terminal `go tool dist list`.
