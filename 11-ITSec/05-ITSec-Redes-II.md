# Segurança de Redes II
- *Essencialmente, é impossível prever todos tipos de riscos, o real objetivo é na verdade fortalecer os sistemas com intuito de reduzir os riscos o máximo possível.*  

# 1. Fortalecimento
## 1.1 **De Sistemas**
### 1.1.1 **Vetor de Ataque**
- Método ou mecanismo pelo qual um invasor ou malware ganha acesso a uma rede ou sistema.
    - Por exemplo, um anexo de e-mail, procolo de rede ou mesmo o *input* do proprio usuário. Mas continuam, essencialmente, um caminho pela qual um invasor obtém acesso indevido ao sistema.

### 1.1.2 Superfície de Ataque
- ***É a soma de todos os Vetores de Atk. em um sistema.*** Ou seja, todos os diferentes modos que um invasor poderia obter acesso ao sistema.
- Não é possível conhecer todas as vulnerabilidades do sistema, então, considere todos os pontos de acesso pelos quais um agente externo poderia interagir com nossos sistemas como uma possível superfície de ataque. 
- Há muitas abordagens que você pode usar como especialista em suporte de TI para reduzir as superfícies de ataque, e todas se resumem a simplificar sistemas e serviços. ***Quanto menor a complexidade, menor a chance de falhas não detectadas.***
    - Esse conceito também se aplica ao acesso em ACLs. **Só dê acesso quando for realmente necessário**. 
    - **Outra maneira de manter as coisas simples é reduzir suas implementações de software.** Em vez de ter 5 soluções de software diferentes para 5 tarefas distintas, *substitua-as por uma solução unificada, se possível.*  

# 2. **Firewall Baseado em Host**
- É um firewall no proprio computador-cliente que os protegem de serem comprometidos, on quando em redes desconhecidas ou de hosts potencialmente comprometidos dentro da propria rede.
- ***Nosso firewall baseado em rede tem o dever de proteger nossa rede interna filtrando o tráfego que entra e sai dela. Já o firewall baseado em host, em cada host individual, protege uma única máquina***.
    - *Como em nosso firewall baseado em rede, ainda é importante começar com uma regra de negação implícita.*
    - *Um firewall baseado em host é crucial na redução do que é acessível a um invasor externo.*
- **Se os usuários do sistema tiver direitos administrativos, ele poderá alterar as regras e as configurações do firewall.**  

## 2.1 Host/Rede Bastião
- São os hosts da rede que estão em contato direto com a internet, sendo especificamente reforçados e minimizados para reduzir o que pode ser executado neles.  

# 3. **Registros e Auditoria**
- Parte essencial de qualquer arquitetura de segurança; Não adianta ter todas essas defesas implementadas se não dá pra ver se estão funcionando, precisando que se tenha visibilidade dos sistemas de segurança em uso, registros de todos os dispositivos e equipamentos de infraestrutura gerenciados para que se saiba o tipo de tráfego reccebido.
    - *Também precisamos de maneiras de proteger os registros e facilitar a análise e revisão.*
    - Depende do que está sendo registrado e dos eventos que devem ser registrados, por exemplo, **um servidor de autenticação registra cada tentativa de autenticação, seja ela bem-sucedida ou não**, **já um firewall registra o tráfego que corresponda às regras com detalhes como endereços de origem e destino e portas sendo usadas**.
        - *Essas podem ser usada para detecção de ataques ou de comprometimentos no sistema*. 

## 3.1 Sistemas de Gerenciamento de Eventos e Informações de Segurança,
- Ou *SIEMs*, podem ser definidos com um servidor central de logs com ferramentas adicionais de análise para fins de administração de segurança.
    - Há muitos campos importantes para capturar nas entradas de registro, ***como o carimbo de data/hora, o evento ou código de erro, o serviço ou aplicativo que está sendo registrado, a conta do usuário ou do sistema associada ao evento e os dispositivos envolvidos no evento***. 

### 3.1.1 *Normalização*
- Conversão de dados de logs em um formato padronizado e consistente com uma estrutura definida de registros. 
    - **Por exemplo**, as entradas de registro do firewall podem ter a *data/hora* e o formato de *ano, mês e dia*, já os registros a máquina-client *dia, mês e ano*. 
        - *Para normalizar esses dados, você escolhe um formato padrão e depois define os campos dos tipos de registro que precisam ser convertidos.*
    - **Quando os registros são recebidos dessas máquinas, as entradas de registro são convertidas** no padrão definido e armazenadas pelo servidor de registro permitindo analise e comparação de dados de diferentes tipos e de maneira muito mais fácil.
    - ***Quando os registros estiverem centralizados e padronizados, você poderá criar alertas automatizados com base em regras***.

#### 3.1.1.1 exemplos de servidores *SIEM* 
- *rsyslog*, de código aberto
    - https://github.com/rsyslog/rsyslog
- *Splunk Enterprise Security*
    - https://www.splunk.com/
- *IBM Security Qradar*
    - https://www.ibm.com/products?q=IBM%20Security%20QRadar%20SIEM
- *RSA Security Analytics*
