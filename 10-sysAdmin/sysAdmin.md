# 1.[***SysAdmin***](https://github.com/J-A-Niss/anotacaoTI/blob/main/10-sysAdmin/sysAdmin01.md)
- Sysadmin é o administrador; quem administra o(s) sistema(s); o responsável por fazer com que as coisas funcionem direito.
- Gravar as ações pode ajudar com resolução de problemas, anotar de qualquer modo que seja, as ações feitas pode ser usado como um guia do que foi feito e do que aconteceu.
- Comandos como o `script` em Linux e o ` Start-Transcript` no powershell ajudam a gravar os comandos usados nos respectivos CMDs, para auxiliar em possiveis resoluções.
- Gravar a seção tambem, com programas como *OBS* ou o *recordMyDesktop* tambem auxilia.
	
## 1.1.**Servidor**
- Software ou máquina que providencia serviços à outros softwares e máquinas; por exemplo um webserver armazena e providencia conteúdo à clientes através da internet.

##### 1.1.1.[KVM Switch, Keyboard Video Mouse](https://en.wikipedia.org/wiki/KVM_switch)
- Dispositivo que permite um usuário controlar varios computadores com um ou mais setups de mouse, teclado e monitor.    
							
#### 1.2.Produção
- Partes da infraestrutura onde um serviço é executado ao cliente. Para qualquer alteração feita, deve ser antes testada em um **ambiente de teste**; uma VM rodando a mesma config. da produção, mas que não ta disponível ao cliente.
- Tambem é recomendável ter uma maquina secundária de stand-by com as mesmas especificações da principal, para que possa redirecionar o tráfego durante a aplicação das alterações; o objetivo é nunca tirar o acesso do cliente ao serviço.
							
#### 1.3.Reprodução do caso
- Metodologia usada para retraçar passos que levaram a um erro:
1. *O que foi feito para chegar nesse ponto.*
2. *O que aconteceu de inesperado.*
3. *O que era para acontecer.*

### 1.2.Cliente
- Quem acessa e usa seus serviços.

# 2.***Nuvem***   

## 2.1.[Cloud computing](https://colab.research.google.com/drive/1ZmYM90FYDxNtBGZEISQj4bY5jaE8Rr-M#scrollTo=gpOAAL87zrL5)
- Conceito de que voce pode acessar todo conteúdo da internet em qualquer lugar do mundo por meio da Nuvem contanto que se tenha conexão à internet; Na verdade é uma rede de computadores que armazena e processa dados **DataCenters** ao redor do mundo todo, que são centros de servidores especificamente designados para armazenar dados.
- A computação em nuvem tem alguns benefícios, como menor custo inicial, serviços acessíveis de qualquer lugar do mundo que tenha conexão com a internet, e atualizações de software gerenciadas por outra empresa.
- Com a computação local, você controle tudo da sua infraestrutura de TI e pode atualizar e proteger sua organização o tempo todo.  
					
### 2.2 [*Infrastructure as a Service*](https://cloud.google.com/learn/what-is-iaas?hl=pt-br#:~:text=IaaS%2C%20or%20Infrastructure%20as%20a,way%20requires%20time%20and%20capital.) 
- Um tipo de terceirização de infraestrutura de redes por meio da nuvem; que dispõe de VMs designadas para atuar nas diversas areas, aplicação, dados, virtualização, servidores etc, como se fosse uma máquina presencial/real.
- Nesse caso **voce** é o gerente do serviço e determina como ele será gerido. Essa nuvem pode ser publica, privada ou híbrida;
	 
1. **Publica** é um serviço de nuvem fornecido ao público por terceiros
2. **Privada** é o serviço particular de uma organização específica que detem todo serviço, ou físicamente no local ou em um DataCenter
3. **Híbrida** é um pouco de ambos de modo integrado ao ponto que migrar de um a outro não traga problemas.
     
#### 2.2.1 **Regiões**
- Esse serviço é separado por regiões que são **locais geográficos que contêm os DataCenters**, cada DataCenter é separado por zona, e cada zona é plenamente independente uma da outra de modo que se um DataCenter fica offline por qualquer razão é possível migrar os usuários para outro sem que sequer seja notado; também é questão importante no que tange latência e distancia entre provedor e cliente.

