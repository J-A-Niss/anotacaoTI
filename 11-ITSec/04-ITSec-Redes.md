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
- Um dos métodos EAP mais comuns e seguros de EAP, ***é um tipo de autenticação compatível com EAP que usa o TLS para fornecer autenticação mútua do cliente e do servidor de autenticação por meio de certificados***. Essa é considerada uma das configurações mais seguras para a segurança sem fio. 
- Quando um cliente quer se autenticar em uma rede usando 802.1X, há três partes envolvidas, o dispositivo cliente é o que chamamos de ***suplicante***.
    - O suplicante se comunica com o ***autenticador***, que age como intermediário da rede que exige que os cliente se autentiquem na rede antes que tenham permissão de se comunicar com ela
    - O **autenticador** encaminha a solicitação de autenticação ao ***servidor de autenticação*** e aí a verificação de credenciais realmente ocorre.
- *A segurança do EAP-TLS deriva da segurança inerente que o protocolo TLS e o PKI fornecem, que também significa que as armadilhas são as mesmas no que se refere a gerenciar adequadamente os elementos de PKI.*    

## 1.4 ***Do Software***
### 1.4.1 ***Firewall***
- Ferramente essencial para proteção ***que regula o fluxo de tráfego em uma rede***. Podem tambem ser implementados como um *dispositivo dedicado à proteção de toda a rede, ou  como software, dedicado apenas a um host*.

#### 1.4.1.1 *Baseado em Host*
- Um firewall baseado em host fornece proteção para dispositivos móveis, como um laptop que poderia ser usado em um ambiente não confiável como um hotspot Wi-Fi em um aeroporto.
- **Também são úteis para proteger outros hosts de serem comprometidos pelo dispositivo corrompido na rede interna**. Isso é algo que um firewall baseado em rede poderia não conseguir.
- ***Todos os principais sistemas operacionais têm firewalls integrados.***

#### 1.4.1.2 *Baseado na Rede*
- Gerenciado por dispositivos, como por exemplo roteadores, que possuem um firewall dedicado à rede.   

#### 1.4.1.3 Proxies
- **Um servidor que age como intermediário** entre o cliente e um servidor providenciando recursos. **Ao invés de ser conectar diretamente ào servidor** para completar a requisição, como uma página web por exemplo, **o cliente direciona o pedido ao proxy que então o avalia e realiza todas as tarefas associadas ao seu envio**.
    - *Isso auxilia na simplificação do pedido e para providenciar mais segurança, privacidade e equilibrio de carga.*
- Haproxy
    - *http://www.haproxy.org/#docs,%20http://cbonte.github.io/haproxy-dconv/1.8/intro.html#3.3.1*
- nginx
    - *http://nginx.org/en/*
- Apche
    - *https://httpd.apache.org/docs/current/en/*

# 2. **Monitoramente de Tráfego**
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

# 3. ***Proteção Wireless***
## 3.1 WEP
- *Wired Equivalent Privacy*, sua finalidade era fornecer privacidade equivalente à de uma rede cabeada significando que as informações transmitidas pela rede devem ser protegidas contra **interceptação**. Diferente das redes cabeadas, os pacotes podiam ser interceptados por qualquer pessoa fisicamente próxima do ponto de acesso ou da estação cliente e sem alguma forma de criptografia para proteger os pacotes, o tráfego sem fio poderia ser lido por qualquer pessoa nas proximidades.
- ***O WEP se mostrou gravemente ineficaz em fornecer confidencialidade ou segurança para redes sem fio e foi descartado em 2004 em favor de sistemas mais seguros.***
    -  O WEP usa a cifra de fluxo simétrico RC4, usado como uma chave compartilhada de 40 ou 104 bits em que a chave para pacotes individuais foi derivada. A chave de criptografia real de cada pacote foi calculada considerando a chave compartilhada fornecida pelo usuário combinada com um vetor de inicialização de 24 bits, é um bit de dados aleatório para evitar a reutilização da mesma chave de criptografia entre pacotes. Como esses bits de dados são concatenados, um esquema de chave compartilhada de 40 bits usa uma chave de 64 bits para criptografia e o de 104 bits usa uma chave de 128 bits. **Originalmente, a criptografia WEP estava limitada a apenas 64 bits devido às restrições de exportação dos EUA aplicadas às tecnologias de criptografia.**
        - **Essas leis mudaram e a criptografia de 128 bits pode ser usada** a chave compartilhada foi inserida como 10 caracteres hexadecimais para WEP de 40 bits ou 26 caracteres hexadecimais para WEP de 104 bits. **Isso reduziu o keyspace disponível para somente caracteres ASCII válidos em vez de todos os possíveis valores hexadecimais.**
