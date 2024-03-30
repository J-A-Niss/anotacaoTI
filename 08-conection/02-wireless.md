# Wireless   

- Um jeito de montar redes, porem sem fios. As especificações são definidas pelos padrões [IEEE 802.11](https://en.wikipedia.org/wiki/IEEE_802.11), esse conjuntos tambem chamado de familia *oitencos-e-dois onze* compõe o conjunto de tecnologias chamados de WiFi. Dispositivos sem fio se comunicam basicamente por ondas de radio, e dispositivos 802.11 podem até operar em diferentes **bandas de frequencias**, mas geralmente adotam os mesmos protocolos; ***banda de frequencia sendo certos especros de rádio que foram delimitados para serem usados para certas comunicações***, *geralmente wifi opera 2.4 e 5 gigahertz*.  

- As especificações mais comuns de 802.11 são *802.11b, a, g, n* e *ac* , listados na ordem que foram adotados, cada versão tendo uma melhoria sobre a anterior. Agora, em termos de modelo de rede, *802.11 é como se interage tanto na camada de física e de enlace de dado*. ***Um quadro 802.11 possui varios campos:***
    1. *Controle de quadro* - 16bits e contem varios subcampos que descrevem como o quadro deve ser processado
    2. *Duração* - especifica o tamanho do quadro em si, *tipo o checksum só que não*
    3. *4 campos de endereço* - São 4 campos porque precisa haver espaço para indicar qual ponto de acesso sem fio deve estar processando o quadro.
        1. o primeiro representa o endereço mac do ponto de acesso
        2. o segundo é o endereço da rede de destino do envio
        3. endereço receptor
    4. Controle de sequencia - na verdade é colocado entre o terceiro campo de endereço e o quarto campo de endereço; possui 16 bits e um numero sequencia usado para acompanhar os quadros
        4. endereço do dispositivo enviador em si
    5. Carga da dados
    6. Checksum em si.


## Ponto de acesso  

- Um ponto de acesso serve como ponte entre a parte com e sem fio de um rede.  

### Configurações de rede   

1. Rede Ad-hoc
    - Não possui necessariamente uma infraestrutura, vendo que os dispositivos se conectam entre si. Não são muito comun.   

2. WLAN ou Wireles LAN
    Consiste de um ou mais pontos de acessos atuando como intermédio entre redes com e sem fio   

3. Rede em malha
    Essencialmente uma rede ad-hoc, só que maior e consistindo primeriamente de dispositivos wireless conectados à uma rede com fio, permitindo implantar mais pontos de acesso à malha sem ter que necessariamente passar cabo por cada um deles.   

### Canais   

- Seções individuais e menores da banda de frequencia geral usada por uma rede sem fio sendo importante por ajudarem a resolver um problema muito antigo das redes, **colisão de domínio; na qual o sinal de um computador da rede pode interromper o outro.** Isso é feito por meio de frequencias diferentes, entendendo que frequencias não são sempre absolutamente identicas, precisa de um pouco de folga na frequencia que o sinal chega e com isso, existem algumas frequencias que mesmo com essa folga não se misturam, de modo que não colidam. É crucial evitar a colisão o máximo possível.

## Segurança   

- Por ser só sinal de rádio enviado pelo ar, hipoteticamente qualquer um no alcance poderia interceptar o sinal e com isso em mente foi desenvolvido o **WEP ou Wired Equivalent Privacy**, sendo essa uma tecnologia de criptografia que oferece um nível muito baixo de privacidade. WEP usa apenas 40 bits para suas chaves, que pode ser quebrado em pouquissimo tempo com computadores modernos sendo o WEP eventualmente substituido pelo ***WPA ou Wifi Protected Access***, este usando uma chave de 128 bits, e o mais comun sendo o ***WPA2 que usa 256 bits*** em suas chaves.   

- Outro modo de incrementar a segurança é por um filtro MAC, que permite apenas dispositivos específicos acessar.