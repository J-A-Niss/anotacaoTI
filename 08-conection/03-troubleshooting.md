# Troubleshooting  

- Por ter MUITAS partes móveis, existe a real possibilidade de falha, ou dano ou das coisas simplesmente darem errado. Alguns dispositivos ja possuem funções integradas de fabrica para auxiliar na resolução desses problemas; por meio da detecção e solução de erros.
    - Det. de erros é a habilidade de um protocolo/programa determinar que algo deu errado
    - Sol. de erros é a habilidade de um protocolo/programa tentar consertar o erro  

## ICMP Internet Control Message Protocol   

- Usado por hosts e roteadores remotos para comunicar mensagens de erros para a origem da transmissão.
    1. Tipo - especifica tipo de mensagem sendo entregue, 8 bits
    2. Código - é o código do erro em si, 8 bits
    3. Checksum - o checksum do pacote, 16 bits
    4. *Resto do cabeçalho* - 32 bits, usado para enviar dado adicional, caso algum outro campo necessite
    5. Carga - Existe exclusivamente para que o recipiente saiba qual transmissão causou o erro, contem todo cabeçalho IP e os primeiros oito bits da carga do pacote problemático  

- ICMP não foi necessariamente feito para interação com humanos, vendo que é mais especifico para interação de rede-computador, visto isso foi feita uma **ferramenta específica  e dois tipos de mensagens para operadores humanos, o Ping**. O Ping é uma ferramente muito simples que permite o usuário mandar uma **mensagem ICMP de solicitação de eco**, essa mensagem pergunta ao destino se o destino *"ainda ta ai?"* e caso o destino ainda esteja funcional e alcançável deve enviar um *ICMP resposta-eco*. É possível invocar um Ping por meio do cmd, digitando Ping e um endereço IP ou um nome de domínio completo.   

## Traceroute  

- Utilidade que te permite descobrir o caminho entre dois nós, transmitindo informação de cada nó ao longo do caminho; isso funciona por meio de uma manipulação do campo do TTL (time to live) no nível IP, quando o TTL chega a zero o pacote é descartado e uma mensagen ICMP de tempo excedido é enviado ao transmissor; ja o traceroute usa o TTL dos pacotes como modo de descoberta de problemas, colocando 1 no primeiro pacote, 2 no segundo, 3 no terceiro e assim em diante, o objetivo sendo de enviar o pacote ao destino final e para isso envia 3 pacotes identicos para cada salto.  

## Teste de conectividade de portas  

- Testes feitos através do CMD para determinar a disponibilidade de portas.
- [netcat](https://en.wikipedia.org/wiki/Netcat)
- [Test-NetConnection](https://learn.microsoft.com/en-us/powershell/module/nettcpip/test-netconnection?view=windowsserver2022-ps)  

### Resolução de nomes   

- Na maioria do tempo o proprio sistema se encarrega disso, mas as vezes é necessário ser feito de modo manual devido a erros. Uma das ferramentas mais comuns é o *nslookup*, disponível em todos OS; Você executa o comando "nslookup" seguido do nome do host e o resultado mostra qual servidor foi utilizado para fazer a solicitação e qual o resultado da resolução.  

#### Servidor DNS publico  

- Servidores de nomes que podem ser usados por qualquer pessoa, gratuitamente, usar esse tipo de servidor é uma boa técnica para solucionar quaisquer problemas de resolução de nomes. Desses todos, o maior é a Level 3 e seu negócio essencialmente revolve em vender conectividade à rede deles para outros provedores que lidam direto com o consumidor. A maioria desses servidores estão disponíveis globalmente por meio do Anycast. ***Sempre se certifique que o servidor de nomes é confiável e tente usar os servidores fornecidos pelos provedores***  
