# 1. ***ITSec***
*IT Security* ou Segurança de TI é o ramo que estuda e analisa potenciais ameaças à sistemas e computadores.

## 1.1 **CIA**
- *Confidentiality, Integrity e Availability*; ou Confidencialidade, Integridade e Disponibilidade. Acronimo do que é chamado de tríade CIA, um modelo guia para designar políticas de segurança de informação.
    - **Confidencilidade**
        - Como o nome implica, envolve manter seus dados seguros e afastados de olhares indesejados. Como por exemplo, uma senha que não é contada para ninguém, usada para aumentar a segurança de sua conta.
    - **Integridade**
        - Integridade de manter os dados precisos e inalterados. Por exemplo, um site que indica que o arquivo tem 3MBs e quando voce o baixa tem 30MBs indican que algo inferiu na integridade do arquivo do seu download.
    - **Disponibilidade**
        - Para que os dados estejam facilmente acessíveis a quem precisar do acesso.

## 1.2 Terminologia
1. ***Risco*** é a possibilidade de sofrer uma perda durante um ataque ao sistema.
2. ***Vulnerabilide*** é uma falha no sistema que pode ser usada para compromete-lo. 
    - ***Vulnerabilidade de dia zero*** é uma vulnerabilidade desconhecida pelo desenvolvedor ou vendedor, mas conhecida pelo invasor; *chamada de dia zero porque se tem zero dias para conserta-la* e já foi explorada por invasores.
3. ***Exploit*** é um software usado para ter vantagem de um *bug* de segurança ou uma *vulnerabilidade*.
4. ***Ameaça*** é a possiblidade de perigo que pode explorar uma vulnerabilidade, ou seja, **possiveis invasores**.
5. ***Hacker*** é alguém que tenta explorar ou invadir um sistema
6. ***Ataque*** é uma tentativa real de causar dano ou invadir um sistema
7. ***Malware*** é a abrevição de *malicious software* ou software malicioso.

# 2. ***Malware***
- *Malicious Software* ou Software Malicioso é um software cujo proposito é causar algum tipo de dano, roubando/deletando/modificando arquivos.

Para mais info. sobre prot. antimalware: https://colab.research.google.com/drive/1MKxEvVGAYvCppaFOUVT0Cl9DUMg1JE4i#scrollTo=Ak3aFkgWkqzN

## 2.1 *Vírus*
- Funciona como um vírus da vida real, na qual o virus de apega à uma célula do seu corpo e usa para se reproduzir e lhe causar dano, o vírus de computado se apega à um código executável, como um programa, e quando esse programa é executado ele se apega à outros arquivos que se tornam suscetíveis à infecção pelo vírus, onde ele se reproduz nos arquivos e causa mais dano.

## 2.2 *Worms*
- Parecido com o vírus, mas no caso ele não precisa se apegar à um arquivo para se espalhar, sendo independente e podendo se espalhar por canais, como a rede local.

### 2.2.1 *Love Bug*
- Foi um caso famoso de um worm que se espalhou por meio de um **arquivo executável disfarçado como arquivo de texto**, enviado por email parecendo ser uma confissão amorosa, que então era executado, se propagando por meio de software, fazendo outros ataques maliciosos, danificando arquivos etc. 
- Ele se espalhava roubando endereços de email e clientes de chat no computador da vítima, replicando o email para todos os contatos da vítima, sendo ***esta uma das maiores razões que não se abre arquivo executável de remetentes desconhecidos***.  

## 2.1 *Adware*
- Malware que faz anuncio de propaganda e coleta dados, muitas vezes se faz download de adware de forma legítima, acontecendo quando se concorda com termos de serviço que permitem o uso de software gratuito em troca da exibição de anúncios. Em outros casos, ele é instalado sem consentimento e pode *fazer outras ações maliciosas além de só exibir anúncios*.

## 2.3 *Trojan*
*Na mitologia grega, existe a história invasão de Troia. Onde os gregos constroem uma estátus de um cavalo e dão de presente aos troianos, dentro da qual se escondem e atacam a cidade durante a noite.*
- Um *Trojan* é um malware que se disfarça de algo, *e como os troianos*, o usuário precisa aceitar e executar o arquivo para que este cause dano.  

## 2.4 *Spyware*
- Malware cujo propósito é espionar o usuário, incluindo monitoramento da tela do usuário, pressionamento de teclas (keylogger), webcam, microfone etc. E então enviar todos estes dados para o remetente.

### 2.4.1 *Keylogger*
- Tipo de spyware cuja função é detectar o pressionamento da tecla do computador, podendo capturar de mensagens à senhas e logins.

## 2.5 *Ransomware*
- Malware que faz seus dados refém até que um resgate seja pago.