### 2.3 [*Networking as a Service*](https://en.wikipedia.org/wiki/Network_as_a_service)
- Identico ao IaaS, porém, focado no aspecto de networking (redes) para que a empresa não tenha que lidar com o custoso hardware de rede.   

### 2.4 [*Platform as a Service*](https://www.business.com/articles/8-ways-cloud-computing-can-increase-productivity/)
- Identico, porém, focado na plataforma; com objetivo de auxiliar em compilação de código, armazenamento de dados e entrega de aplicativos.   

### 2.5 *Software as a Service*
- O software ja vêm pré-configurado e o usuário final não lida com a configuração da nuvem. O provedor gerencia tudo relacionado ao serviço.
 
# 3.[**Server OS**](https://phoenixnap.com/kb/server-operating-system)
- OS dedicado à funcionalidade de um servidor. Quase todos distribuidores possuem um OS dedicados para servidores	
- [conexões remotas](https://www.coursera.org/learn/administracao-de-sistemas-servicos-infraestrutura-ti/supplement/LgiZ5/conexoes-remotas)  
- [OpenSSH](https://en.wikipedia.org/wiki/OpenSSH)   

# 4.[**File Transfer Protocol**](https://en.wikipedia.org/wiki/Comparison_of_FTP_client_software)
- Forma de transferir arquivos via internet por meio de um servidor; não é muito seguro por não lidar com dado encriptado. Muito usado no compartilhamento de conteúdo web.
			
### 4.1.SFTP, *Secure File Transf. Protocol*
- Identico ao FTP, porem possui encripção nos dados, trazendo mais segurança às transferencias   

### 4.2.TFTP, *Trivial File Transfer Protocol*
- Não usa nem autenticação, muito popular com hospedação de arquivos de instalação.   
				
### 4.3.NetworkTimeProtocol
- Modo usado para sincronizar relógios em máquinas conectadas em uma rede. Usado por alguns programas de segurança que necessitam de sincronia dos relógios para funcionar.
- O modo exato de funcionamento varia de OS pra OS mas a ideia não muda.
 
# 5.***Serviços***   

## 5.1 No Linux
- Os arquivos de configuração estão no diretório `/etc`; por exemplo, a configuração do vsftpd está no diretório `etc/vsftpd.conf`

#### Comandos:
1. `service ntp status` indica o status do serviço, no caso o ntp
2. `sudo date -s "ano-mes-dia hr:min:seg"` para determinar a data e hora manualmente
3. `sudo service ntp stop` pausa o serviço, no caso o ntp
4. `sudo service ntp start` inicia o serviço
5. `sudo service ntp restart` reinicia o serviço por meio do `stop` e `start` simultaneamente
6. `sudo apt install vsftpd` instala o *vsftpd*, um simples servidor ftp
7. `lftp localholst` *lftp* é um programa cliente ftp que permite conectar a um servidor ftp
8. `sudo service vsftpds reload` o serviço recarrega, re-lendo as configurações do arquivo, sem sua interrupção
	 
## 5.2 No Windows
- Por meio da GUI pode se configurar os serviços.   

#### Comandos:
1. `Get-Service` lista todos serviços do windows
2. `Get-Service wuauserv` *wuauserv* significa windows update service
3. `Get-Service wuauserv | Format-List *` lista informações adicionais do serviço em questão
4. `Stop-Service wuauserv` pausa o windows update
5. `Start-Service wuauserv` inicia o windows update   

## 5.3 **Comunicação**
- Função essencial para qualquer organização, existem varios metodos para que funcionários se comuniquem entre si, aqui alguns listados:

### 5.3.1 IRC - Internet Chat Relay
- Protocolo usado para mensagens de bate-papo, operando em modelo cliente-servidor, sendo que muitos clientes IRC podem ser usados para se conectar à um servidor IRC.
- Muito usado nos anos 90, mas foi aos poucos substituido por chats de medias sociais como instagram e facebook.  

### 5.3.2 [Email](https://blog.servermania.com/what-protocols-send-receive-email-with-the-mail-server)
- Existem varios, os mais comuns são:    

1. **POP3**
- Post Office Protocol; baixa o email de um servidor de email direto ao cliente, e então, **deleta o email do servidor, no caso em que o email só podera ser visto em um unico dispositivo**.
- Util se quiser manter uma quota de armazenamento baixa, já que **o email é deletado do servidor**, mesma razão pela qual é util em questão de segurança e privacidade
2. **IMAP**
- Internet Message Adress Protocol; Parecido com o pop, **mas não deleta o email do servidor de emails**.
3. **SMTP**
- Simple Mail Transfer; usado para enviar os emails.   

#### 5.3.3 [Spam](https://colab.research.google.com/drive/1fEC2bfYk5LVaZWvNFlDB0n_tw1F9RqRx#scrollTo=FbimnQ22_vEI)
- É um tópico muito extenso que requer muita atenção, para mais informações, seguir o link.
- **Spam é definido como qualquer mensagem ou chamada não solicitada enviada para um grande número de destinatários**.   
  
##### 5.3.3.1 Tipos:
- **Phishing**; do ingles *fishing ou pescar*, tenta enganar a vítima a liberar informações como dados pessoais, logins, senhas etc.
- Pode se dar tambem por mensagens de texto; em via de regra, *todo tipo de comunicação falsa com intuito de enganar a vítima a liberar informação é considerado phishing*.
- **Clickbait**; do ingles '*isca*' de clique, tenta enganar a vítima com link que não leva ao endereço que indica levar.
- **Spoofing**; do ingles *imitar/fingir*, é uma mensagen/email enviada de um endereço que se apresenta como legítimo, mas não é.
- **Golpe de suporte técnico**; o golpista de finge ser do suporte técnico de uma companhia legítima, Microsoft por exemplo, e tem objetivo de obter informações da vítima.     

 ## 5.4 **Serviços de arquivo**   
 - Auxiliam na organização de arquivos em larga escala; seja salvando, baixando ou enviando, entre funcionários podendo ser da mesma organização ou de organizações diferentes.    

### 5.4.1 Servidores de Armaz. de Arquivos.
- Permitem o armazenamento e distribuição de arquivos de modo central. 
- [Este serviço tambem pode ser feito por meio da nuvem](https://www.cloudwards.net/comparison/).  

#### 5.4.1.1 Armaz. de Arquivos em rede   

##### NFS - **Network File System** (Sist. de arqui. em rede)
- Protocolo que permite compartilhação de arquivos pela rede.
- Compatível com *todos* OS.
- Configurado por um ambiente em Linux
	- *É possível instalar o software do servidor NFS e, em seguida, modificar os arquivos de configuração dos diretórios aos quais você quer permitir acesso compartilhado. Depois de fazer isso, o serviço NFS vai ser executado em segundo plano no servidor.*
	- *A partir dai, é só usar o nome de host ao invés do nome do disco rígido e acessar o diretório* `/share`
- Apesar disso, o NFS ainda possui algums problemas de compatibilidade com Windows.   

##### **Samba**
- **NFS do windows**, possui todas funcionalidades do NFS e ainda possui outro serviços como por exemplo serviço de impressora.
- Implementa o protocolo [**SMB**](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831795(v=ws.11)?redirectedfrom=MSDN)

##### NAS - **Network Attached Storage**
- Computador dedicado à armaz. de dados, possui um OS simplificado e MUITO espaço de armazenamento.  

#### [**Sincronização móvel**](https://colab.research.google.com/drive/1NAQxoDJ4mdpS3m1dB4w2J7tsnUeitjXJ#scrollTo=_hPMAALtg0Pm)
- Garante que os dados são iguais em dispositivos móveis. Geralmente isso é feito por meio da nuvem onde estão armazenados os dados originais.
	- Tanto iOS quanto Android possuem suporte de sincronia na nuvem.   

## 5.5 **Serviços de Impressora** 
- Organizações maiores precisam de um gerenciamente de impressoras mais robusto, devido ao fato que podem ter dezenas de diferentes impressoras funcionando. Normalmente isso é feito por meio de um servidor de impressões.   

### 5.5.1 [**Servidor de Impressão**](https://colab.research.google.com/drive/1BXvIwGGL-4-ZBjCpzBIBy0GonVvh2byw#scrollTo=ctmyMbkBpyls)
- Local central de gerenciamento de impressão, auxilia a tudo, desde a impressão ao gerenciamento físico das impressoras em si. Muitos OS ja vem com um serviço de impressão, então é necessário só instala-lo em um servidor.
	- ***No Linux*** o serviço é o [CUPS](https://en.wikipedia.org/wiki/CUPS); **Common UNIX Printing System** que o permite gerenciar o sistema de impressão por meio de uma URL.
- Esse serviço tambem pode ser gerenciado pela *nuvem*, associando impressoras à navegadores de WEB permitindo que os usuários imprimam sem precisar configurar nada nas máquinas.   

## 5.6 **Serviços de Plataforma**
- Providencia uma plataforma para que devs possam criar e implementar aplicativos de software por completo, sem ter que lidar com manutenções, rede e outros serviços associados às ferramentas da plataforma.   

### 5.6.1 [**Balanceadores de Carga**](https://colab.research.google.com/drive/1ko__xVFHgp2XpIW98OzDzfcHQHBYJrlC#scrollTo=5ANMCbfy62dZ)
- Balanceadores de carga monitoram e encaminham o tráfego de rede de entrada e saída de e para um pool de servidores físicos ou virtuais, podendo ser hardware ou software, distribuindo o tráfego de maneira uniforme ou conforme regras personalizadas, impedindo que o fluxo de tráfego sobrecarregue um servidor.
- Os recursos básicos dos servidores costumam incluir CPUs, RAM e largura de banda de rede, mas também podem oferecer outros recursos, como aplicativos, servidores de arquivos, serviços de banco de dados e muito mais. 
- Os balanceadores de carga também conseguem detectar quando um servidor falhou em redirecionar e equilibrar o tráfego de rede nos outros servidores. Além disso, os balanceadores dão a capacidade de adicionar e remover servidores do pool conforme necessário.   

#### 5.6.1.1 **Escalonamento Automático ou Autoscaling**
- Serviço que equilibra a carga de modo automático, ao ponto que cada VM só sera usada (e cobrada) conforme for necessário.

### 5.6.2 **Bancos de Dados**
- Permitem armazenar, consultar, filtrar e gerenciar grandes quantidades de dados.
- [MySQL, PostgreSQL & SQLite](https://www.digitalocean.com/community/tutorials/sqlite-vs-mysql-vs-postgresql-a-comparison-of-relational-database-management-systems)  

## 5.7 **Problemas de Serv. de Rede**
- Os navegadores de hoje têm ferramentas integradas que ajudam a diagnosticar problemas no navegador ou no próprio site por meio das ferramentas de desenvolvedor (**F12** na maioria dos browsers).   

### 5.7.1 [**Códigos de Status HTTP**](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
- Os códigos de status HTTP são códigos ou números que indicam algum tipo de erro ou mensagens informativas que ocorreram ao tentar acessar um recurso da Web.
```
    1xx informational response  – the request was received, continuing process
    2xx successful – the request was successfully received, understood, and accepted
    3xx redirection – further action needs to be taken in order to complete the request
    4xx client error – the request contains bad syntax or cannot be fulfilled
    5xx server error – the server failed to fulfil an apparently valid request
```    

## 5.8 **Serviços de Diretório**
- Contém serviços de busca que fornecem mapeamento entre recursos de rede e seus endereços, ou seja, usado para organizar e pesquisar objetos; de usuários à números de telefone compartilhados na rede. Auxilia no gerenciamento de usuários, ao invés de salvar todas informações localmente, salva tudo no mesmo servidor caso precise fazer alguma alteração geral de modo mais rápido.
- **Ou seja, são uteis para para organizar dados e torná-los pesquisáveis para uma organização** e isso é feito por meio de um modelo hierárquico de objetos e containers, esses chamados de Unidade Organizacional (*Organizational Units*)
    - *Identico à um sistema de arquivo (Arquivo e Pastas)*  
```
Domínio
    - Computadores
    - Usuários
        - Venda
            - Usuário 1
            - Usuário 2
        - Engenharia
            - Usuário 1
            - Usuário 2
        - Marketing
            - Usuário 1
            - Usuário 2
            - Usuário 3 
```    
### 5.8.1 **Replicação**
- Modo de copiar e distribuir a informação entre varios servidores físicos, mas ainda de modo 'unificado' para propositos de armazenamento e administração.
- Outra função é redução de latência ao ter réplicas da pesquisa do diretório localmente, em cada escritório.   

### 5.8.2 **X.500**
- Padrão de diretório, que inclui:
    1. *Directory Access Protocol, ou DAP*
    2. *Directory System Protocol, ou DSP*
    3. *Directory Information Shadowing Protocol, ou DISP*
    4. *Directory Operational Bindings Management Protocol, ou DOP*
- Microsoft tambem tem uma, chamada de *Active Directory* ou *AD*    

### 5.8.3 [**LDAP - Lightweigth Directory Access Protoc.**](https://en.wikipedia.org/wiki/LDAP_Data_Interchange_Format)
- Usado para acessar informações em diretórios de serviços numa rede.

#### 5.8.3.1 OpenLADP
- Um *LDAP* em código aberto que oferece suporte à varias plataformas incluindo Windows, UNIX, Linux e varios derivados.

##### 5.8.3.1.1 Forma do Registro:
- O registro é uma coleção de informações usadas para descrever algo, que se dá por:
```
dn:CN=Nome Sobrenome,OU=Sysadmin,DC=example,DC=com

dn | distinguished name
CN | common name of the object
OU | Organizational Unit
DC | domain component
```  
##### 5.8.3.1.2 Autenticação LADP
- Restringe o acesso de usuários à diretórios e é feito por meio de uma **vinculação**(*Bind Operation*) que vincula clientes ao servidor de diretório e que pode ser feita de 3 maneiras diferentes: 
1. Anônima
    - *Na real que não é uma autenticação, e potencialmente, da acesso ao diretório para qualquer um, como se fosse publico.*
2. Simples
    - *Necessita do nome e senha do diretório, normalmente enviado por texto simples, ou seja, não é muito seguro*
3. SASL (*simple auth. & security layer*)
    - O método mais comun por ser o mais seguro dos 3, utiliza protocolos de segurança como **TLS** para autenticar o diretório E o usuário por meio do [**Kerberos**](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc780469(v=ws.10)?redirectedfrom=MSDN); **protocolo de autenticação de rede sado para autenticar a identidade do usuário, proteger a transferência de credenciais do usuário e muito mais.** 

# 6.DNS, *Doman Name Service*
- Sistema de nomeamento que converte nome de domíno em endereço de IP, controlando qual servidor um usuário final alcançará quando digitar um nome de domínio no navegador da web.

## 6.1.DHCP, *Dynamic Host Config. Protocol*
- Protocolo usado para mapear computadores de uma rede à endereços de IP de modo automático.  

## 6.2.PXE, *Pre Exec. Enviroment* (pixie)
- Configuração de pré-inicialização que permite um computador rodar/instalar um OS por meio da rede.   

## 6.3.Dnsmasq
- Serviço que providencia *DNS, DHCP, TFPT* e *PXE* em um pacote único. Considerado util por centralizar varios serviços diferentes, leve em consumo de recursos e fácil de se usar.   

## 7. **Gerenciamento Centralizado**
- Sistema central que gerencia todas partes da infraestrutura de TI. Os serviços de diretório fornecem autenticação, autorização e contabilidade centralizadas, também conhecidas como **AAA** (*authorization, authentication, accounting*).
- Quando computadores e apps são configurados para usar serviços de diretório para serviços AAA, as decisões sobre conceder ou negar acesso a computadores, sistemas de arquivos e outros recursos são centralizadas.
- Acessos aos recursos e à rede é baseado na sua função dentro da organização, isso agiliza na hora de trocar as funções/permissões de alguém que trocou de grupo/função, isso é chamado de [***controle de acesso baseado em função*** ou **RBAC** (*Role-Based Access Control*)](https://en.wikipedia.org/wiki/Role-based_access_control)
- O gerenc. centr. tambem é usado para configurações de software e rede, no caso de necessitar alterações em massa.