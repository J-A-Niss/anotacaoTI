# Segurança de Redes
# 1. Fortalecimento de Rede
- Ou *Network Hardening* é o processo de reduzir potenciais vulnerabilidades na rede com o intuito de torna-lá mais segura.

## 1.1 Serviços *Extras*
- Quaisquer serviços que não são absolutamente necessarios são uma potencial fonte de vulnerabilidade, por via de regra, ou são desativados/desabilitados ou seu acesso é considerávelmente restrito.

## 1.2 Negação Implícita
- Conceito de segurança de rede onde propõe que ***tudo que não for explicitamente permitido deve ser implicitamente proíbido***.
    - Não siginifica bloquear todo tráfego, mas sim permitir apenas o que for especificado.
    - Geralmente feito por meio de um *Access-control list*, **ACL** e definidas no firewall, facilitando a criação de regras seguras para o firewall.
    - ***Em vez de exigir que você bloqueie especificamente todo o tráfego indesejado, é possível apenas criar regras para o tráfego que deve ser autorizado.***

# 2. Monitoramente de Tráfego
- É importante por vários motivos, como por exemplo, **permite estabelecer um valor de referência para a aparência típica do tráfego da rede** e isso ajuda a discernir o tráfego comun do incomun, ajudando na detecção de possíveis ataques. 
    - *Geralemente é feito com o monitoramento de rede e a análise de registros.*

## 2.1 ***Análise de Registros*** 
- É a prática de coletar registros de diferentes redes e, algumas vezes, de dispositivos clientes em sua rede, para realizar uma análise automatizada deles. Isso destacará comportamento atípico; possíveis invasões, sinais de infecções por malware etc.
    - Se analisa itens como registros de firewall, registros do servidor de autenticação e registros de aplicativos, procurarando mensagens de interesse em registros específicos, como os do firewall. 
- Os sistemas de análise de registros são configurados usando regras definidas pelo usuário para corresponder a entradas de registro *interessantes*/atípicas. 
    - Elas podem então ser *realçadas* com um sistema de alerta para permitir uma melhor investigação, parte desse processo de alerta também envolveria **categorizar o alerta com base na regra correspondente. Também seria necessário atribuir uma prioridade para facilitar a investigação** e permitir uma pesquisa/filtragem melhor.
        - Os alertas podem assumir a forma de um envio de **e-mail** ou de **SMS** com informações e um link para o evento que foi detectado. ***Seria possível até acordar alguém no meio da noite se o evento fosse grave o suficiente***.
    - A normalização dos dados de registros é uma etapa importante porque registros de diferentes dispositivos e sistemas podem não ter uma formatação comum, podendo ser necessário converter registros em um formato comum para facilitar a análise   

### 2.1.1 Análise de Correlações
- **Processo de coletar dados de registros de diferentes sistemas à eventos correspondentes em outros sistemas**.
    - *Se nota-se uma conexão suspeita vindo de um endereço de origem suspeito e o firewall registrar em nosso servidor de autenticação, pode-se correlacionar essa conexão registrada com os dados do registro do servidor de autenticação, mostrando todas as tentativas de autenticação feitas pelo cliente suspeito.* 
- Essa análise tambem é crucial na etapa de investigação e recriação do evento na hora da detecção do comprometimento  
    - Chamada de **Análise Pós-Falha** (*Post-Fail*) pois é feita, como o nome indica, *após* a catástrofe.
        - O registro detalhado e a análise de registros permitiria a reconstrução minuciosa dos eventos que levaram ao comprometimento, permitindo uma melhor compreensão do que não se fazer na próxima vez, tambem pode ajudar na compreensão do dano causado, entre arquivos deletados e informação roubada, com mais especificidade.

## 2.2 *Splunk*
- Sistema de agregação e pesquisa de registros muito flexível e extensível. O Splunk pode coletar dados de registros de vários sistemas e em uma grande variedade de formatos podendo tambem ser configurado para gerar alertas e permite uma poderosa visualização da atividade com base nos dados de registros. 

## 2.3 *Flood Guards*
- Protegem contra ataques DoS/DDoS identificando tipos de ataque flood, como floods de SYN ou UDP e disparando alertas assim que um limite configurável de tráfego é atingido.
    - Há outro limite chamado ***limite de ativação*** que quando atingido, dispara uma ação pré-configurada, normalmente o bloqueio de tráfego da fonte do ataque identificado, por um período de tempo. 

### 2.3.1 *Fail2Ban*
- Um *flood Guard* de código aberto que detecta sinais de um ataque em um sistema e bloqueia outras tentativas do suposto endereço do ataque. 

# *Firewalls*
- Windows
    - https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc754274(v=ws.11)?redirectedfrom=MSDN  

- Mac
    - https://support.apple.com/pt-br/guide/mac-help/mh34041/mac

- Ubuntu
    - https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands