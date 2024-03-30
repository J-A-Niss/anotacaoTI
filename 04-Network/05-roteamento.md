# [Roteamento](https://pt.wikipedia.org/wiki/Routing_Information_Protocol)   

- Processo pela qual um Roteador encaminha tráfego dependendo de seu endereço destino, possuindo duas interfaces, sabendo que precisa de no mínimo duas redes para funcionar; ***essencialmente o roteador entrega informação ao endereço mais proximo do destino que tiver.***

1. Roteador recebe um pacote de dado
2. Roteador examina o IP destino do pacote
3. Roteador procura a rede-destino do IP na tabela de roteamento
4. Roteador encaminha o pacote para a interface mais próxima da rede remota, determinado com info. adicional da tabela de roteamento.    

- Essas etapas são repetidas até que o tráfego chegue em seu destino.

## [Tabela de roteamento](https://pt.theastrologypage.com/routing-table)    

- Essencialmente é uma lista de todas as redes que o roteador conheçe e suas distancias em termos de *"saltos"*, isso é usado para encontrar o próximo salto ou rota subsequente para um pacote de dados, variando conforme o tamanho e modelo do roteador; possuindo pelo menos 4 colunas:   

1. Rede destino
    - Contém uma linha para cada rede que o roteador conheçe. O roteador tem uma definição para a rede e sabe quais endereços essa rede tem.   

2. Proximo salto (*next hop*)
    - O endereço do proximo roteador que deveria receber dado pretendido à rede destino; ou indica que a rede esta diretamente conectada ao destino e não há mais saltos a fazer.   

3. Total de saltos (*total hops*)
    - Parte responsável por entender qual  o caminho mais curto para a rede destino, analisando qual a melhor rota enviar os dados.    

4. Interface
    - O roteador precisa saber por qual de suas interfaces deve enviar os dados    

## Protocolo de roteamento   

- Protocolo especial usado por roteadores para se comunicarem e partilharem informação, são divididos em dois, ***protocolo interno e externo***   

1. Interno
    - **Usados pelo roteador para partilhar informações dentro de um sistema autonomo**; esse sistema autonomo sendo um conjunto de redes sob o controle de um unico operador, como por exemplo, uma empresa que precisa transferir dados entre varios escritórios, cada qual contando com sua propria rede local   . Esses por sua parte estão subdivididos e duas categorias, *estado de conexão* e *vetor de distancia*
        1. Estado de conexão (*link state*)
            - Cada roteador anuncia o estado da conexão de cada interface, essas interfaces podendo estar conectadas a outros roteadores ou redes, essa informação é então, propagada a todos os roteador do sistema autonomo.
            - Isso faz com que cada roteador do sistema tenha informação detalhada de cada roteador do sistema, com essa informação o roteador executa algoritmos complexos para determinar o melhor caminho ao destino.
        2. Vetor de distancia
            - Forma mais antiga, basicamente olha sua tabela de rede e a envia aos roteadores vizinhos, ou seja, todo roteador conectado. Nesse modo o roteador não sabe do sistema todo.

2. Externo
    - **Usado por roteadores para partilhar informação fora de um sistema autonomo**  

## RFC (request for comments)   

- RFCs eram uma ferramenta que permitia que os acadêmicos discutissem como os computadores poderiam se comunicar. Ao longo do tempo os RFCs passaram a pertencer à IETF, ou *Força-Tarefa de Engenharia da Internet*, uma comunidade aberta responsável por desenvolver e aplicar os padrões necessários para que a Internet continue funcionando.    

### Espaço de Endereço Não-Roteável   

- São faixas de IP reservadas para uso por alguém que não possa receber roteamento. Nem todo PC conectado à internet precisa se comunicar com todo pc conectado na internet e esse espaço permite que um nó de rede se comunique entre si, mas que nenhum roteador gateway vai encaminhar tráfego à rede