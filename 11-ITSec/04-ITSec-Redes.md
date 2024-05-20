# Segurança de Redes
# 1. **Fortalecimento** 
## 1.1 ***Da Rede***
- Ou *Network Hardening* é o processo de reduzir potenciais vulnerabilidades na rede com o intuito de torna-lá mais segura.

### 1.1.1 Serviços *Extras*
- Quaisquer serviços que não são absolutamente necessarios são uma potencial fonte de vulnerabilidade, por via de regra, ou são desativados/desabilitados ou seu acesso é considerávelmente restrito.

### 1.2.1 Negação Implícita
- Conceito de segurança de rede onde propõe que ***tudo que não for explicitamente permitido deve ser implicitamente proíbido***.
    - Não siginifica bloquear todo tráfego, mas sim permitir apenas o que for especificado.
    - Geralmente feito por meio de um *Access-control list*, **ACL** e definidas no firewall, facilitando a criação de regras seguras para o firewall.
    - ***Em vez de exigir que você bloqueie especificamente todo o tráfego indesejado, é possível apenas criar regras para o tráfego que deve ser autorizado.***

## 1.3 ***Do Hardware***
### 1.3.1 *DHCP Snooping*
- ***DHCP***, protocolo em que os dispositivos em uma rede recebem informações de configuração essenciais para comunicação pela rede, sendo esse um alvo de invasores devido à natureza do serviço que providencia.
    - *Se um invasor conseguir implantar um servidor DHCP malicioso em sua rede, ele poderia liberar leases de DHCP com a informação que quisesse, incluindo configurar um endereço de gateway ou servidor de DNS que, na verdade, é uma máquina sob seu controle, o dando acesso ao seu tráfego e abrindo a porta para futuros ataques*. Este é chamado de ***Servidor DHCP Malicioso*** (*Rogue DHCP Server Attack*)
- ***Um switch que tenha espionagem de DHCP vai monitorar o tráfego de DHCP enviado através dele.*** Também vai rastrear as atribuições de IP e mapeá-las para hosts conectados às portas do switch criando um mapa dos endereços IP atribuídos a portas físicas da chave, podendo essas informações também podem ser usadas para proteger contra *spoofing* de IP e ataques de envenenamento de ARP.
    -  *A espionagem de DHCP também faz você designar um IP confiável de servidor DHCP, se estiver operando como auxiliar de DHCP e encaminhando solicitações DHCP ao servidor, ou é possível ativar a confiança de snooping de DHCP na porta com uplink, de onde as respostas de DHCP legítimas viriam agora*.

### 1.3.2 **ARP** 
- *Address Resolution Protocol* é um protocolo que conecta um IP dinâmico (*que sempre muda*) ao endereço MAC de uma máquina física, geralmente em uma LAN (*local area network*)
    - O ARP permite um ataque *man-in-the-middle* da camada 2 devido à natureza não autenticada do ARP permitindo que um invasor forje uma resposta do ARP anunciando seu endereço MAC como o endereço físico correspondente ao endereço IP da vítima. Esse tipo de resposta do ARP é chamada de ***Resposta ARP Gratuita*** por estar respondendo uma pergunta que não foi feita. Quando isso acontece, todos os clientes no segmento de rede local colocariam essa entrada no cache e como a entrada ARP é forjada, ela desvia os quadros destinados ao endereço IP da vítima para a máquina do invasor. O invasor poderia ativar o encaminhamento de IP, o que permitiria monitorar transparentemente o tráfego destinado à vítima, podendo tambem manipular ou modificar os dados.

#### 1.3.2.1 *Dynamic ARP Inspection*
- A Inspeção dinâmica de ARP, ou DAI, é outro recurso nos switches corporativos que evita esse tipo de ataque.
- ***Esse recurso exige o uso de espionagem de DHCP para estabelecer uma ligação confiável entre endereços IP e as portas do switch***. A DAI detecta esses pacotes ARP desnecessários forjados e os descarta por meio uma tabela proveniente da espionagem de DHCP com atribuições de endereços IP autoritativos por porta também impondo limitação de taxa de pacotes ARP por porta para impedir a verificação de ARP.

##### 1.3.2.1.1 ***IP Spoofing***
- Um invasor altera o cabeçalho do pacote de dados para parecer que vem de fonte confiável. Para impedir ataques de spoofing de IP, o *IP Source Guard*, ou **IPSG**, ***pode ser ativado nos switches corporativos junto com a espionagem de DHCP***.
    - *Ele funciona usando a tabela de espionagem de DHCP para criar ACLs de maneira dinâmica para cada porta do switch. Isso descarta os pacotes que não correspondem ao endereço IP da porta com base em uma tabela de espionagem de DHCP*.

##### 1.3.2.1.2 **802.1X**
- Ele é o padrão da IEEE para encapsular tráfego do **EAP** (**Protocolo de autenticação extensível**), pelas redes 802, também é chamado de *EAP over LAN*, ou EAPOL.
    - *Ele foi originalmente criado para Ethernet, mas foi acrescentado o suporte para outros tipos de rede, como redes Wi-Fi e de fibra*.