- A autenticação de chave compartilhada funcionava exigindo que os clientes se autenticassem com um processo de respostas de desafio de 4 etapas e o WEP enviava essas etapas **transmitindo o texto simples e o texto cifrado de uma maneira que expõe as duas mensagens abrindo a possibilidade do invasor recuperar a chave de criptografia.** *Um conceito geral em segurança e criptografia é nunca enviar o texto simples e o texto cifrado juntos*.
- ***MAS o verdadeiro ponto fraco do WEP não estava relacionado aos esquemas de autenticação***. 
    - O uso da cifra de fluxo RC4 e como os IVs eram usados para gerar chaves de criptografia Mas a chave de criptografia no WEP é composta **apenas da chave compartilhada, que não muda com muita frequência**, tendo 24 bits de dados aleatórios incluindo o IV acrescentado ao final dela, **resultando em um pool de apenas 24 bits**, em que as chaves de criptografia exclusivas seriam escolhidas entre as não utilizadas. ***Como o IV é composto de 24 bits de dados, o número total de possíveis valores não é muito grande de acordo com os padrões de computação modernos***.
    - São apenas cerca de 17 milhões de IVs exclusivos, o que significa que **após uns 5 mil pacotes um IV será reutilizado, e quando um IV é reutilizado, a chave de criptografia também é reutilizada**. Além do fato que o IV era transmitido por texto simples, significando que um invasor só precisaria monitorar os IVs e procurar pelos repetidos, **permitindo que o invasor reconstrua esse fluxo de chaves que usa pacotes criptografados com os IVs fracos**.

## 3.2 **WPA**
- *Wi-Fi Protected Access* originalmente designado como o substituo de curto prazo do WEP, compatível com hardware ainda o utilizando por meio de uma simples atualização de *firmware*.
    - **Firmware** é um tipo de micro-código integrado à hardware para auxiliar em seu desempenho.
- Isso permitiu que não fosse necessário a re-aquisição de novo hardware de wi-fi 

### 3.2.1 TKIP
- *Temporal Key Integrity Protoc.* Foi desenvolvido para lidar com as limitações de segurança do WEP implementando 3 novos recursos que o tornavam mais seguro que o WEP:
    1. *Novo método de derivação de chave mais seguro, para incorporar o IV com mais segurança à chave de criptografia por pacote.* 
    2. *Contador sequencial foi implementado para evitar ataques de repetição, rejeitando pacotes fora de ordem.*
    3. *Um MessageIntegrityCheck de 64 bits, ou verificação de integridade de mensagem, foi introduzida para evitar falsificação, adulteração ou corrupção de pacotes.*
