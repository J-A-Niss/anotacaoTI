# Serviço NAT - Network Address Translation   

- Tradução de endereço de rede é considerado uma técnica ao invés de um padrão definido, e essencialmente pega um IP e "traduz"(e por "traduz" entenda, **muda**) para outro. Isso é feito por razões de segurança como tambem preservação do finito espaço de IPV4. Isso se da a partir de um gateway, geralmente um roteador ou um firewall, que reescreve o IP fonte de um datagrama IP enviado, mantendo o IP original para reescreve-lo na resposta. ***Isso basicamente faz o sinal do IP aparentar sair do ROTEADOR que enviou o sinal, e não do computador que o enviou, "escondendo" o IP do computador enviador do computador recebedor, isso é chamado de Mascaramento de IP.***   

```
1. PC Enviador manda o datagrama ao roteador, que mascara o IP do PC com seu proprio e 'guarda' o IP original
2. Roteador envia o datagrama com o IP mascarado ao receptor
3. Receptor responde o datagrama ao roteador, não sabendo que na verdade é do PC enviador
4. Roteador pega a resposta, desmascara o IP e a transmite ao enviador

- Nisso o recebedor não sabe que recebeu do enviador, achando que recebeu do roteador.
```  

- *Um-pra-vários*
    - Ocorre no caso que varios computadores em LAN usando um gateway que mascara seus sinais, dando a impressão que a LAN fosse na verdade um sinal só. Isso pode dar problema sendo que o roteador receberá varias respostas enderaçadas ao mesmo IP e precisará de um jeito para enviar as respostas corretas ao enviador correto e isso pode ser feito por meio de **preservação de porta**
        - ***Preservação de porta***: Técnica pela qual o cliente escolhe uma porta fonte para que seja usada pelo roteador; ja que as conexões de saida escolhem uma porta aleatoriamente de 49.152 à 65.535, o roteador marca qual foi a porta escolhida e a usa de ponto de referencia. Ou seja **o roteador usa a porta como o endereço de origem para saber qual mensagem vai para qual computador ja que o IP foi mascarado**
        - ***Redirecionamento de porta***: Técnica na qual portas específicas são configuradas para nós especificos   

#### [Exaustão do IPv4](https://en.wikipedia.org/wiki/IPv4_address_exhaustion)

- Basicamente não tem mais IPv4 disponível, e para circumvir esse problema, usa-se NAT para que dispositivos individuais não necessitem necessariamente de um IP para se conectar a internet.   

## [VPN - Virtual Private Network](https://pt.wikipedia.org/wiki/Rede_privada_virtual)   

- Permite a extensão de uma rede local para um host que pode não operar na mesma rede local. É um protocolo de tunelamento, significa que elas viabilizam acesso a algo que não está disponível localmente. A maioria das VPNs funciona usando a seção payload da camada de transporte para transportar um payload criptografado que contém um segundo conjunto inteiro de pacotes: as camadas de rede, de transporte e de aplicação de um pacote destinado a atravessar a rede remota. Esse payload é transportado ao endpoint da VPN, na qual as outras camadas são descartadas, e o payload original é descriptografado deixando o servidor com as 3 camadas superiores do novo pacote.  

- Requerem um procedimento de autenticação rigoroso para garantir que sejam acessados por computadores autorizados, sendo as VPN responsáveis por disseminar a **autenticação em dois fatores**; na qual mais que uma senha e login são necessários para autenticar um usuário.   

- O mais importante é que as VPNs são uma tecnologia que usa túneis criptografados para permitir que um computador ou uma rede remota atue como se estivesse conectado a uma rede que não está fisicamente ligada a eles.   

#### VPN Ponto a ponto   

- Estabelece um tunel vpn entre dois locais, funciona parecido com vpn tradicional que usuários podem aparentar estarem conectados na mesma rede, mas difere no ponto que o tunelamento é tratado por dispositivos nos dois locais de modo que os proprios usuários não precisam estabalecer suas proprias conexões.   

## [Proxy](https://pt.wikipedia.org/wiki/Proxy)  

- Um servidor que age como um intermediário para requisições de clientes; solicitando recursos de outros servidores. Um cliente conecta-se ao servidor proxy, solicitando algum serviço, como um arquivo, conexão, página web ou outros recursos disponíveis de um servidor diferente, e o proxy avalia a solicitação como um meio de simplificar e controlar sua complexidade. 