# Como compartilhar arquivos no GNOME Boxes (Host/Guest)

Gerenciar máquinas virtuais pode ser um divisor de águas para testar novos sistemas operacionais ou distribuições Linux, mas a transferência de arquivos entre o sistema operacional convidado e o hospedeiro costuma ser um obstáculo.

O [GNOME Boxes](https://help.gnome.org/users/gnome-boxes/stable/), é ferramenta de virtualização focada no desktop Linux, ele oferece uma solução elegante para esse problema.

Este guia completo vai te mostrar como configurar o compartilhamento de arquivos no GNOME Boxes, garantindo uma experiência de VM fluida e sem estresse.

## O que é o GNOME Boxes?

GNOME Boxes é uma ferramenta de virtualização intuitiva, similar ao [VirtualBox](https://www.virtualbox.org/) e [VMware](https://www.vmware.com/), que permite criar e gerenciar sistemas operacionais virtuais com uma interface gráfica simples.

- Sistema operacional convidado (Guest OS): É o sistema operacional que roda dentro da máquina virtual.
- Sistema operacional hospedeiro (Host OS): É o seu sistema operacional principal, onde o GNOME Boxes está instalado e em execução.

## Compartilhamento de arquivos no GNOME Boxes

O processo de compartilhamento de arquivos no GNOME Boxes envolve três etapas principais:

1. Instalar o pacote necessário no sistema operacional convidado para ativar o compartilhamento de arquivos.
2. Aprender a transferir arquivos do sistema operacional hospedeiro para o sistema operacional convidado (arrastar e soltar).
3. Aprender a transferir arquivos do sistema operacional convidado para o sistema operacional hospedeiro (através de uma pasta compartilhada).

## Passo 1: Instale o pacote SPICE no sistema operacional convidado

Para que seu sistema operacional convidado (seja Linux ou Windows) consiga compartilhar arquivos com o sistema operacional hospedeiro, é crucial instalar o pacote [SPICE](https://www.spice-space.org/).

Você pode instalá-lo usando o gerenciador de pacotes da sua distribuição.

### Debian - Ubuntu

```bash
sudo apt install \
spice-webdavd \
spice-client-gtk \
spice-vdagent
```

> O pacote `spice-vdagent` é importante para funcionalidades como resolução de tela automática e copiar/colar entre o convidado e o hospedeiro.

### Fedora

```bash
sudo dnf install \
spice-webdavd \
spice-gtk \
spice-vdagent
```

### Arch Linux

```bash
sudo pacman -Syu --needed \
spice \
spice-gtk \
spice-protocol \
spice-vdagent \
gvfs-dnssd
```

### Microsoft Windows

Se você estiver usando o Microsoft Windows como sistema convidado, precisará baixar e instalar os pacotes SPICE manualmente.

1. Acesse a página oficial de download do SPICE: [Clique aqui](https://www.spice-space.org/download.html).
2. Na seção **Guest** (Convidado) e em **Windows binaries** (Binários do Windows), baixe o `spice-guest-tools` e o **Spice WebDAV daemon** mais recente.
> Se o link do Spice WebDAV daemon abrir uma página, clique com o botão direito e selecione **Salvar link como**.
3. Instale ambos os pacotes e reinicie o sistema operacional convidado.

> **Importante**: Lembre-se que este pacote é necessário em **todos** os sistemas operacionais convidados. Cada vez que você criar uma nova VM, precisará instalar este pacote.

## Passo 2: Transferindo Arquivos do Hospedeiro para o Convidado (Arrastar e Soltar)

Este é o método mais simples para transferir arquivos.

1. Basta arrastar o arquivo desejado do seu sistema operacional hospedeiro para a janela da máquina virtual.
2. Você verá uma mensagem "Pronto para Receber Arquivo" aparecer na VM.
3. Os arquivos transferidos serão salvos automaticamente no diretório `Downloads` do sistema operacional convidado.

![Enviando arquivo para o sistema convidado GNOME Boxes drag and drop..](https://cdn.hashnode.com/res/hashnode/image/upload/v1748339825564/152f77f6-f63b-44c4-8e70-53b14ea4ad58.png)

Você também pode enviar arquivos usando o menu do GNOME Boxes:

1. Clique no menu hambúrguer (geralmente no canto superior direito da janela do Boxes).
2. Selecione a opção "Enviar Arquivo".

![Enviando arquivo para o sistema convidado no GNOME Boxes.](https://cdn.hashnode.com/res/hashnode/image/upload/v1748339841123/5eb786ec-b9e4-4202-b940-700c8f705ab1.png)

## Passo 3: Transferindo Arquivos do convidado para o hospedeiro (Pasta Compartilhada)

Esta abordagem é um pouco mais complexa, mas muito eficaz.

Ela utiliza o protocolo SPICE para montar uma pasta do sistema operacional hospedeiro, onde você pode deixar arquivos para serem transferidos.

1. Dentro do GNOME Boxes, clique no menu hambúrguer e selecione "Preferências".
2. Vá para a aba "Dispositivos e Compartilhamentos".
3. Na seção "Pasta Compartilhada", clique no botão "+".
4. Por padrão, ele sugerirá o local da pasta "Público" do seu sistema operacional hospedeiro, mas você pode alterá-lo para qualquer pasta de sua preferência.

![Configurando pasta compartilhada no GNOME Boxes.](https://cdn.hashnode.com/res/hashnode/image/upload/v1748339971081/e87499b7-7546-4da8-9e19-9b2de08e82d1.png)

Agora, no sistema operacional convidado:

- **Para GNOME 47 ou superior**: Abra o gerenciador de arquivos (Nautilus) e clique em "Rede". Em seguida, dê um duplo clique na pasta **spice client** para montá-la.
- **Para versões mais antigas do GNOME**: Vá para `Outros Locais > Redes > Pasta Spice Client`.

![Acessando pasta compartilhada no GNOME.](https://cdn.hashnode.com/res/hashnode/image/upload/v1748340032717/b06e9039-f2b6-4f1d-b160-eac7b37d7d03.png)

- **No KDE**: Abra o gerenciador de arquivos (Dolphin) e clique em "Rede".

![No KDE](https://cdn.hashnode.com/res/hashnode/image/upload/v1748340121633/c817f647-9eba-4872-b439-5565ab296879.png)

Após montar a pasta **Spice client**, você verá a(s) pasta(s) que você adicionou nas **Preferências** do GNOME Boxes.

Dentro dessas pastas compartilhadas, você pode criar novas pastas ou copiar e colar arquivos. Eles aparecerão instantaneamente no sistema operacional hospedeiro.

> O compartilhamento é de duas vias (compartilhamento bidirecional). Se você colocar algo na pasta compartilhada no sistema operacional hospedeiro, ele também ficará acessível na pasta montada no sistema operacional convidado.

## Solução de problemas

Se por algum motivo o sistema operacional hospedeiro não exibir a pasta compartilhada, acesse o gerenciador de arquivo clique em rede e digite o endereço:

```bash
dav://localhost:9843
```

![Acessando rede dav://localhost:9843](https://cdn.hashnode.com/res/hashnode/image/upload/v1748340187722/c73c8fa1-223b-457d-92c2-110d8e56b53d.png)

### Erro Conexão Recusada (Connection Refused)

Embora o compartilhamento de arquivos no GNOME Boxes seja uma excelente funcionalidade, você pode encontrar alguns problemas, como o erro "conexão recusada" ou "argumento inválido", especialmente em sistemas como o Ubuntu, mesmo seguindo todos os passos.

Nesses casos, você pode usar o endereço do servidor diretamente:

1. No Gerenciador de Arquivos (Nautilus), pressione `Ctrl + l` para destacar o painel de endereço.
2. Digite o seguinte endereço `dav://`[`localhost:9843`](http://localhost:9843):
3. Isso abrirá a pasta compartilhada no gerenciador de arquivos. Após abrir a pasta você pode adicionar a mesma no gerenciador de arquivos (Nautilus, Dolphin, etc) para acessá-la facilmente no futuro, sem precisar digitar o endereço novamente.
