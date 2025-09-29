# Como instalar o OpenJDK em diferentes sistemas operacionais

[OpenJDK](https://openjdk.org) (Open Java Development Kit) é uma implementação gratuita e de código aberto da plataforma Java Standard Edition (Java SE).

Ela é desenvolvida pelo Oracle Corporation e pela comunidade de desenvolvedores sob o Java Community Process (JCP).

O OpenJDK é a base da maioria das distribuições de Java e é amplamente utilizado para desenvolvimento e execução de aplicativos Java.

## Pontos principais sobre o OpenJDK

1. **Código Aberto**: O código-fonte do OpenJDK está disponível sob a licença GPL (General Public License), permitindo que desenvolvedores o usem, modifiquem e distribuam livremente.
2. **Compatibilidade**: O OpenJDK é compatível com a especificação Java SE, o que significa que os programas desenvolvidos com o OpenJDK devem ser executáveis em qualquer outra implementação compatível com Java SE.
3. **Componentes**: O OpenJDK inclui uma série de componentes necessários para o desenvolvimento Java, incluindo:
    - O compilador Java (javac).
    - A Máquina Virtual Java (JVM).
    - Bibliotecas de classes padrão.
    - Ferramentas para depuração e monitoramento.
4. **Desenvolvimento Comunitário**: O desenvolvimento do OpenJDK é aberto e colaborativo, com contribuições de várias organizações e desenvolvedores individuais.

## Atualizações do OpenJDK

O OpenJDK recebe atualizações regulares de segurança e correções de bugs.

Também há lançamentos de novas versões principais a cada seis meses, conforme o ciclo de lançamento do Java.

O OpenJDK é uma escolha popular tanto para desenvolvimento quanto para implantação de aplicativos Java, devido à sua natureza aberta e ao forte suporte da comunidade.

## O que é JDK e JRE?

O JDK (Java Development Kit) e o JRE (Java Runtime Environment) são componentes essenciais do ecossistema Java, cada um servindo a um propósito específico no desenvolvimento e execução de aplicativos Java.

### JDK (Java Development Kit)

O JDK contém o JRE.

Usado por desenvolvedores de software para escrever, compilar e depurar programas Java.

### JRE (Java Runtime Environment)

Usado por usuários finais e servidores para executar programas Java.

Não inclui ferramentas de desenvolvimento, como o compilador.

## Como instalar o OpenJDK

### macOS

```bash
brew install \
openjdk
```

### Linux

#### Arch Linux

```bash
sudo pacman -S \
jdk-openjdk
```

#### Fedora

```bash
sudo dnf install \
java-latest-openjdk-devel
```

#### Ubuntu

```bash
sudo apt install \
openjdk-21-jdk
```

## Microsoft Windows

### Winget

```bash
winget install `
Microsoft.OpenJDK.21
```

### Pacote MSI

Acesse o site:

- [https://learn.microsoft.com/pt-br/java/openjdk/download#openjdk-21](https://learn.microsoft.com/pt-br/java/openjdk/download#openjdk-21)

Baixe o pacote MSI e de 2 cliques sobre o mesmo para iniciar a instalação.
