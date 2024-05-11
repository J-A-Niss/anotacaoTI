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
56 letras + 10 números + 10 carácteres especiais = 76 possíveis carácteres

>> senha de 6 carácteres  = 76 x 76 x 76 x 76 x 76 x 76 = 192.699.928.576 possíveis combinações 

senha de 10 carácteres = 76 x 76 x 76 x 76 x 76 x 76 x 76 x 76 x 76 x 76 = 6.428.888.932.339.941.376 possiveis combinações

ignorando letras e carácteres especiais:

senha de 6 carácteres  = 56 x 56 x 56 x 56 x 56 x 56 = 30.840.979.456 poss. comb.

>> senha de 10 carácteres = 56 x 56 x 56 x 56 x 56 x 56 x 56 x 56 x 56 x 56 = 303.305.489.096.114.176 poss. comb. 
```
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

# 6. [***Criptografia***](https://colab.research.google.com/drive/1aHMWY1F0gc10exlVUsZOUT1cJ3W-xDD1#scrollTo=VHFF5ddpSfKh)
- É a prática e estudo da conversão de dados de um formato legível à um formato *codificado* com o objetivo de ocultar mensagens. Seu estudo é chamado de **Criptologia**
    - Seu inverso é chamado de *criptoanálise*

## 6.1 **Encripção**
- Ato de pegar uma mensagem de texto simples e aplica-la uma operação denominada *cypher* ou cifra, de modo a gerar uma mensagem ilegível, chamado de *cyphertext* ou texto-criptografado.

### 6.1.1 **Algoritmo de Criptografia**
- É a lógica subjacente usada para criptografar um texto normal, essencialmente são operações matemáticas **muito** complexas usadas para ocultar a mensagem.

#### 6.1.1.1 Algoritmos de Criptog. Simétrico

##### 6.1.1.1.1 **DES** - *Data Encryption Standard*
- Designado pela IBM em conjunto com a NSA (*National Sec. Agency*), adotado então como o primeiro **FIPS, *Federal Info. Processing Standard*** ou Padrão Federal de Proc. de Info. dos USA, significando que era usado para encriptar e proteger dados governamentais.
- O **DES** é uma cifra de bloco simétrica que usa chaves de 64 bits, operando com blocos de 64 bits. ***Apesar da chave ser de 64 bits, 8 bits são usados para verificação de paridade, ou seja, para avergiguar erros. Ou seja, o comprimento real do DES é de 56 bits.***

##### 6.1.1.1.2 **AES** - *Adv. Encp. Standard*
- Substitui o DES, usando blocos de 128 bits e suportando chaves de 128, 192 e 256 bits de comprimento. Devido ao tamanho das chaves, ataques de força bruta ao AES são apenas teóricos por enquanto pelo fato do ***poder computacional, ou o tempo necessário, são completamente inviáveis***.
- CPUs da Intel e da AMD já possuem AES incorporados para agilizar o processo de encripção, tendo em mente que as vezes, essa encripções são feitas em massa, sendo melhor que elas sejam rápidas e de baixo impacto no sistema.

##### 6.1.1.1.3 RC4 - *Rivest Cypher 4*
- Foi uma cifra de fluxo simétrico que era usada simplesmente pela sua velocidade, infelizmente devido à fraquezas e vulnerabilidades inerentes, esta cifra foi abandonada em favor de **TLS 1.2 com AES GCM**.
    - *Isto foi exacerbado com o* [RC4 NOMORE](http://www.rc4nomore.com/) *onde invasores inseriam JavaScript malicioso em websites que induziam a vítima a transmitir pedidos encriptados que continham cookies pessoais, na qual o invasor pega a lista de cookies prováveis e os testa um a um.*

##### 6.1.1.1.4 GCM - *Galois Counter Mode*
- Modo específico de AES, que pega um valor de *semente* aleatorio, o incrementa e criptografa o resultado, criando blocos de texto criptografado numerados em sequência e depois o texto criptografado é incorporado ao simples a ser criptografado.

##### 6.1.1.1.5 *Seed Value*
- Valor secreto usado para inicializar um processo gerado por um software, usando um ou mais valores.   

#### 6.1.1.2 Algoritmos de Criptog. Assimétrico   
##### 6.1.1.2.1 RSA
- Um dos primeiros sistemas práticos de criptografia desenvolvidos, nomeado pela sigla de seus criadores, *Ron Rivest, Adi Shamir* e *Leonard Alderman*. Patenteado em 1983 e lançado em domínio público pela *RSA Security* em 2000.
- O processo de geração de chave em si é incrivelmente complexo para ser abordado, mas basicamente é ***a escolha de dois números primos únicos, aleatórios e muito grandes.***

##### 6.1.1.2.2 DSA - *Digital Sign. Algorithm*
- É um *sist. de cript. assim.* usado para assinar e verificar dados. Patenteado em 1991 e faz parte do padrão de processamento de info. do governo dos EUA. Parecido ao RSA, esse cobre a geração de chave a assinatura e verificação de dados usando pares de chaves. **É importante ressaltar que a segurança do sistema depende da escolha de um valor de semente aleatório que é incorporado ao processo de assinatura.**
    - Em 2010 a Sony **não estava garantindo que esse valor aleatório fosse alterado para cada assinatura**. Isso fez com que um grupo de hackers chamado *Fail0verflow* conseguisse recuperar a chave privada que a Sony usava para assinar softwares para a plataforma. **Isso permitiu a gravação e a assinatura de softwares personalizados que podiam ser executados na plataforma do console**, fazendo com que a pirataria de jogos se tornasse um problema, facilitando a cópia e a distribuição ilícitas de jogos.

##### 6.1.1.2.3 DH - *Diffie-Hellman*
- Algoritmo de troca de chaves.
    1. As partes querem se comunicar por um canal *não-seguro*
    2. As partes escolhem um numero inicial que será público, inteiro, aleatório, enorme e que diferente para cada nova seção
    3. Cada parte escolhe um novo número próprio, que será secreto
    4. Então soma o numero secreto ao público e envia o resultado à outra parte
    5. A outra parte então soma seu número secreto mais a soma do numero público com o número secreto da outra parte
    6. O resultado final é um novo valor, idêntico em ambos os lados, sem liberar informações desnecessárias à terceiros
- Esse algoritmo foi designado para a troca de chaves, mas existem tentativas de adapta-lo para fins de criptografia. Tambem foi parte de PKI, ou sistema de infraestrutura de chave pública.   

##### 6.1.1.2.4 ECC 
- Criptografia de curvas elípticas é um sistema de criptografia de chave pública que usa a estrutura algébrica de curvas elípticas sobre campos finitos para gerar chaves seguras. Sistemas tradicionais de chave pública usam a fatoração de grandes números primos, enquanto a ECC utiliza curvas elípticas. Uma curva elíptica é composta por um conjunto de coordenadas que se ajustam à uma equação. **A vantagem dos sistemas de criptografia baseados em curva elíptica é que eles conseguem segurança semelhante aos sistemas tradicionais de chave pública com tamanhos de chave menores.**
    - *Assim, por exemplo, uma chave de curva elíptica de 256 bits seria comparável a uma chave RSA de 3.072 bits. Isso é uma vantagem enorme, porque reduz o volume de dados que precisa ser armazenado e transmitido ao lidar com chaves.*   

#### 6.1.1.3 *Hash*
- *Hashing* é o processo que transforma um dado de qualquer tamanho em um código único com tamanho fixo chamado de *Hash*, sendo usado para facilitar a identificação e comparação de dados. **O *output* em si será sempre único, *exceto o tamanho, que será sempre idêntico*** de modo que dois *inputs* diferentes nunca resultem no mesmo *output*. Tambem ajuda a identificar cópias em bancos de dados ou arquivos.
    - Por exemplo: *Se você usar a função de hash "MD5" para transformar a frase "Olá, mundo!", ela gerará o código "5eb63bbbe01eeed093cb22bb8f5acdc3".*
- Isso torna o dado em questão em uma *hash*:
1. Determinística
    - Mesmo dado sempre gerará o mesmo *hash*
2. Eficiente
    - A função é rápida de calcular
3. Única
    - Diferentes dados geram diferentes *hashes*

##### 6.1.1.3.1 *Hash Criptográfico*
- Distinto da criptografia em si devido ao fato que são unidirecionais, ou seja, *não da pra recuperar o dado original por meio do hash.* Por exemplo, no processo de autenticação de senha a senha em si é colocada e comparada à um hash da senha da conta, que é a informação salva de fato no banco de dados, caso o hash da senha da conta não ser congruente com a senha fornecida o acesso é negado. Neste caso se salva os hashes das informação, que não são re-conversíveis nos dados originas i.e: *logins* e *senhas*, então mesmo no caso de uma invasão e os hashes forem vazados, não será uma perda tão grande.
    - ***Neste caso, o que invasores fazem é tentar um ataque de força bruta contra as hashes das informações, quando ocorre uma correlação eles utilizam as informações correlacionadas para entrar na contra.***

##### 6.1.1.3.2 *Algoritmos de geração de hashes criptográficos*
- **MD5**
    - Projetado em 1990, opera em blocos de 512 bits gerando resumos de 128 bits, foi publicado em '92 mas decobriram um falha em '96, na qual criptógrafos recomendaram o uso da *SHA1*, mas não erá nada crítico então a MD5 continuou a ser utilizada até 2004 quando foi suscetível à colisão de hashes, permitindo então que invasores explorem essa falha e em 2008 pesquisadores comprovaram que era possível falsificar certificados SSL com por meio dessa colisão de hashes, que acarretou na recomendação da interrupção de seu uso em 2010 e em 2012 o malware `Flame` usou dessa fraqueza para assinar certificados digitais e se passar por software oficial da Microsoft.  
- **SHA1**
    - Faz parte do pacote de funções de algoritmo de hash seguro, projetado pela NSA e publicado em 1995 ele opera blocos de 512 bits e gera um resumo hash de 160 bits. SHA1 é outra função de hash criptográfico amplamente usada em protocolos famosos, como TLS/SSL, PGP/SSH e IPSec e também é usado em sistemas de controle de versão como o Git, que usa hashes para identificar revisões e garantir a integridade dos dados pela detecção de dados corrompidos ou adulterados. Em 2010 foi recomendado sua substituição pelo *SHA2*, e apesar disso, pesquisadores não conseguirem comprovar  que é possível ocorrer uma colisão *parcial* de hashes, **mas não uma completa**, devido à necessidade computacional que simplesmente ainda não é realista. 
        - ***Apesar disso, em 2017 foi publicada a primeira colisão completa de hashes no SHA1, que custaria, teorica e aproximadamente 6.500 anos de uso de uma unica CPU e 110 em uma unica GPU em computação ininterrupta***.

##### 6.1.1.3.3 *Colisão de Hashes*
- Ocorre quando uma hash dois tipos distintos de dados em um mesmo bloco geram a mesma hash. Usado em ataques de força bruta, vendo que o invasor precisaria 'adivinhar' qual senha corresponde a qual hash salva no banco de dados tentando todas possíveis combinações e passando as na função de hash para ver quais são compatíveis.
    - Senhas comuns são salvas em uma ***'Tabela arco-iris'***, neste caso não se 'adivinha' tanto quanto se puxa possiveis senhas de uma lista pré-definida, trocando então um pouco da necessidade de poder computacional por espaço em disco. Nestes casos se usa então ***'Sal'*** que é mais uma informação adicionada ao hash gerado pela senha. Caso então que um invasor teria que computar mais uma *Tabela Arco-iris* para cada valor de *Sal*. Se *'Sal'* suficiente é usado, os requerimentos de recursos computacionais se tornan impraticáveis.

##### 6.1.1.3.4 MIC
- *Message Integrity Check*, é uma hash de uma mensagem. Pode ser considerado a somatória total (*checksum*) da mensagem, com intuito de averiguar se a mensagem não foi corrompida, devido ao fato de não necessariamente auxiliar na segurança da.   

### 6.1.2 **Chave**
- Algo de único que é introduzido durante a encripção no texto simples, que auxilia na complexação da criptografia. Se a mesma chave é reusada se torna possível quebrar a criptografia de decodificar a mensagen, para isso é introduzido um **vetor de inicialização, ou IV**, que são dados aleatórios integradao à chave de criptografia, na qual a chave resultante é usada para criptografar os dados.
    - **A idéia é de que com a chave mestra, se gera uma chave avulsa de uso unico composta da chave mestra e o IV.** E para **decodificar** é **necessário o IV em texto simples junto com a mensagem codificada**.
- O tamanho da chave é definido em bits e indica seu comprimento total, que tambem define a qta. máxima de chaves de um determinado algoritmo, e seu comprimento define o potencial total de segurança da criptografia. 
- Imaginando um sistema ideal, sem falha nenhuma, na qual a unica chance de um invasor de quebrar a criptografia seria de tentar adivinhar a chave, usando nesse caso o método da ***força bruta***, na qual chaves maiores protegem melhor.
    - Usando o **DES** como exemplo, com 64 bits totais, das quais 8 são dedicados à paridade, ***tendo então 56 bits de chave, o que traz 2^56 ou 72.000.000.000.000.000 de chaves possíveis.***
        - *Eventualmente, com o avanço da técnologia, 56 bits se tornou muito pouco.*

#### 6.1.2.1 **Chave Simétrica**
- Chave simétrica é a que é usada para *encriptar* **e** *decriptar* as mensagens.   

#### 6.1.2.2 **Chave Assimétrica**
- Em contraste à chave simétrica, essa usa uma chave para *encriptar* e **outra** para *decriptar*. O processo funciona do seguinte modo:
    1. Duas pessoas, `A` e `B` querem se comunicar de forma segura, cada um gera uma chave particular
    2. Dessa chave particular, uma pública é derivada
    3. Quando cada parte gera uma chave particular e uma pública, as chaves publicas são trocadas
    4. Quando mensagens são trocadas, se usa a chave publica da OUTRA parte para *encriptar* a mensagen, que só pode ser *decriptada* com sua chave particular.
    6. `A` envia uma mensagen *encriptada* com a chave publica de `B`, para `B` que só poderá *decriptar* a mensagem de `A` com sua propria chave particular.
- ***A força do sistema de criptografia assimétrica vem da dificuldade computacional de descobrir a chave privada correspondente à uma chave pública.*** Nisto, o sistema assim. de criptografia confere 3 qualidades: 
1. Confidencialidade
    - Por meio dos sistemas de *encrip* e *decripção*
2. Autenticidade
    - Conferida por meio da ass. digital, que garante sua não adulteração
3. Não-repudiação
    - E devido à tudo isso, o autor não pode disputar a origem da mensagem, trazendo a gerantia de que a mensagem veio de quem se afirma ser seu autor.
- Devido à tudo isso, a chave assim. é mais *complexa* e *computacionalmente exigente*.   

### 6.2.3 TLS
- Geralmente chamado de *TLS-SSL*, apesar do ssl ter sido depreciado em 2015. **TLS** é um protocolo genérico de comunicações seguras pela rede. Muito usado em browsers web, VoIP, email, mensagens instantaneas e até mesmo segurança de redes wi-fi. O TLS em si nos tras 3 coisas:
1. ***Linha de comunicação segura***, onde os dados transmitidos são protegidos contra interceptação.
2. ***Autenticação das partes*** que estão se comunicando, embora geralmente apenas o servidor seja autenticado pelo cliente
3. ***Integridade da comunicação***, com verificações para detectar a perda ou alteração de mensagens em trânsito.
- Resumidamente, TLS traz uma via segura para que uma aplicação se comunique à um serviço/servidor. Isto é estabelecido por um *handshake TLS*:
1. ***ClientHello***
    - *O cliente estabelece uma conexão com um serviço, inclui informações sobre o cliente, como a versão do TLS com suporte no cliente, uma lista de pacotes de cifra com suporte e talvez outras opções de TLS.*
2. ***ServerHello***
    - *A resposta do servidor seleciona a versão mais alta do protocolo suportada pelo cliente e um pacote de cifra da lista. Também transmite o certificado digital dele e a mensagem final* `ServerHelloDone` 
- O cliente verifica se o certificado do servidor é de confiança e se foi emitido para o nome de host apropriado. Caso o certificado passe na validação, o cliente envia a mensagem `ClientKeyExchange` .
3. ***ClientKeyExchange***
    - *O cliente escolhe um mecanismo de troca de chave para estabelecer uma chave compartilhada com o servidor, que será usada com uma cifra simétrica para criptografar o resto da comunicação. O cliente também envia a mensagem* `ChangeCipherSpec`, *indicando que ele está passando para a comunicação segura e envia uma mensagem* `Finished` *criptografada que tambem serve para encerrar o* `Handshake`
4. ***ChangeCipherSpec***
    - *O servidor tambem responde com um* `ChangeCipherSpec` e `Finished` *criptografado após receber a chave e agora os dados podem ser transmitidos pelo canal seguro.*
- A chave de sessão é a chave de criptografia usada nas sessões de TLS para criptografar os dados trocados. Apesar disso, se a chave privada for comprometida, talvez um invasor decodifique todas as mensagens já trocadas que foram criptografas com as chaves derivadas dessa chave privada. Para impedir isso, existe o conceito de *forward secrecy*.
    - ***Forward Secrecy***: *propriedade do sistema criptográfico que protege as chaves de sessão mesmo que haja comprometimento da chave privada*.  

#### 6.2.3.1 SSH 
- *Secure Shell Protocol* protocolo de rede seguro que usa criptografia para permitir o acesso seguro a um serviço de rede por redes inseguras. Geralmente o SSH é usado para login remoto em sistemas de linha de comando.  

#### 6.2.3.2 [PGP](https://www.philzimmermann.com/EN/essays/WhyIWrotePGP.html)
- [Pretty Good](https://www.youtube.com/watch?v=8xVfjkb-xVs) Privacy é um aplicativo de criptografia para a autenticação de dados com privacidade em relação a terceiros, usando a criptografia assimétrica. É usado geralmente para e-mail criptografado, mas também está disponível para criptografia de disco inteiro ou criptografia de pastas, arquivos ou documentos arbitrários. 

##### 6.1.2.2.1 *Assinatura de Chave Pública*
- Utilizado para que o recipiente da mensagem tenha certeza que a mensagem foi enviada pela pessoa esperada sem ter sido adulterada. Isso é feito combinando com sua chave **particular**, gerando uma assinatura de chave publica.
    7. Agora `B` pode averiguar a autenticidade da mensagem de `A` ao combinar sua mensagen, chave pública e assinatura digital
    8. Se a mensagem não foi modificada a ass. digital fará a validação
        - *Se a mensagem foi adulterada, **nem que seja um único caráctere**, a validação falhará*

##### 6.1.2.1.1 Cifra de Substituição
- Chave simples que substitui letras por outras letras: 
```
e=a | l=m > Hello World = Homma Warmd
```
- Com a chave ou a tabela de substituição fica fácil de traduzir a mensagem fazendo a inversão.

##### 6.1.2.1.2 *Cifra de César*
- Uma cifra de substit. que substit. letras e as deslocas, embaralhando ainda mais a mensagem original, na qual o num. do deslocamento é a chave.

##### 6.1.2.1.3 **ROT13**
- *Rotate 13*, nesta o alfabeto é rotacionado 13 posições, neste caso é uma **Cifra de Cesar que usa uma chave de 13.**
```
A B C D E F G H I J K L M
| | | | | | | | | | | | | 
N O P Q R S T U V X W Y Z 

