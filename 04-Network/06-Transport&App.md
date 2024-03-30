# Transport and Aplication    

## Transport  

- Permite que o tráfego seja direcionado a uma aplicação de rede específica. A camada de transporte é reponsável por muitas funções, dentro dessas a **multiplexação e desmultiplexação** de tráfego, estabelecimento de conexões de longa duração e garantia de integridade dos dados por meio de checagem de erros e verificações.
    1. **Multiplexação** na camada de transporte significa que os nós da rede têm a capacidade de direcionar o tráfego para diferentes serviços de recepção. 
    2. **Desmultiplexação** é o mesmo conceito, só que na ponta receptora, ela pega o tráfego totalmente destinado ao mesmo nó e o entrega ao serviço de recepção correto.   

- A '*plexação*' é feita através de **portas**; ***Portas sendo um número de 16 bits usado para direcionar tráfego para serviços específicos executados por um computador em rede.***   

## [TCP - Transfer Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)  

- Protocolo de comunicação da camada de transporte, cuja função é verificar se dados foram enviados na sequencia correta e sem erros, complementado pelo ***protocolo da internet ou IP***. Nesse protocolo se assentam a maioria das aplicações cibernéticas devido a sua versatilidade e robustez. O protocolo em si é subdividido em varias partes e é **altamente dependente de varias confirmações** isso para garantir que todos dados estejam sendo recebidos e o enviador não esta enviando dados desnecessários.    

1. Porta Destino
    - Como o nome implica, é para onde a informação é destinada
2. Porta Origem
    - Porta com numeração alta, escolhida de seção especial de portas conhecidas como ***portas efêmeras***; seu propósito é manter diversas conexões de saída separadas. Essencialmente garante que a aplicação correta recebe a informção pedida, por exemplo, abrir uma pagina na web, e o servidor envia a pagina, e a pagina é aberta pelo browser, e não um processador de texto. 
3. Numero Sequencia
    - Numero de 32 bits usado para rastrear onde na sequencia TCP este é para estar.
4. Numero confirmação
    - Numero do proximo segmento esperado
5. *Data Offset*
    - Numero em 4 bits que comunica o comprimento do cabeçalho para que o dispositivo possa compreender onde exatamente a carga de dado começa.
6. Flag de controle
    - São 6 bandeiras:
        1. URG/ *urgent*         - Valor 1 aqui indica que o segmento é considerado urgente, e o **ponteiro urgente** tem mais informações
        2. ACK/ *acknoledgement* - Valor 1 indica que o campo de **confirmação** precisa ser examinado
        3. PSH/ *push*           - O transmissor quer que o receptor envie os dados armazenados em buffer para a aplicação receptora o quanto antes; ***buffer sendo uma técnica na qual certa quantidade de dados são armazenados em algum local antes de serem enviados a outro local***
        4. RST/ *reset*          - Indica que um dos lados da conexão não conseguiu se recuperar de uma série de segmentos perdidos ou mal-formados
        5. SYN/ *synchronize*    - Usado quando a conexão é estabelecida para que o receptor examine o campo de *n° sequencia*
        6. FIN/ *finish*         - Indica que o transmissor não tem mais dado a enviar e a conexão pode ser encerrada
7. Janela TCP
    - Especifica quantos numeros de sequencia podem ser enviados antes que uma confirmação seja uma necessária
8. *TCP Checksum*
    - Numero de 16 bits que opera como o campo de soma de verificação, ou seja, depois que todo dado é ingerido pelo destinatário a soma é calculada em todo segmento e é comparada com a soma da verificação, para garantir que nada foi perdido/alterado no meio do caminho.
9. Ponteiro urgente
    - Usado ao longo das flags de controle para demarcar segmentos mais importantes; *defasado* porém, ainda pode ser encontrado
10. Opções
    - Usado para controles mais complexos de protocolo; *igualmente defasado*.
11. ***Firula***
    - Usado para que garantir que a carga começe no local previsto.   

### Handshake   

- Metodo pela qual dois dispositivos garantem que estão falando o mesmo protocolo e vão conseguir se entender.

#### Handshake Triplo:   

- Esse handshake é muito comun e ocorre sempre que há interação entre duas máquinas para estabelecer uma conexão TCP
```
transmissor --SYN-->>  receptor 
transmissor <-SYN/ACK- receptor 
transmissor --ACK-->>  receptor 
```

#### HS Quadruplo:  

- Usado para encerrar as comunicações
```
transmissor <-FIN-- receptor 
transmissor --ACK-> receptor 
transmissor --FIN-> receptor 
transmissor <-ACK-- receptor 
```   

## Soquetes   

- Instanciação de uma ponta ou terminal em uma potencial conexão TCP; ***instanciação é o ato de implementar algo que é definido em outro lugar.***    

- **LISTEN**       - Soquete ta pronto e aguardando conexão, visto apenas no lado do transmissor/servidor
- **SYN_SENT**     - Pedido de sincronia enviado mas a conexão não foi estabelecida ainda, visto apenas no lado do cliente
- **SYN_RECEIVED** - Soquete em LISTEN recebeu o SYN mas ainda não o respondeu, visto no servidor
- **ESTABLISHED**  - Conexão estabelecida e ambos lados estão prontos a trocarem dados, visto em ambos lados.
- **FIN_WAIT**     - FIN enviaado mas não foi recebido ainda
- **CLOSE_WAIT**   - Conexão encerrada, mas o soquete ainda não foi liberado pela aplicação
- **CLOSED**       - Conexão encerrada.   
   

### Porta Efemera  

- Tambem conhecida como porta privada. As portas efêmeras não podem ser registradas junto à IANA e geralmente são usadas para estabelecer conexões de saída. Você deve lembrar que todo o tráfego do TCP usa uma porta de destino e uma porta de origem. Quando um cliente quer se comunicar com um servidor, o cliente recebe acesso a uma porta efêmera que será usada apenas por uma conexão, enquanto que o servidor escuta em um sistema estático ou porta registrada.   

#### [Para saber mais sobre portas e ver uma lista de quais foram atribuídas a quais serviços](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers)    

### FIREWALL   

- Dispositivo que bloqueia tráfego baseado em certos critérios, sendo críticos para proteção de redes, podendo operar em diversas camadas da rede podendo inspecionar tráfego da camada da aplicação e até mesmo bloquear tráfego de certos endereços de IP sendo mais comumente usados na camada do transporte. Estes geralmente possuem uma configuração que bloqueia tráfego para certas portas e permitindo à outras. ***Algumas vezes é um dispositivo de rede externo mas é melhor pensar nele como um programa que pode rodar em qualquer lugar.***

### Aplication  

- Permite que as aplicações se comuniquem entre si de modo que se compreendan. Nessa camada existem tantos protocolos que não da pra numerar todos, porque basicamente cada aplicação tem um protocolo que usa para se comunicar com o servidor; por exemplo, todos browsers usam o protocolo HTTP, ou *Hyper Text Transfer Protocol*. Basicament são muitas aplicações e muitos protocolos, mas todos precisam se comunicar de algum modo, e para tanto, decidiram por padronizar.  

## OSI - Open Systems Interconnection   

- Modelo de 7 camadas, igualmente importante, adicionando duas camadas entre a camada de transporte e aplicação, ***seção e apresentação***.
    1. Seção
        - Facilita a comunicação entre as aplicações e a camada de transporte; a parte do OS que pega o dado da camada de aplicação que foi desencapsulado de todas camadas abaixo e envia para a camada de apresentação.
    2. Apresentação
        - Responsável que o dado desencapsulado é compreendido propriamente pela aplicação em questão.