# Serviços de Rede  

## DNS - Domain Name System ou Sistema de Dominio de Nome   

- Serviço global e altamente distribuido que transforma sequencia de letra em enderço de IP. É muito mais facil pro usuário lembrar de um nome, como Google ou Youtube do que um endereço de IP; isso tambem pelo fato que o endereço de IP pode mudar e o nome mantem o mesmo, facilitando encontra-lo. O nome de domínio é o termo usado para algo que pode ser resolvido pelo DNS. Pela sua estrutura global, DNS ajuda o cliente a se conectar mais facilmente com, por exemplo, um data center mais proximo o que resulta em uma conexão melhor e mais rapida.

- Primeiramente, um servidor DNS deve ser especificamente configurado em um nó na rede e é a quarta coisa que precisa ser configuarada para que o host funcione de forma adequada, sendo essas:
    1. IP
    2. Mascara subnet
    3. gateway p/ host
    4. servidor DNS   

- Um computador/rede pode até funcionar sem um serv. DNS, mas isso dificulta imensamente como um usuário iteragirá; existem 5 tipos primários de servidores DNS, sendo que qualquer um deles pode preencher muitas dessas funções ao mesmo tempo:
    1. Serv. de nome de Cache
        - Geralmente fornecido pelo provedor; seu propósito é armazenar pesquisas de nome de domínio por um det. período de tempo
    2. Serv. de nome Recursivo
        - *Idem ao Cache*, porém esses executam uma solicitação de resolução de DNS completa
    3. Serv. de nome Raiz
    4. Serv. de nome TLD
    5. Serv. de nome autoritativo    

### Registro de Nomes   

- Os nomes precisam se globalmente unicos, e para tanto, existem empresas dedicadas a manter um registro de nomes junto à ICANN, responsáveis por atribuir nomes de domínio público para organizações ou individuos. Esse registro é finito, sendo necessário renovar o registro caso contrário o nome se tornará disponpivel ao publico.

#### Servidor DNS publico  

- Servidores de nomes que podem ser usados por qualquer pessoa, gratuitamente, usar esse tipo de servidor é uma boa técnica para solucionar quaisquer problemas de resolução de nomes. Desses todos, o maior é a Level 3 e seu negócio essencialmente revolve em vender conectividade à rede deles para outros provedores que lidam direto com o consumidor. A maioria desses servidores estão disponíveis globalmente por meio do Anycast. ***Sempre se certifique que o servidor de nomes é confiável e tente usar os servidores fornecidos pelos provedores***  

### TTL - Time to Live   

- Valor em segundos, que pode ser configurado pelo proprietário de um nome de domínio, que indica o tempo que o servidor de nomes está autorizado a manter no cache o registro do nome antes que tenha que descarta-lo e fazer uma nova busca.  

### Resolução Recursiva Completa   

1. Contatar serv. de nome Raiz; existem 13 desses que estão distribuidos ao redor do globo por meio de ***anycast, sendo essa uma técnica usada para rotear tráfego para diferentes destinos, dependendo de diferentes condições***
2. O serv. raiz responde a pesquisa DNS com o serv. de nomes **TLD** que deve ser consultado
    - ***TLD - Top Level Domain, representando o topo do sistema hierárquico de resolução de nomes DNS, sendo essa a ultima parte de qualquer nome de domínio, basicamente tudo que vem depois do ponto.***
3. Para cada TLD tem um serv. propagado via anycast
4. O serv. TLD responde com um redirecionamento, informando ao computador qual serv. de nome autoritativo ele deve entrar em contato.
5. Finalmente a pesquisa DNS é redirecionada ao servidor autoritativo com o IP real do servidor em questão   

- Essa hierarquia rígida é crucial para a estabilidade da internet, sendo que fazer toda resolução DNS passe por um processo estrito, regulado e rígido dificulta ação de agentes mal-intencionados   

## UDP - User Datagram Protocol   

- Protocolo que não requer conexão, portanto, não possui o conceito de um ACK, a confirmação de recebimento. Com o UDP, basta definir uma porta e enviar o pacote. Neste caso, muito menos tráfego precisa ser dirigido no total sendo que uma unica conexão DNS pode se encaixar perfeitamente dentro de um unico datagrama UDP, ou seja, muito menos pacotes de datagrama serão enviados. ***Essencialmente, enquanto o TCP é mais robusto, o UDP é mais simples e celere.***  

## Reg. De Recursos  

- Basicamente permitem a ocorrência de diferentes tipos de resolução DNS, sendo que muitos deles servem para fins específicos.  

1. Registro A
    - Usado para apontar um certo nome de dominio em um determinado endereço IPv4, essencialmente, um unico desse é configurado para um unico IP, porem, um unico endereço pode ter varios *registros A* viabilizando uma técnica chamada ***DNS Round-Robbing, para balançear tráfego entre vários IPs.***
        - DNS Round-Robbing - *Envolve repetir uma lista de elementos, um a um de modo ordenado com objetivo de equilibrar cada entrada da lista; essencialmente é uma lista cíclica de endereços de IP que podem ser usados na conexão*
