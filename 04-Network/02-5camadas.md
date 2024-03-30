# Estrutura e funcionamento das redes de computador    

- Entender como aplicações não só funcionam, mas como interagem umas com as outras, com o sistema da empresa e até externamente. Existem regras para essa comunicação, como qualquer outra, e no mundo da computação, essas regras são chamadas de **protocolos**    

## Protocolos   

- Conjunto definido de padrões que os computadores devem seguir para se comunicar.    

## Networking   

- nome dado à todo o conceito de como os computadores se comunicam entre si   

## TCP/IP - Modo de 5 camadas   

1. Camada Física
    - Os componentes físicos i.e: *cabos*. Estão incluídas as especificações dos cabos de rede e os conectores que unem os dispositivos, juntamente com as especificações que descrevem como os sinais são enviados através dessas conexões.
    - De certa forma é a camada mais complexa por terem muitos princípios da matemática, física e engenharia elétrica envolvidos em transmitir incriveis quantidades de dados por um espaço minúsculo em altíssima velocidade sendo ***seu principal objetivo transmitir informação, por meio de um Bit, de uma ponta à outra***.
    - **Não esquecendo que um Bit é a menor representação de dado que o computador entende, podendo ser um 1 ou um 0.**
    - Esses dados são enviados por um fio de cobre, por meio de um processo chamado **modulação**, na qual a **tensão da carga que se move pelo cabo é variada**, e este tipo específico de modulação é chamado de **codificação em linha** ou *line coding*, isso permite que um computador entenda que a carga elétrica, em determinado estado, é um 1 ou um 0.     

2. Camada de enlace *(data link)*
    - Tambem chamada de camada de interface ou de acesso de rede; nesta são enviados os primeiros protocolos. Responsável por dfinir um padrão comun de interpretar os sinais enviados na primeira camada para que dispositivos possam se comunicar em rede. ***O mais comun é o ethernet***    

    - Ethernet - Define protocolo responsável por levar dados à um nó em uma mesma rede. O Ethernet e a camada de enlace permite que dados sejam enviados e recebidos por softwares nas camadas mais altas da rede. ***Essencialmente seu propósito é fazer com que as camadas adiante não precisem se preocupar com a interação com a camada física e qual hardware é usado.*** Com isso, todas camadas adiante podem funcionar independentemente da forma da conexão e a que se conecta. Por exemplo, o browser não sabe nem se preocupa se ta conectado via cabo ou wifi, só que esteja conectado à internet.

3. Rede (internet)
    - Nessa camada ocorre a comunicação de diferentes redes, por meio de roteadores e um conjunto de redes conectadas por meio de roteadores é uma ***internet***. Nessa camada o protocolo mais usado é o IP ou ***internet protocol***     

    - IP é o coração da internet e de todas as redes menores de computadores.   

    - Software de rede é dividido em usuário e servidor, na qual o usuário faz uma solicitação e o servidor responde através da rede. Um nó pode rodar varias aplicações; um pc com um browser aberto com um site de video rodando em uma aba e um programa de email na outra, por exemplo.    

4. Transporte
    - Enquanto a camada de rede transmite dados a nó individual, a de transporte organize o que vai pra onde. Nessa camada é onde o TCP (*transmission control protocol*) é usado, justamente para ordenar qual aplicação recebe o dado enviado pela camada de rede.    

5. Aplicação
    - Nessa camada os protocolos são específicos de cada aplicação, por exemplo navegar na web ou enviar emails.   

### [OSI](https://pt.wikipedia.org/wiki/Modelo_OSI)     

- A principal diferença entre o nosso modelo de cinco camadas e o modelo OSI de sete camadas é que o modelo OSI divide a camada de aplicação em três camadas no total.    

## Conexão   

#### Cabos   

- Subdividem em duas categorias, cobre e fibra;    

1. **Cobre**
    - O dispositivo emissor comunica dados binários através desses fios de cobre alterando a tensão entre duas faixas. O sistema da extremidade receptora consegue interpretear essas mudanças de tensão em 0s e 1s, os quais são traduzidos para várias formas de dados.
    - As categorias mais comuns são a *Cat5, Cat5e e Cat6 (categoria 5, 6)* e as categorias diferem na quantiadade de tranças que resultam em tamanho e velocidade de transmissão diferentes. Categorias mais novas substituem mais antigas por solucionarem problemas ocorrentes, como *Crosstalk, onde um pulso de um fio é acidentalmente detectado por outro.*
    - O tipo mais comun de cabo é o conhecido como *par trançado*, na qual pares de fios de cobre são trançados e esses pares agem como um conduíte unico de informação, a fim de evitar interferençias eletromagnéticas e *crosstalk*. No caso de um Cat6, existem 8 fios, formando 4 pares trançados dentro de uma unica capa. Isso permite que ocorra **comunicação duplex, na qual informação pode fluir pelo cabo em ambas direções.** Isso se da por meio de reservação dos pares de se comunicarem em uma direção e o outro par na outra. Em contrapartida, uma **comunicação simplex é informação enviada em uma unica direção, como por exemplo em uma babá eletrônica.**      

2. **Fibra Ótica**
    - Tubo de vidro da espessura de aprox. um fio de cabelo. Diferente de cobre que usa tensão elétrica, estes tubos transportam pulsos de luz, que são identificados similarmente como 1s e 0s. Muito usados em locais com bastante interferencia eletro-magnética que pode impactar o pulso elétrico do cabo de cobre e podem transmitir dado ***mais rápido e mais longe apesar de serem muito mais caros e frágeis***     

### [Cabo de ethernet](https://en.wikipedia.org/wiki/Ethernet_over_twisted_pair)    


## Porta    

### Porta de rede   

- O ponto final da comunicação, geralmente encontrado nos dispositivos conectados à rede. Algumas portas possuem luz por meio de LEDs, um indicando que o cabo esta conectado em ambos pontos à um dispositivo conectado à rede, e outra luz indicando a transferencia de dado ocorrendo pelo cabo.

### Hubs   

- Dispositivo que permite conexão de varios computadores ao mesmo tempo, sendo que todos dispositivos conectados em um hub se comunicam entre si, e cabe a cada sistema determinar se o dado é para ele ou não. Quando há confusão no envio de pulso elétrico/dado, ocorre uma **colisão de dominio**. Foram substituidos pelo ***Switch***  

#### Colisão de domínio   

- Se vários sistemas tentarem enviar dados ao mesmo tempo, os pulsos elétricos enviados polo cabo podem interferir uns nos outros. Isso faz com que esses sistemas tenham que esperar um período de silêncio para poder tente enviar seus dados novamente.    

- Com intuito de evitar a colisão foi criada uma técnica, por meio do protocolo de ethernet chamada **Carrier Sense Multiple Access with Collision Detection** conhecido como
**CSMA/CD**
### [Carrier Sense Multiple Access with Collision Detection ou CSMA/CD](https://pt.wikipedia.org/wiki/CSMA/CD)    

- Usado para determinar quando os canais de comunicação estão livres e quando o dispositivo pode transmitir dados. Se não houver dado sendo transmitido no segmento, o nó fica livre pra enviar. Se dois ou mais computadores tentam ao mesmo tempo, os computadores detectam a colisão e param, na qual cada dispositivo envolvido aguarda um tempo aleatório para tentar eviar novamente

    1. Carrier Sense: Capacidade de identificar se está ocorrendo transmissão, ou seja, o primeiro passo na transmissão de dados numa rede Ethernet é verificar se o cabo está livre.   

    2. Multiple Access: Capacidade de múltiplos nós concorrerem pela utilização da mídia, ou seja o protocolo CSMA/CD não gera nenhum tipo de prioridade (daí o nome de Multiple Access, acesso múltiplo). Como o CSMA/CD não gera prioridade pode ocorrer de duas placas tentarem transmitir dados ao mesmo tempo. Quando isso ocorre, há uma colisão e nenhuma das placas consegue transmitir dados.   

    3. Collision Detection: É responsável por identificar colisões na rede.   

### Switch   

- Alem de ter toda funcionalidade do Hub, consegue tambem inspecionar o conteúdo do dado de protocolo enviado pela rede para determinar para qual sistema deve ser enviado. Isso praticamente eliminan colisão de rede.   

## Roteador  

- Dispositivo usado para enviar dado para redes independentes, normalmente usado em casas ou pequenos escritórios. Geralmente recebem os dados dos computadores conectados ao provedor    
