# Como restaurar chaves SSH"

## O que é uma chave SSH?

Uma chave SSH, ou chave de Secure Shell, é uma forma de autenticação e criptografia usada em conexões de rede seguras.

O Secure Shell (SSH) é um protocolo utilizado para acesso remoto a sistemas e execução de comandos de forma segura, protegendo a comunicação entre o cliente e o servidor.

A chave SSH é composta por duas partes:

**Chave privada**: A chave privada **deve** ser mantida em segredo e guardada pelo usuário. **Chave pública**: A chave pública pode ser compartilhada livremente.

A ideia é que a chave privada só funcione com a chave pública correspondente.

Quando um usuário se conecta a um servidor SSH, ele usa sua chave privada para provar que tem a chave pública correspondente, autenticando-se de maneira segura e eliminando a necessidade de senhas.

O uso de chaves SSH é comum em ambientes de administração de servidores, sistemas remotos e integração contínua, proporcionando uma camada adicional de segurança em comparação com autenticação baseada em senha.

## Tipos de chaves SSH

- **ed25519**: É um tipo de chave assimétrica utilizado no protocolo SSH para autenticação e criptografia. Ela faz parte de uma família de curvas elípticas conhecida como Curve25519, que foi projetada para oferecer um alto nível de segurança com eficiência computacional.
- **RSA (Rivest-Shamir-Adleman)**: Um dos algoritmos mais antigos e amplamente utilizados. Embora ainda seja suportado, o Ed25519 é considerado mais seguro e eficiente.
- **DSA (Digital Signature Algorithm)**: Também um algoritmo mais antigo, mas ainda suportado pelo SSH.
- **ECDSA (Elliptic Curve Digital Signature Algorithm)**: Utiliza curvas elípticas para gerar as chaves, oferecendo um bom equilíbrio entre segurança e eficiência.
- **RSA com SHA-2 (RSA usando algoritmos de hash da família SHA-2)**: RSA pode ser usado com algoritmos de hash mais recentes para melhorar a segurança.
- **ECDSA com SHA-2 (ECDSA usando algoritmos de hash da família SHA-2)**: Assim como no caso do RSA, o ECDSA pode ser combinado com algoritmos de hash mais seguros.

Embora essas sejam algumas das opções mais comuns, a preferência por uma chave específica pode depender de fatores como segurança, eficiência e suporte do sistema e das implementações do SSH.

> 📝 O uso de `ed25519` tem ganhado popularidade devido à sua segurança e eficiência em comparação com algumas das opções mais antigas.

## Como restaurar as chaves SSH

Para restaurar as suas chaves SSH copie as mesmas para a pasta `.ssh`.

Caso a pasta `.ssh` não exista crie a mesma:

- **Linux**: `~/.ssh/`. Atalho é equivalente a `/home/seu-usuário/.ssh`.
- **macOS**: `~/.ssh/`. Atalho é equivalente a `/Users/seu-usuário/.ssh`.
- **Windows**: `%HOMEPATH%\.ssh\`. Atalho é equivalente a `C:\Users\seu-usuário\.ssh`.

Em seguida copie as chaves para a pasta `.ssh` que foi criada.

## Definindo as permissões das chaves SSH

Após restaurar as chaves SSH é necessário definir as permissões corretas.

Definindo o proprietário das chaves:

```bash
sudo chown -R $(whoami):$(whoami) ~/.ssh
```

Definindo a permissão da pasta:

```bash
chmod 700 ~/.ssh
```

Definindo a permissão da chave privada:

```bash
chmod 600 ~/.ssh/id_ed25519
```

Definindo a permissão da chave publica:

```bash
chmod 644 ~/.ssh/id_ed25519.pub
```

Outros arquivos (caso existam):

```bash
chmod 644 ~/.ssh/authorized_keys
chmod 644 ~/.ssh/known_hosts
chmod 644 ~/.ssh/config
```

Assim que as permissões estiverem definidas devemos adicionar a chave privada no gerenciador de chaves.

Para verificar se o gerenciador de chaves está em execução:

```bash
eval "$(ssh-agent -s)"
```

Por fim adicionamos a chave SSH privada no gerenciador com o comando:

```bash
ssh-add ~/.ssh/id_ed25519
```
