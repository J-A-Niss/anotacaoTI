# Drivers
- Resumidamente é um software que indica como que o hardware deve agir por meio de comunicaçao com o OS.  

## Dispositivos
### Windows
- Todos estão agrupados em um gerenciador de dispositivos. Pode ser acessado pela GUI, por meio de *'botão direito no' > "Este computador" > "gerenciar" > "gerenciador de dispositivos"*  ou do comando *"devmgmt.msc"* na caixa de dialogo do "Executar". O sistema [Plug and Play" ou PNP](https://learn.microsoft.com/en-us/windows-hardware/drivers/kernel/introduction-to-plug-and-play) que o Windows usa para detectar novo hardware conectado ao computador automaticamente e depois ele reconhece e instala o software correto para gerenciá-lo.
#### OS
- É crucial manter atualizado por varios motivos, mas especialmente por motivos de segurança, o [Windows Update Client Server](https://en.wikipedia.org/wiki/Windows_Update) acaba realizando isso de modo autonomo e em segundo plano. Ele faz isso mantendo contato com os servidores de atualização da Microsoft e baixando as atualizações.

### [Linux](https://pt.wikipedia.org/wiki/Arquivo_de_dispositivo)
#### Ubuntu
- Possui varios tipos de dispositivos, mas dois mais comuns:
    1. **Dispositivo de caractere**; este transfere caractere por carac. como por exemplo mouse & teclado.           -c
    2. **Disp. de bloco**; este transfere um bloco de dado, que em torno, é usado apenas para armazenamento de dado. -b
- Dispositivos SD são disp. de armazenamento em massa como por exemplo o disco rígido.   

- No Linux, o comando "*apt upgrade*" não atualiza o OS, e diferente do Windows que o OS é o *Windows*, no Linux é o [kernel e alguns outros pacotes](https://en.wikipedia.org/wiki/Linux_kernel); o kernel controla os componentes centrais do OS, sendo nesse o caso o kernel um pacote como qualquer outro.
- O [comando](https://www.cyberciti.biz/faq/how-do-i-update-ubuntu-linux-softwares/) *"uname"* exibe as informações do sistema, e o sinalizador *-r* a versão. [Para mais info. em como atualizar.](https://www.linux.com/learn/linux-101-updating-your-system)