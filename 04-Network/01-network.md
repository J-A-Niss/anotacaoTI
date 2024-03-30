# Network  (rede)    

- Como o proprio nome diz, é uma rede de computadores interconectada, podendo ser tanto dentro de uma empresa como em escala global.    

- **A internet** é a conexão física entre os computadores; uma enorme rede de satelites, cabos subterraneros e redes celulares, e **a Web** é a informação que ta na internet e se usa da *Web* para acessar a internet através de um link, como por exemplo [www.google.com](https://google.com). Ainda sim existem diversos meios de acessar a web como email, chat e compartilhamento de arquivo e na area de TI projetar esses tipos de conexões é chamado de **Networking**.    

- Não se conecta diretamente à internet, se conecta a servidores que se conectam diretamente a internet, esses servidores armazenam os sites usados e os sites exibem os conteudos do site. O dispositivo usado para se conectar é chamado de cliente. O cliente se conecta à rede por meio de *provedor de internet* (ISP) e o provedor por sua parte fornece o acesso à toda infraestrutura necessária para que o cliente acesse a internet (redes/cabeamento etc). O provedor tambem se conecta a outras redes e a outros provedores e essas redes são as que se conectam a internet.   

```
cliente <--> provedor <--> rede <--> servidor <--> website    

Mas como boa parte do processo não é mostrado ao usuário, parece que:    

cliente <---> website 
```   

- Computadores em uma rede possuem um identificador chamado de *endereço de IP*. Quando se acessa um website se vai diretamente ao endereço de IP do site. Dispositivos que podem se conectar a internet tambem possuem um outro identificador unico chamado endereço MAC (***não relacionado ao macOS***), este é permanente e codificado no dispositivo em si. **Quando se envia ou recebe dado por uma rede, precisa de ambos**. Dados são enviados por meio de pacotes (*packets*).    

##### Pacotes   

- Bits de informação(1s e 0s), divididos para maior agilidade do processamento, que são enviados e recebidos pela internet. Basicamente os pacotes são enviados desse modo fragmentado até que encontrem seu destino final, por exemplo, pesquisar uma imagen no google, então fica de modo que o pacote procura o endereço do google, até que o encontre e o google envia um outro pacote que te mostra as imagens procuradas.  

## Hardware de rede   

1. Cabo Ethernet
    - Cabo que permite uma conexão física à rede através de uma porta no computador   

2. WiFi
    - Conexão sem fio, por meio de rádio e antena, mais comun em smartphones e notebooks.   

3. Fibra Ótica
    - Método mais caro, os cabos são feitos com uma fibra de vidro que transmite dado através de luz ao invés de eletricidade através de um fio de cobre, permitindo assim um acesso ainda mais rápido à rede.    

- Esses métodos todos se conectam à um **roteador**   

### Roteador   

- Dispositivo responsável por conectar varios dispositivos entre si e rotear o tráfego à rede. Se um computador quer enviar um arquivo a outro na rede, fará por meio do roteador, o computador enviará o pacote de dado ao roteador que usará um **protocolo de rede** para ajudar a determinar pra onde que o dito cujo pacote vai. Esse protocolo consta essencialmente de regras que o ajudam a descobrir onde dados devem ser enviados.    

#### Protocolos de Rede    

- Regras que garantem que os pacotes sejam roteados de forma eficiente, não sejam corrompidos, sejam seguros, sigam para a máquina certa e sejam nomeados corretamente. Existem dois protocolos mais dominantes, o ***Protoc. de controle de transmissão*** e o ***protoc. da internet***   

1. IP - Internet Protocol
    - Responsável por entregar os pacotes enviados aos computadores certos   

2. TCP - Transfer Control Protocol
    - cuida do envio seguro e consistente das informações de uma rede a outra    


## WEB   

- Modo pela qual se acessa a internet sendo que todos sites podem ser acessados pela web e sites são ***documentos de texto que formatamos com HTML, ou linguagem de marcação de hipertexto***   

- Pode se acessar pelo enderço, ou [www.google.com](https://google.com) on o '*www*' significa world-wide web e o *google* é o nome do dominio registrado no ICANN, a *Corporação da Internet para Atribuição de Nomes e Números*. Nomes são usados por serem muito mais reconhecíveis e faceis de serem lembrado, e se o nome é registrado no ICANN, ele não pode ser mais usado a não ser que seja disponibilizado novamente. Já o *.com* é a terminação, e existem varias, como *.net* ou *.org* e serve pra indicar o tipo de site, por exemplo *.edu* indica sites de instituições de ensino.   

- Pode-se acessar um site tambem pelo endereço de IP em si, como por exemplo *172.217.6.46* direcionando para a página inicial do Google através de um protocolo essencial da Web, o *Sistema de Nomes de Domínio*, ou DNS. O DNS permite mapear palavras para endereços de IP, de modo que não importa se usa o nome ou o IP para acessar algum website. Basicamente seu computador faz uma busca de DNS para achar o endereço de IP do nome do site digitado.   

- O protocolo da Internet versão 4, ou IPv4, é um endereço composto de 32 bits divididos em quatro grupos. Apesar de parecer que são muitos endereços IPv4 possíveis, existem menos de 4,3 bilhões de endereços IPv4 mas existem mais de 4.3 bilhões de sites no mundo e alguns endereção são reservados, permitindo ainda menos endereços. Graças ao IPv6 ou endereços IP versão 6. Os endereços IPv6 têm 128 bits, quatro vezes mais que o IPv4 e devido a isso, muito mais dispositivos podem ter endereços IP. A adoção dos endereços IPv6 tem sido gradual e com o tempo, você verá cada vez mais endereços IPv6 por aí. Com IPv6 é possível ter 2^128, ou seja, **muitos** endereços.    

- Outra solução que conseguimos usar é a NAT, Network Address Translation, ou  tradução de endereços de rede. Com ela, as organizações podem usar um endereço IP público e vários privados dentro da rede.    

#### Internet das Coisas (internet of things/iot)    

- Internet das coisas é um conceito que permite que mais dispositivos sejam conectados à Internet.    

## Privacidade e Segurança    

### Networking   

- Processo de design do network em si.   

#### Network Stack   

- conjunto de hardware ou software que fornece a infraestrutura de um computador