##### 1.3.2.1.3 *EAP-TLS*
- Um dos métodos EAP mais comuns e seguros de EAP, ***é um tipo de autenticação compatível com EAP que usa o TLS para fornecer autenticação mútua do cliente e do servidor de autenticação***. Essa é considerada uma das configurações mais seguras para a segurança sem fio. 
- Quando um cliente quer se autenticar em uma rede usando 802.1X, há três partes envolvidas, o dispositivo cliente é o que chamamos de ***suplicante***.
    - O suplicante se comunica com o ***autenticador***, que age como intermediário da rede que exige que os cliente se autentiquem na rede antes que tenham permissão de se comunicar com ela
    - O **autenticador** encaminha a solicitação de autenticação ao ***servidor de autenticação*** e aí a verificação de credenciais realmente ocorre.
- *A segurança do EAP-TLS deriva da segurança inerente que o protocolo TLS e o PKI fornecem, que também significa que as armadilhas são as mesmas no que se refere a gerenciar adequadamente os elementos de PKI.* 

# 2. Monitoramente de Tráfego
- É importante por vários motivos, como por exemplo, **permite estabelecer um valor de referência para a aparência típica do tráfego da rede** e isso ajuda a discernir o tráfego comun do incomun, ajudando na detecção de possíveis ataques. 
    - *Geralemente é feito com o monitoramento de rede e a análise de registros.*

## 2.1 ***Análise de Registros*** 
- É a prática de coletar registros de diferentes redes e, algumas vezes, de dispositivos clientes em sua rede, para realizar uma análise automatizada deles. Isso destacará comportamento atípico; possíveis invasões, sinais de infecções por malware etc.
    - Se analisa itens como registros de firewall, registros do servidor de autenticação e registros de aplicativos, procurarando mensagens de interesse em registros específicos, como os do firewall. 
- Os sistemas de análise de registros são configurados usando regras definidas pelo usuário para corresponder a entradas de registro *interessantes*/atípicas. 
    - Elas podem então ser *realçadas* com um sistema de alerta para permitir uma melhor investigação, parte desse processo de alerta também envolveria **categorizar o alerta com base na regra correspondente. Também seria necessário atribuir uma prioridade para facilitar a investigação** e permitir uma pesquisa/filtragem melhor.
        - Os alertas podem assumir a forma de um envio de **e-mail** ou de **SMS** com informações e um link para o evento que foi detectado. ***Seria possível até acordar alguém no meio da noite se o evento fosse grave o suficiente***.
    - A normalização dos dados de registros é uma etapa importante porque registros de diferentes dispositivos e sistemas podem não ter uma formatação comum, podendo ser necessário converter registros em um formato comum para facilitar a análise   

### 2.1.1 Análise de Correlações
- **Processo de coletar dados de registros de diferentes sistemas à eventos correspondentes em outros sistemas**.
    - *Se nota-se uma conexão suspeita vindo de um endereço de origem suspeito e o firewall registrar em nosso servidor de autenticação, pode-se correlacionar essa conexão registrada com os dados do registro do servidor de autenticação, mostrando todas as tentativas de autenticação feitas pelo cliente suspeito.* 
- Essa análise tambem é crucial na etapa de investigação e recriação do evento na hora da detecção do comprometimento  
    - Chamada de **Análise Pós-Falha** (*Post-Fail*) pois é feita, como o nome indica, *após* a catástrofe.
        - O registro detalhado e a análise de registros permitiria a reconstrução minuciosa dos eventos que levaram ao comprometimento, permitindo uma melhor compreensão do que não se fazer na próxima vez, tambem pode ajudar na compreensão do dano causado, entre arquivos deletados e informação roubada, com mais especificidade.

## 2.2 *Splunk*
- Sistema de agregação e pesquisa de registros muito flexível e extensível. O Splunk pode coletar dados de registros de vários sistemas e em uma grande variedade de formatos podendo tambem ser configurado para gerar alertas e permite uma poderosa visualização da atividade com base nos dados de registros. 

## 2.3 *Flood Guards*
- Protegem contra ataques DoS/DDoS identificando tipos de ataque flood, como floods de SYN ou UDP e disparando alertas assim que um limite configurável de tráfego é atingido.
    - Há outro limite chamado ***limite de ativação*** que quando atingido, dispara uma ação pré-configurada, normalmente o bloqueio de tráfego da fonte do ataque identificado, por um período de tempo. 

### 2.3.1 *Fail2Ban*
- Um *flood Guard* de código aberto que detecta sinais de um ataque em um sistema e bloqueia outras tentativas do suposto endereço do ataque. 

# *Firewalls*
- Windows
    - https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc754274(v=ws.11)?redirectedfrom=MSDN  

- Mac
    - https://support.apple.com/pt-br/guide/mac-help/mh34041/mac

- Ubuntu
    - https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands