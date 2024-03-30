# Conexões à internet   

## Conex. Discada  

- A mais primordial começou com apenas pequenas redes locais, eventualmente foi incrementada às redes de telefonia usando os proprios fios de telefone nos anos '70, esses sistema conhecido como ***POTS ou Plain Old Telephone Service***, criando o sistema USENET, na qual uma forma desse é usada ainda hoje. Na época alguns locais como faculdades/universidades usavam uma forma muito primitiva de **conexão discada** para troca de mensagens, na qual a conexão discada usa o POTS para transferencia de informação por meio de um numero telefônico usando o ***clássico barulho do modem***, na qual o modem pega os dados que os computadores entendem e os transforma em comprimento de onda audivel que pode ser transmitida pelo POTS.   

- A taxa de transmissão é a medida de quantos bits podem ser passados em uma linha telefônica em um segundo. No final dos anos 50, os computadores só conseguiam enviam uns aos outros dados em uma linha telefônica a 110 bits por segundo. Quando o USENET foi desenvolvido, esta taxa aumentou para cerca de 300 bits por segundo. E quando o acesso discado à Internet virou um insumo doméstico no início dos anos 90, essa taxa aumentou para 14,4 kilobits por segundo.  

## Banda Larga  

- Essencialmente é qualquer conexão que não é discada. Sempre sendo muito mais rapida e duradoura que a conexão discada pelo fato que a conexão esta sempre ativa. Em meados dos anos 90, tornou-se bastante comum as empresas que precisavam de acesso à Internet para seus funcionários usarem várias tecnologias T-Carrier. As tecnologias T-Carrier foram inventadas pela AT&T para transmitir várias chamadas telefônicas através de um único link eventualmente se tornando sistemas de transmissão mais comuns.  

### T-Carrier  

- As tecnologias T-Carrier foram inventadas primeiramente pela AT&T para oferecer um sistema que permitia a muitas chamadas telefônicas passar por um único cabo. Cada chamada telefônica individual era feita em pares individuais de fios de cobre antes do sistema de transmissão 1, que foi a ***primeira especificação T-Carrier, chamado de T1 para abreviar.***
    ##### T1
    - Modo que a AT&T encontrou de transmitir 24 ligações telefonicas por meio de um unico cabo de cobre trançado, essa mesma tecnologia foi reaproveitada para transferencia de dados; cada um dos 24 canais conseguia tranferir dados a 64 kilobits por segundo possibilitando uma unica linha transmitir 1544 megabits/s   

## DSL - Digital Subscriber Line   

- Operando em uma faixa de frequência que não interfere nas chamadas telefônicas normais, uma tecnologia conhecida como linha digital de assinante, ou DSL, conseguia enviar muito mais dados pela rede do que as tecnologias discadas tradicionais. Por muito tempo, os dois tipos mais comuns de DSL eram ADSL e SDSL. *ADSL significa linha digital assimétrica para assinante, ou seja, diferentes velocidades de download e upload para o usuário*. *SDSL significando Symmetrical Digital Subscriber Line* e como o nome indica, a velocidade de up e download são iguais.   

## A cabo  

- O mesmo cabo usado para transmissão televisiva; por meio de frequencias que não interferiam na transmissão televisiva conseguiam fornecer internet de alta velocidade por meio dos cabos, sendo uma das diferenças desse cabo a *tecnologia de largura de banda compartilhada*. Por ser compartilhada existe a chance de diminuição de velocidade em horários de pico, ou seja, *quando muitos usuários acessam ao mesmo tempo*. As conexões à Internet por cabo são gerenciadas pelo que chamamos de modem a cabo. Este é o dispositivo que fica na extremidade da rede do consumidor e o conecta ao sistema de terminação de modens a cabo, ou **CMTS. O CMTS é o que conecta as diferentes conexões a cabo com a rede principal do ISP.**   

## Fibra   

- Muito mais avançado que um cabo, sendo que a fibra ótica envia sinal de luz por um cabo de vidro, e esse possui um alcance de distancia muito maior que um sinal elétrico. Por isso é mais custoso e complexo sendo adotado mais por grandes fornecedores e data centers; porém com o avanço nessas tecnologias, o termo *FTTX ou Fiber To The X* sendo o X o objetivo de onde a fibra era a ser enviada. Esse X pode ser:
    1. *Bairro*, na qual fibra é entregue à uma grande area geografica.
    2. *Prédio*, na qual fibra é entregue à um edificio, tanto residencial quanto empresarial.
    3. *Casa*, na qual a fibra é entregue à um unico domicilio.
- Ao invés de modem, o ponto final da fibra é um *OTN, Optical Terminator Network* converte os dados dos protocolos entendidos pelas redes de fibra para dados que os cabos de par trançado de cobre conseguem entender. ***Nesse caso a fibra entrega a um fio de cobre, e esse fio de cobre, por muitas vezes, entrega ao usuário final.***  

### [Protocolo de banda larga ponto-a-ponto](https://en.wikipedia.org/wiki/Point-to-Point_Protocol)
### [Protocolo de banda larga ponto-a-ponto sobre Ethernet](https://pt.wikipedia.org/wiki/PPPoE)   

### WAN - Wide Area Network  

- Essencialmente funciona como uma unica rede que abrange varios locais físicos e geralmente exigem que voce contrate uma conexão com um provedor, para que ele se encargue do envio de dados entre os locais. WANs são boas no caso de precisar transferir muitos arquivos para varios locais ja que as tecnologias prezam a velocidade. ***Essencialmente e WAN funciona como um tipo de conexão direta entre dois locais distintos, por meio de um provedor, que tambem preve alta velocidade e privacidade***. São varios os protocolos que cercam a WAN:
    1. [Frame Relay](https://en.wikipedia.org/wiki/Frame_Relay)
    2. [Data Link Control](https://en.wikipedia.org/wiki/High-Level_Data_Link_Control)
    3. [Async. Transfer Mode](https://en.wikipedia.org/wiki/Asynchronous_Transfer_Mode)  

- ***Uma alternativa às WANs são Vpn de ponto a ponto***   

#### VPN Ponto a ponto   

- Estabelece um tunel vpn entre dois locais, funciona parecido com vpn tradicional que usuários podem aparentar estarem conectados na mesma rede, mas difere no ponto que o tunelamento é tratado por dispositivos nos dois locais de modo que os proprios usuários não precisam estabalecer suas proprias conexões.