# Como instalar a biblioteca libwebp

## O que é libwebp?

[Libwebp](https://developers.google.com/speed/webp?hl=pt-br) é uma biblioteca de software de código aberto desenvolvida pelo [Google](https://www.google.com.br/?hl=pt-BR) para codificar e decodificar imagens no formato WebP.

WebP, também criado pelo Google, é um formato de imagem que oferece alta qualidade com tamanhos de arquivo menores do que os formatos tradicionais como JPEG e PNG.

Isso significa que as imagens WebP carregam mais rapidamente, o que pode melhorar o desempenho e a experiência do usuário em sites e aplicativos.

A libwebp fornece uma maneira fácil de integrar a funcionalidade WebP em seus próprios programas.

Alguns dos recursos da libwebp incluem:

- Codificação e decodificação de imagens WebP.
- Suporte para imagens com e sem perdas.
- Suporte para transparência.
- Controle preciso sobre a qualidade da imagem.
- APIs fáceis de usar.

## Instalação

### Linux

#### Arch Linux

```bash
sudo pacman -S \
libwebp
```

#### Fedora

```bash
sudo dnf install \
libwebp
```

#### Ubuntu

```bash
sudo apt install \
libwebp
```

### macOS

#### Homebrew

```bash
brew install \
webp
```

> [https://formulae.brew.sh/formula/webp](https://formulae.brew.sh/formula/webp).

## Utilitário pré compilado

O Google fornece o utilitários pré compilados para os seguintes sistemas operacionais:

- Microsoft Windows (x64).
- Linux (aarch64).
- Linux (x86-64).
- macOS (arm64).
- macOS (x86-64).

Para baixar o utilitário acesse:

- [https://developers.google.com/speed/webp/docs/precompiled](https://developers.google.com/speed/webp/docs/precompiled).

Após realizar o download descompacte o arquivo que foi baixado em um diretório onde o **mesmo não será removido**.

Em seguida adicione a pasta `bin` ao `PATH` do sistema operacional.

### Linux

Edite o arquivo `*.bashrc` e adicione o caminho até a basta `bin`:

```bash
export PATH="caminho/nome-da-pasta/bin:$PATH"
```

Algumas distribuições Linux já possuem as pastas `$HOME/.local/bin` e `$HOME/bin` mapeadas na variável `PATH`.

Neste caso basta **copiar os binário** da pasta `bin` para uma das pastas `bin` do sistema operacional.

Se houver a necessidade de mapear esses diretórios na variável `PATH` do sistema operacional, os seguintes comandos podem ser utilizados:

```bash
echo 'export PATH="$HOME/bin:$PATH"' \
>> ~/.bashrc
```

ou

```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' \
>> ~/.bashrc
```

Após adicionar é necessário executar:

```bash
source ~/.bashrc
```

### macOS

Adicione o caminho até a pasta `bin` no arquivo `.bash_profile`:

```bash
export PATH="$PATH:caminho/nome-da-pasta/bin"
```

Ou adicione um arquivo com o caminho no diretório `paths.d`:

```bash
sudo -s 'echo "caminho/nome-da-pasta/bin" > /etc/paths.d/libwebp'
```

### Microsoft Windows

Abra o aplicativo **Variáveis de Ambiente**:

`Advanced system settings` -&gt; `Environment variables` -&gt; `Path` -&gt; `Edit`.

E adicione o caminho até a pasta `bin`.