### 2.5.1 *WannaCry*
- Ransomware emblemático, de maio de 2017. O malware explorou uma vulnerabilidade em sistemas Windows antigos e infectou máquinas pelo mundo todo, chegando a desativar os sistemas do serviço público de saúde da Inglaterra, causando uma crise de saúde pública. 

## 2.6 *BotNet*
- Rede computadores comprometidos, cujo objetivo é de usar o poder das máquinas infectadas para fazer alguma função distribuída, como por exemplo, *mineração de bitcoin*.
    - Mineração de bitcoin envolve uma máquina realizar cálculos que consomem seus recursos, e um ataque de botnet muito popular foi de sequestrar sistemas para fazer tais cálculos, sem a anuência do usuário.

## 2.7 *Backdoor*
- É uma vulnerabilidade que permite o acesso à um sistema, caso as outras vias de acesso estejam bloqueadas e são geralmente instaladas quando se tem um acesso ao sistema e invasores querem manter este acesso.

## 2.8 *Rootkit*
- Como o nome indica, é um kit para o acesso *root*, sendo ferramentas usadas que um administrador usaria, permitindo modificações em níveis de admin ao OS. É de dificil detecção por usar o proprio sistema para se esconder, executando processos que não são demonstrados no gerenciador de tarefas.

## 2.9 *Logic Bomb*
- Malware instalado propositalmente que *após um certo gatilho*, como um período de tempo ou algum outro evento realizado pela máquina, *executa um programa malicioso*.
    - Houve um caso famoso de [bomba lógica em 2006](https://www.independent.co.uk/news/business/news/disgruntled-worker-tried-to-cripple-ubs-in-protest-over-32-000-bonus-481515.html) quando um administrador de sistemas de um banco instalou uma bomba lógica que derrubou os serviços da empresa para tentar diminuir o valor das ações. O funcionário foi pego, indiciado por fraude e condenado a 8 anos de prisão.  

# 3. **Ataques à rede** 
- Ataque que alvejam a rede em si.

## 3.1 Envenenamento de Cache
- Engana um servidor DNS com um endereço de um DNS falso que vai apontar à um servidor comprometido, que então te transmite endereços DNS falsos quando voce tentar acessar sites legítimos, podendo se espalhar para outras redes se outros servidores estiverem recebendo informações de um servidor comprometido, propagando o ciclo.

### 3.1.1 [Ataque no Brasil em 2011](https://threatpost.com/major-dns-cache-poisoning-attack-hits-brazilian-isps-110711/75859/)

## 3.2 Meddler-in-the-middle
- Coloca um invador entre 2 hosts que acreditam estarem se comunicando diretamente, na qual o invasor monitora a comunicação entre os hosts a modificando.

### 3.2.1 *Cookie Hijacking*
- Tambem conhecido como *Session Hijacking* ou **Sequestro de Sessão**, na qual o invasor utiliza um token de segurança já pré-gerado pelo host se comunicando o servidor para poder roubar as informações; por exemplo, acessar o Youtube com sua conta e ter sua sessão sequestrada por um invasor, se passando por voce para acessar sua conta.
    - Geralmente esse tipo de sequestro se dá em acessos de **pontos públicos**

#### 3.2.1.1 *Rogue Access Point*
- É um ponto de acesso malicioso, instalado em uma rede sem o consentimento/conhecimento do administrador.

#### 3.2.1.2 *Evil Twin*
- Parecido com o *RogueAP*, mas no caso é um rede que se faz parecer identica à outra, com objetivo de enganar um usuário à se acessar nela, rede esta que é controlada geralmente por um administrador malicioso com objetivo de monitorar o tráfego de quem se conecta à ela.    

## 3.3 *Denial of Service*
- Um DoS é um ataque envolve sobrecarregar um sistema ou servidor com acessos falsos, com objetivo de impedir acesso de usuários legítimos.

### 3.3.1 *Ping of Death*
- Um ataque de *Ping of Death* (PoD) é um ataque de negação de serviço em que o invasor visa interromper uma máquina, enviando um pacote maior que o tamanho máximo permitido, fazendo com que a máquina visada trave ou falhe.

### 3.3.2 *Hug of Death*
- Um DoS, mas feito por usuários legítimos que acabam por sobrecarregar acidentalmente uma rede.

### 3.3.3 *Distributed DoS*
- É um DoS, mas feito com multiplos sistemas, tendo por objetivo sobrecarregar ainda mais redes ainda maiores. Geralmente feitos por meio de botnets
    - [Para mais info sobre DDoS](https://colab.research.google.com/drive/1v6e25s0mlJXaVj_HnVr7y3A8C4nuWDs1#scrollTo=Yu6uXvGxlCDa)

# 4. **Ataques do lado do Cliente**

## 4.1 **XXS**
- *Cross-site scripting attack* ou ataque de scripting em varios sites é um ataque que envolve um invasor injetar código malicioso que alveja o usuário de um serviço, muito usados para ***sequestro de sessão***.

### 4.1.1 **SQL Injection**
- Idêntico ao XXS, mas este alveja o site em si caso este use um banco de dados em SQL, na qual o invasor tem controle do banco de dados, podendo manipula-los como quiser.

## 4.2 **Ataque de Senha**
- Utiliza um programa que tenta descobrir a senha.

## 4.2.1 **Força Bruta**
- Utiliza um programa que tenta adivinhar sua senha, usando literalmente ***todas possíveis combinações dos carácteres permitidos pelo site em questão***. E dependendo do tamanho da senha pode ser rápido ou praticamente impossível. *Teoricamente*, do mesmo modo que é impossível ter uma porta *inarrombável*, é impossível se proteger completamente de um ataque de força bruta, porém, dependendo da complexidade da segurança do sistema, mais tempo e recursos computacionais serão necessários, de modo que esses ataques se tornem impraticáveis.
 
### 4.2.1.1 ***Comprimento > c0mpl3x1d4d&***
```
Senhas geralmente são compostas por uma combinação de: 56 letras + 10 números + 10 carácteres especiais totalizando 76 possíveis carácteres

>> senha de 6 carácteres  = 76 x 76 x 76 x 76 x 76 x 76 = 192.699.928.576 possíveis combinações diferentes

senha de 10 carácteres = 76 x 76 x 76 x 76 x 76 x 76 x 76 x 76 x 76 x 76 = 6.428.888.932.339.941.376 possiveis combinações diferentes

ignorando letras e carácteres especiais:

senha de 6 carácteres  = 56 x 56 x 56 x 56 x 56 x 56 = 30.840.979.456 poss. comb.

>> senha de 10 carácteres = 56 x 56 x 56 x 56 x 56 x 56 x 56 x 56 x 56 x 56 = 303.305.489.096.114.176 poss. comb. 
```
- ***É inegável que a complexidade é sim um fator no total de combinações possíveis da senha, a tornando mais robusta por consequência, mas ironicamente, um senha mais comprida e com menos carácteres especiais, e por consequencia mais facilmente lembrada, pode ser mais segura.*** 
    - **Ou seja; comprimento da senha exponencializa a dificuldade de adivinhação do programa, tornando a senha muito mais segura do que pela complexidade dos carácteres**.

### 4.2.1.2 Captcha
- Um captcha é um tipo de filtro que tenta distinguir um acesso de um humano do acesso de um robo, usado como um tipo de protetor da senha contra um método de força bruta.  

### 4.2.1.3 Ataque de dicionário
- Identico ao de força bruta, mas testa *palavras* comuns ao invés de combinações de carácteres.

# 5. [***Engenharia Social***](https://colab.research.google.com/drive/1O0WwNfPF-ALmuzMxbpvx_GLral0NJqX5#scrollTo=k1eJxqhWdL6R)
- ***O Usuários é sempre o elo mais fraco de qualquer sistema de segurança.***
- Engenharia social envolve a manipulação psicológica do usuário para que este revele informações sensíveis, geralmente sob engano. Um dos métodos mais comuns de Engenharia Social é o ataque de *phishing*.

## 5.1 *Phishing*
- *Phishing*; do ingles *fishing* ou pescar, tenta enganar a vítima a liberar dados pessoais como logins, senhas, números de cartão etc.
- Pode se dar tambem por mensagens de texto; em via de regra, *todo tipo de comunicação falsa com intuito de enganar a vítima a liberar informação é considerado phishing*.

### 5.1.1 *Spear Phishing*
- *Idêntico ao phishing, mas alveja um indivíduo/grupo específico*, com o meio de comunicação falso contendo informações sua, como nome ou algum outro tipo de informação de contato.

## 5.2 *Spoofing*
- Envolve a falsificação do endereço de email do remetente com o intuito de enganar a vítima a achar que o email é legítimo.

## 5.3 *Ataques Físicos*
- ***Não envolvem atacar fisicamente a vítima***, mas sim tentar engana-la fora da internet.

### 5.3.1 *Baiting*
- Tipo de ataque físico que envolve *'abandonar'* um dispositivo, como um USB, em algum lugar com o objetivo de que a vítima conecte o dispositivo à sua propria máquina.

### 5.3.2 *Tailgating*
- Envolve seguir um funcionário legítimo em area restrita, cujo acesso não deveria ser permitido.