2. Quad A
    - Similar ao *registro A*, porem, para um endereço IPv6
3. CNAME
    - Usado para redirecionar tráfego de um domínio para outro, por exemplo, de *microsoft.com* para *www.microsoft.com*
4. MX - Mail eXchange
    - Usado para mandar email ao servidor correto; muitas empresas rodam servidores de web e de email diferentes, então o registro MX garante que o email irá ao servidor de email, e o tráfego normal ao servidor web.
5. SRV - Service Record
    - Usado para definir localização de vários serviços específicos; identico ao MX, mas MX sendo específico para email, este podendo ser configurado para qualquer outra coisa.
6. TXT - Text
    - Originalmente concebido para ser usado para associar um texto descritivo à um nome de domínio para consumo humano; hoje em dia é usado para enviar dado adicional para que outros computadores os processem.  

### TLD - Top Level Domain   

- A parte final do nome de domínio, *.com ou .net* , por exemplo. Definida pelo ICANN, ou *Corporação da internet para nomes e números atribuídos*; responsável pelo controle pelos espaços IP e o sistema de DNS global.  

## Domínio  

- A segunda parte do Nome do Domínio, ou o nome em si, por exemplo *google* no www.*google*.com e é usado para demarcar onde o controle é transferido de um servidor de nomes TLD para um servidor de nomes autoritativo e geralmente fora do controle da ICANN. Pode ser escolhido e registrado por qualquer pessoa física ou pessoa jurídica mas todos devem acabar com TLEs predefinidos.  

#### Subdomínio  

- O prefixo do domínio, ou o *www*, as vezes é chamado de nome de host se for atribuido a um unico host.  

### FQDN - *Fully Qualified Domain Name*  

- Todas as partes do nome de domínio, do *www* ao *.com* e tudo que estiver no meio. DNS suporta até 127 níveis de domínio total, ou seja, um *.com* para um unico nome qualificado sendo que cada seção individual só pode conter 63 cáracteres, o total não pode passar de 255 carácteres.  

### Zona DNS  

- Tem finalidade permitir um controle mais fácil em varios níveis de um domínio. Basicamente usado para organizar melhor os endereços. As zonas são configuradas por meio de arquivos que atribuem todos registros de recursos para uma determinada zona específica, esse arquivo devendo contar um ***SoA ou Start of Authority, registro que atribui a zona e o nome do servidor que é autoritativo para ela***.   

## DHCP - Dynamic Host Configuration Protocol   

- Protocolo na camada de aplicação que automatiza o processo de configuração do host em uma rede. Essencialmente permite que uma máquina consulte um servidor DHCP quando se conecta à uma rede e receba toda configuração de uma só vez. Apesar de ser da camada de aplicação, sua principal função é ajudar a configurar a propria camada de rede.   

- **Alocação Dinâmica**
    - IPs são disponibilizados à dispositivos clientes quando eles requisitam um, ou seja, o IP de uma máquina pode ser diferente sempre que se conecta à rede.  

- **Alocaç. Automatica**
    - Funciona similar à alocação dinâmica, exceto que o servidor DHCP registra quais endereços foram enviados a quais máquinas e tenta re-enviar o mesmo endereço para a mesma máquina caso possível   
    
- **Alocaç. Fixa**
    - Exige uma lista de endereço MAC e seus endereços IP correspondentes   

- **NTP - Network Time Protocol**
    - Usado para manter os computadores em rede sincronizados   

#### DHCP Discovery   

- Processo pela qual um cliente configurado para usar DHCP tenta adquirir informação da rede; esse processo possui 4 passos:
    1. Cliente envia uma mensagem de descoberta DHCP para a rede, já que a maquina não tem um IP e não conheçe o IP do servidor DHCP, ela cria uma mensagen de broadcast especial, o **DHCP escuta na porta 67** e a **mensagem de descoberta é enviada pela porta UDP 68**
    2. Essa é encapsulada em um datagrama UDP com origem na porta 68 e destino na 67, depois isso é encapsulado em um datagrama IP com destino ao endereço 255.255.255.255 e origem 0.0.0.0. Essa mensagem é enviada a todo nó da rede local e caso haja um serv. DHCP presente, o mesmo recebe a mensagem
    3. Então o serv. examina sua configuração para ver se há um IP disponível ao cliente, isso dependendo do tipo de **alocação** que foi configurado, essa resposta é enviada como uma DHCPOFFER para a porta 68, da porta 67, com IP destino de 255.255.255.255 e origem de seu proprio (do servidor) IP. Essa mensagem tambem alcança toda maquina da rede. A mensagem é marcada com o endereço MAC da máquina que enviou a mensagem
    4. A mensagen é então respondida com um DHCPREQUEST, que basicamente diz "sim, quero o IP que voce ta oferencendo", e como um IP ainda não foi enviado, é enviada do IP 0.0.0.0.68 ao 255.255.255.255.67 e então o serv. responde com um DHCPack ou uma mensagem de confirmação, essa mensagem enviada a um IP 255.255.255.255 do IP original do servidor, novamente, reconhecendo que é a maquina certo pelo endereço MAC