- O TKIP ainda usa a cifra RC4 como algoritmo de criptografia, **mas solucionou os pontos fracos na geração de chaves da Web usando uma função de mistura de chaves para gerar chaves de criptografia exclusivas por pacote**. Ele também utiliza chaves com 256 bits.
- **Os métodos de PIN são realmente interessantes *e também onde uma falha crítica foi introduzida***.
    - O mecanismo de autenticação por PIN é compatível com dois modos. Em um deles, o cliente gera um PIN, que por sua vez é inserido no AP. No outro modo, o AP tem um PIN normalmente codificado no firmware, que é inserido no cliente. **O segundo modo é que é vulnerável a um ataque de força bruta on-line**.
        - O método de autenticação por PIN usa PINs com 8 dígitos, mas o último dígito é um checksum calculado a partir dos primeiros 7 dígitos. Assim o número total de PINs possíveis é 10^7, ou cerca de 10 milhões de possibilidades. **Mas o PIN é autenticado pelo AP em *metades*. Isso significa que o cliente enviará os primeiros 4 dígitos do AP, esperará por uma resposta positiva ou negativa, e enviará a segunda metade do PIN se a primeira estiver correta**.***Na verdade, estamos reduzindo ainda mais o total de PINs válidos possíveis e facilitando ainda mais descobrir qual é o PIN correto***. 
            - *A primeira metade do PIN, tendo 4 dígitos, tem cerca de 10 mil possibilidades. A segunda metade, com apenas 3 dígitos devido ao valor do checksum, tem no máximo 1.000 possibilidades.* **Isso significa que o PIN correto pode ser descoberto em, no máximo, 11 mil tentativas, parece muito mas não é**. *Sem nenhuma limitação de taxa, um invasor pode recuperar o PIN e a chave pré-compartilhada em menos de 4 horas*. 
- A *Wi-Fi Alliance* reformula as exigências da especificação WPS, introduzindo um período de bloqueio de 1 minuto após 3 tentativas de inserir o PIN incorreto, aumentando o tempo máximo para descobrir o PIN de 4 horas para menos de 3 dias. **Para um invasor paciente e determinado, isso não chega a ser um obstáculo**, mas se a rede for comprometida com o uso desse ataque porque o **PIN é um elemento imutável que faz parte da configuração do AP**, o invasor pode apenas reutilizar o PIN já recuperado para obter a nova senha.  

## 3.3 **WPA2**
- O WPA2 melhora ainda mais a segurança do WPA implementando o CCMP, *Counter Mode CBC-MAC Protocol* baseado na cifra AES, **afastando-se definitivamente da insegura cifra RC4**. *Counter Mode CBC MAC* é um modo específico de operação para cifras de bloco permitindo criptografia autenticada, ou seja, ***os dados são mantidos confidenciais usando um mecanismo de autenticação e criptografia***.
    - O resumo do CBC MAC é calculado primeiro, depois o código de autenticação resultante é criptografado com a mensagem usando uma cifra de bloco. Estamos usando o AES neste caso operando no *Counter Mode*, transformando uma cifra de bloco em cifra de fluxo, por meio de um valor aleatório e um contador incremental, realizando a authenticação com um handshake de 4 vias:
        1. O AP que envia o valor de uso único ao cliente.
        2. O cliente envia seu valor de uso único ao AP.
        3. O AP envia a GTK
        4. O cliente responde com um Ack confirmando a negociação bem-sucedida.

# 4. Fortalecimento de Redes na Prática
- Idealmente se usaria o 802.1X por seu nível elevado de segurança *mas sua complexidade e sobrecarga de gerenciamente, devido à necessiadade de um servidor RADIUS e um backend adicional de autenticação*, o torna impraticável em muitos casos. **Se o EAP-TLS for implementado também**, todos os componentes da infraestrutura de chave pública também serão necessários, aumentando ainda mais a complexidade e a sobrecarga de gerenciamento.
- **Se o 802.1X for muito complicado para uma empresa, a próxima melhor alternativa seria o WPA2 com o modo AES/CCMP.** 
    - Mas para proteção contra ataques de força bruta ou de tabela arco-íris, deve-se tomar medidas para elevar o nível computacional. **Uma senha longa e complexa que não seria encontrada em um dicionário** aumentaria o tempo e os recursos de que o invasor precisaria para quebrar a senha longa. **Alterar o SSID para algo incomum e exclusivo** também tornaria menos provável o ataque de tabelas arco-íris. Isso exigiria que um invasor fizesse os cálculos por conta própria, aumentando o tempo e os recursos necessários para realizar um ataque.
