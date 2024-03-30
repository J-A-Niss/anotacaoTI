# Endereço de IP   

- Endereço composto de numeros de 32 bits compostos de 4 octetos sendo que cada octeto é geralmente expresso em numeros decimais. Um unico octeto pode representar todos numeros decimais. Este formato é conhecido como notação decimal pontuada, por exemplo:

```
172.16.254.1

172 - 10101100
16  - 00010000
254 - 11111110
1   - 00000001
```

- IP é distribuido em grandes conjuntos a varias organizações e empresas, **não sendo responsabilidade do fabricante, diferente do endereço MAC**, tornado o endereço de IP mais hierárquico e mais facil de armazenar em comparação ao endereço físico. ***O endereço de IP pertence a uma rede e não ao dispositivo conectado.*** Endereço de IP é atribuído automaticamente por meio de uma tecnologia chamada *Protocolo de Configuração Dinâmica de Máquino*, e o endereço atribuido desse modo é chamado de IP dinâmico. Normalmente um IP dinamico é reservado pra maquina-cliente e um endereço de IP estático é reservado para servidores e maquinas de rede, mas existem excessões.   

### Datagrama de IP   

- Série de campos altamente estruturados e estritamente definidos; são os pacotes dentro do protocolo de IP, tal qual os pacotes da camada ethernet. Composto de cabeçalho e a carga, é muito mais complexo que um quadro Ethernet. Atualmente a versão mais comun é a IPv4, mas a IPv6 esta vendo um crescimento no preocesso de adoção.  

## IP de maquina e de rede(*host/network*)

- IP pode ser separado em 2 partes, o da rede e o da maquina, ou *host*  

#### Sistema de classe de endereço   

- Separa em 3 classes de endereço para definir o espaçõ global dos endereços de IP, e cada classe representa uma rede com tamanho diferente. *É possível determinar a classe de um endereço baseado no primeiro octeto.*   

1. **Classe A**
    - Primeiro octeto é usado para o ID de rede e os ultimos 3 são da maquina, essa é a maior, sendo a possível até 2^24 ou **16.777.216** endereços diferentes.    

2. **Classe B**
    - Os dois primeiros são para rede, os dois ultimos para máquina, segunda maior.   

3. **Classe C**
    - Os tres primeiros para rede, o ultimo para máquina.   

```
Classe | 1° octeto | Total     |
A      | 0-126     | 16.777.216|
B      | 128-191   | 64.000    |
C      | 192-224   | 254       |
```   

## Sub-rede (subnetting)   

- Simplesmente é o processo de pegar uma rede maior e separa-la em pedaços menores. Isso ajuda no quesito organizacional sendo que cada sub-rede terá seu próprio roteador-portão aginda como entrada e saída   

## Mascara de sub-rede  

- Assim como o endereço de IP, mascaras de sub-rede são números de 32 bits normalmente gravados como quatro octetos em decimal que possuem como objetivo trazer ainda mais especificidade aos endereços de IP, trazendo mais precisão     

## CIDR (*classless inter-domain routing*)     

- ***Roteamento entre Domínios sem Classe*** , basicamente amplia o conceito de sub-rede usando mascaras de sub-rede para demarcar redes, ***demarcar significando colocar em funcionamento*** dando luz ao termo *"ponto de demarcação"*
    - Ponto de demarcação descrevendo onde uma rede/sistema termina e outro começa   
- Basicamente o CIDR combina ID de rede E sub-rede, por meio de uma / ao final do endereço, por exemplo: *195.195.195.0/24*. Em um mundo onde a classe do endereço não importa, só se necessita da informação da mascara de rede para determinar o ID da rede. Ou seja, **essa pratica simplifica a forma que roteadores e outros dispositivos de rede vêem partes de um endereço de IP, como tambem viabiliza redes com tamanhos mais arbitrários.**