ROT13: Hello World = URYYB JBEYQ
```

##### 6.1.2.1.4 Cifra de Bloco e de Fluxo
- Relacionado à como a cifra opera no texto simples;
    - ***Cifra de Fluxo*** é a que recebe um fluxo de entrada e *encripta* um cáracter/digito por vez, gerando um carácter/dígito por vez., ou sejam *encripta* 1:1
    - ***Cifra de Bloco*** *encripta* varios cáracteres/digitos por vez, gerando então uma unica unidade de dado *encriptado*. Caso não tenha dado suficiente para preencher o bloco, ele será preenchido para que o texto simples encaixe no bloco de modo uniforme.   

##### 6.1.2.1.5 Message Authentication Codes - MACs
- ***Totalmente distintos do Mac address***. É um bit de informação que permite authenticação de uma mensagen, garatindo que veio de onde diz vir e não foi adulterada.
    - **HMAC** ou *Keyed-hash MAC*, usa um hash criptográfico junto com a chave secreta para gerar um MAC.
    - **CMAC** ou *Cypher-based MAC*, identico ou HMAC, mas usa uma cifra simétrica ao invés do hash criptografado.
        - **CBCMAC** ou *Cypher-block Chaining MAC*, identico ao CMAC, mas usa cifras em blocos.

#### 6.1.2.3 **Chaves Públicas**

##### 6.1.2.3.1 PKI - *Public Key Infrast.*
- Ou **ICP**, *Infraest. de Chave Pública*, é um sistema que define a criação, armazenamento e distribuição de ***certificados digitais***.

##### 6.1.2.3.2 **Certificados Digitais** 
- São arquivos que provam que uma entidade é dona da chave pública em questão, estes por sua parte contém:
1. *Informações sobre a chave publica*
2. *Info. sobre seu proprietário*
3. *Assinatura digital de terceiro que averigua sua autenticidade*
- Se a assn. é válida e se confia no terceiro que a autentica, então se pode confiar na chave em si para que se tenha uma comunicação segura e privada com a entidade proprietária; a entidade responsável por armazenar, emitir e assinar certificados é chamada de autoridade certificadora (AC) sendo esta um componente crucial crucial do sistema **ICP**. 
- A **ICP** é baseada em relações de confiança entre entidades e na criação de uma rede ou cadeia de confiança que começa na ***autoridade certificadora raiz***. Os certificados raiz são autoassinados porque são o início da cadeia de confiança por não ter autoridade mais alta para assinar por eles. A autoridade certificadora raiz usa o certificado autoassinado e a chave privada associada para assinar outras chaves públicas e emitir certificados criando uma estrutura de árvore, com a chave privada raiz no topo. Quando a AC raiz assina um certificado e define o campo "AC" no certificado como verdadeiro, esse certificado é marcado como AC intermediária ou subordinada. Isso significa que a entidade para a qual o certificado foi emitido pode agora assinar outros certificados, e essa AC tem a mesma confiança que a AC raiz. *Quando um certificado não tem autoridade como AC, ele é chamado de entidade final ou certificado de folha.*
- Existe também a ***autoridade de registro (AR)***, responsável por confirmar a identidade das entidades que solicitam a assinatura e o armazenamento de certificados AC.
- Existem tambem ***certificados de cliente SSL/TLS***, componente opcional, que como diz o nome são certificados vinculados a clientes e usados para autenticar o cliente junto ao servidor permitindo controle de acesso a um serviço SSL/TLS.
- Há também ***certificados de assinatura de código***, usados para assinar programas executáveis. Os usuários dos aplicativos assinados podem verificar as assinaturas e ter certeza que o aplicativo não foi adulterado. Isso também confirma que o aplicativo veio do autor do software e não é uma imitação maliciosa.  

##### 6.1.2.3.3 [X.509](https://www.ietf.org/rfc/rfc5280.txt)
- Padrão que define o formato dos certs. digitais e a CRL, que uma lista de certificados revogados. O padrão X.509 foi emitido pela primeira vez em 1988 e atualmente está na versão 3. Um certificado X.509 possui os campos: 
    - **A versão do padrão X.509 que o certificado adota**. 
    - **Número de série**, um identificador exclusivo para o certificado atribuído pela AC, que permite que a AC gerencie e identifique certificados individuais.
    - **Algoritmo de assinatura do certificado**. Esse campo indica qual algoritmo de chave pública é usado para a chave pública e qual algoritmo de hash é usado para assinar o certificado.
    - **Nome do emissor** que contém informações sobre a autoridade que assina o certificado. 
    - **Validade**. Contém dois subcampos, "Não antes" e "Não depois", que definem o período de validade do certificado. 
    - **Assunto**. Esse campo contém informações de identificação sobre a entidade para a qual o certificado foi emitido. 
    - **Informações sobre a chave pública do sujeito**. Esses dois subcampos definem o algoritmo da chave pública juntamente com a própria chave pública. 
    - **Algoritmo de assinatura do certificado**. Idem ao campo "Informações sobre a chave pública do sujeito", esses dois campos precisam ser iguais. 
    - **Valor da assinatura do certificado**, os próprios dados da assinatura digital.

## 6.2 **Decripção**
- O processo reverso da encripção, que envolve 'traduzir' uma mensagen criptograda em texto legível.

## 6.3 ***Security through Obscurity***
- *Segurança pela obscuridade*, é o principio de incrementar a segurança, do que quer que seja, por meio da confidencialidade, ou da informação, ou do processo de obter tal informação.

### 6.3.1 [*Kerckhoff's Principle*](https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle)
- "*Mesmo que tudo do sistema seja conhecido, ele permanece seguro se a chave é desconhecida*"
- **A segurança de um *cryptosystem* ou criptosistema é baseado primordialmente em sua chave**, todo seu resto deve ser considerado conhecimento público. Ou seja, ***mesmo que o algoritmo em si seja conhecido, se a chave for desconhecida, o sistema permanece seguro.***
- Esse tambem é denominado por *Shannon's Maxim*: "O inimigo conheçe o sistema" e "Deve-se designar o sistema assumindo que o inimigo terá total conhecimento sobre ele imediatamente."

## 6.4 **Ánalise de Frequências**
- A pratica de estudar a frequência com que letras aparecem um texto criptografado. A premissa desse tipo de análise é que em línguas escritas algumas letras são mais frequentes que outras, e algumas letras têm maior tendência de aparecerem juntas. Por exemplo, as letras mais comuns em inglês são: "e", "t", "a" e "o" e os pares mais comuns dessas letras são: "th", "er", "on" e "an".  

# 7. ***Esteganografia***
- Prática de ocultar mensagens sem codifica-las. Por exemplo, usar uma tinta 'invisível' que só pode ser vista sob uma luz específica. Técnicas atuais envolve ocultar as mensagens e até arquivos em outros arquivos, como imagens. 