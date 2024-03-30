## Endereço MAC (Media Access Control Access)    

- Identificador global conectado à uma interface de rede individual, sendo um numero de 48 BITs normalmente representado por seis agrupamentos de numeros **hexadecimais**. Outro modo de identificar um endereço MAC é por meio de um **Octeto**. Basicamente o número total de endereços MAC possíveis é 2 elevado à potência 48, ou ***281.474.976.710.656 possibilidades unicas***     

- O endereço MAC é separado em duas partes, os tres primeiros Octetos são chamados de *OUI*, ou ***Organizationally Unique Identifier***; estes sendo atribuidos aos fabricantes de hardware pelo IEEE, Instituto de Engenheiros de Energia e Eletronica. Isto é util por trazer a possibilidade de identificar o fabricante de uma interface de rede exclusivamente pelo endereço MAC.    

- Os ultimos 3 octetos podem ser atribuidos conforme os fabricantes desejarem na condição que só atribuam endereços unicos e diferentes para manter a unicidade global dos endereços MAC    

- Ethernet usa o endereço MAC para garantir que o dado tem um máquina emissora e uma máquina recebedora, isso faz com que cada nó saiba exatamente quando o tráfego lhe é destinado.

### Hexadecimais - Forma de representar numeros usando 16 digitos   

- Já que não existem numerais individuais para representar digitos maiores que 9, usam-se letras para representar os números 10, 11, 12, 13, 14 e 15.  

```
hexadecimal - | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A  | B  | C  | D  | E  | F  |
decimal     - | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 
```    

### Octeto    

- Em rede computacional, um octeto é qualquer numero que pode ser representado por 8 bits    

## Unicast, multicast e broadcast    

1. Unicast
    - Transmissão para apenas um unico endereço recebedor. Se o bit menos significativo do primeiro octeto do endereço de destino for 0, o quadro ethernet é destinado apenas para o endereço de destino. Basicamente o dado é enviado a todos no dominio, mas só o recebedor específico o recebe.    

2. Multicast
    - Se o bit menos significativo do primeiro octeto do endereço de destino for 1 significa que o dado pode ser recebido por todos dispositivos na rede local, sendo aceito ou descartado dependendendo de varios outros critérios.    

3. Broadcast
    - Sinal é enviado a todos dispositivos na rede local e isso é feito com um endereço especial de broadcast. Este endereço é composto apenas por F, deste modo:  **FF:FF:FF:FF:FF:FF**  

## Pacote de dado (*data packet*)   

- Termo abrangente usado para representar qualquer conjunto unico de dado binário enviado através de uma rede. Pacotes enviados pela camada da Ethernet são conhecidos como **quadros ethernet** (*ethernet frame*)  

#### Quadro Ethernet   

- Quadro altamente estruturado de informação apresentada em uma ordem específica de modo que interfaces de rede da camada física conseguem converter uma cadeia de bit enviada por um link em dado util e vice-versa. Todas seções são obrigatórias e possuem tamanho definido.    

1. Preambulo
2. Endereço Destino
3. Endereço Fonte 
4. VLAN
    - Virtual LAN
5. EtherType Field
    - Usado para descrever o protocolo do conteúdo
6. Carga de dados
    - Os dados enviados em si
7. FCS
    - Numero de 32 bits que representa a soma de todo o quadro   

#### [Cyclic redundancy check](https://en.wikipedia.org/wiki/Cyclic_redundancy_check)    

- Conceito crucial de integridade de dados, é a transformação matemática que usa divisão de polinômios para criar um número que representa um conjunto maior de dados. Sempre que for feita em um conjunto de dados, deve se obter o mesmo numero da soma. Normalmente usada em detecção de erros, para averiguar se há corrupção dos dados.