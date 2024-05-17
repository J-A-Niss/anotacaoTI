# ***Authenticaction, Authorization, Accounting***
# 1. **Authentication**
- É um modo de garantir que o usuário é quem diz ser. O modo mais comun de autenticação se dá por meio de credenciais, como login e senha. Usa-se o termo `auth-n`.

## 1.1 **Identification**
- *Identificação*, um modo unico de descrever uma entidade específica, como por exemplo, um usuário.  

## 1.2 *Multifactor Authn*
- Sistema na qual usuários são authenticados por varios métodos diferentes, normalmente, varias informações diferentes, unicas ao usuário. Categorizados em 3 tipos de fatores:
1. *Algo que voce sabe*
    - Por exemplo, **senha**.
2. *Algo que voce tem*
    - Algo físico, como por exemplo **cartão de banco**
3. *Algo que voce é*
    - Identificação **biométrica**  

- Idealmente se incorpora pelo menos 2 desses fatores.

### 1.2.1 *2FA*
- *2-Factor Authentication* ou Autenticação de 2 fatores; tipo mais comun de authn que se utiliza 2 dos fatores acima descritos.

### 1.2.2 *OTP*
- *One Time Password*, ou Senha de Uso Único é uma senha que se altera cada vez que se loga em uma conta, geralmente é transmitida por um token físico, como um authenticador.  

#### 1.2.2.1 Tokens de Segurança
- São métodos de gerar senhas unicas.  

##### 1.2.2.1.1 Tokens de Data
- São tokens que usam senhas geradas  por uma semente secreta ou valor aleatório que muda periodicamente, utilizando o NTP para sincronizar a senha atual à conta na qual o token está vinculado.   

##### 1.2.2.1.2 Tokens de Contagem
- Identico ao Token de Data, mas utiliza uma contagem interna para alterar a senha aleatória ao invés de data e hora, que é incrementada sempre que é usada. 

## 1.2.3 Biometria
- Utiliza características da fisiológicas do indivíduo para o identificar, como impressão digital e escaneamento de retina.

# 2. **Authorization**
- Os recursos que uma identidade te da, por exemplo, autorização de administrador de sistemas. Usa-se o termo `auth-z`

# Para mais informações: *https://colab.research.google.com/drive/1VXLefLLdR5m24_X85E83KlRHeoHVpouo#scrollTo=PaWT3-hxwsuz*  

# 3. **Certificados**
- São chaves públicas assinadas por uma autoridade certificadora como sinal de confiança. Para emitir certificados do cliente, uma organização precisa configurar e manter a infraestrutura da AC para emitir e assinar certificados. Parte da autenticação do certificado também envolve a autenticação do cliente no servidor proporcionando autenticação mútua. 

## 3.1 **Datas**
- Os certificados têm duas datas que precisam ser verificadas, `Não é válido antes de` que verifica se o certificado *já* é válido, e `Não é válido depois de` que é uma simples data de expiração. 

# 4. **RADIUS**
- *Remote Authn. Dial-in User Services* ou **Serviço de Usuário Discado de Autenticação Remota** é um protocolo que fornece serviços AAA para usuários em uma rede. Muito comum, é usado para gerenciar o acesso a redes internas, Wi-Fi, serviços de e-mail e VPN.
- Os clientes que querem se autenticar em um servidor RADIUS não interagem diretamente com ele. Em vez disso, quando um cliente quer acessar um recurso protegido, apresenta credenciais de autenticação a um NAS, ou servidor de acesso à rede, que vai retransmitir as credenciais ao servidor RADIUS. O servidor RADIUS verifica então as credenciais usando um esquema de autenticação configurado.

# 5. **Kerberos**
- Protocolo de autenticação de rede em que entidades usam tickets para comprovar a identidade delas em canais inseguros e realizar autenticação mútua. Ele também usa criptografia simétrica para proteger as mensagens contra interceptação e ataques de reprodução.
    - **Primeiro**, o usuário que quer se autenticar digita o nome de usuário e a senha na máquina cliente. O software cliente do Kerberos usa a senha para gerar uma chave *simétrica*, cliente então envia uma mensagem em texto simples ao servidor de autenticação (**AS**) do Kerberos incluindo o ID do usuário que está autenticando. **A senha e a chave secreta derivada não são transmitidas**. O AS usa o ID de usuário para verificar se há uma conta no banco de dados de autenticação, como um servidor do Active Directory. Em caso positivo, o AS gera a chave secreta usando o hash de senha armazenado no servidor de distribuição de chaves.
    - O AS usa a chave secreta para criptografar e enviar uma mensagem com a chave de sessão TGS do cliente. É uma chave secreta usada para criptografar comunicações com o servidor de concessão de ticket (TGS), que o servidor de autenticação já conhece. O AS também envia outra mensagem, com um ticket de concessão de ticket (TGT), que é criptografada com a chave secreta do TGS. O ticket de concessão de ticket tem informações como o ID do cliente, o período de validade do ticket e a chave de sessão do serviço de concessão de ticket do cliente. 

## 5.1 *Tickets*
- Uma token para comprovar a identidade, usados para autenticação em serviços protegidos pelo Kerberos, ou que estão no domínio do Kerberos. Com os tickets, os usuários *fazem autenticação em serviços sem usar nome de usuário e senha para cada serviço*. O ticket expira após algum tempo, mas tem provisões para renovação automática transparente.   

# 6. *TACACS*+
- *Terminal Access Controller Access-Control System Plus*; Usado principalmente para administração, autenticação, autorização e contabilidade de dispositivos, em oposição ao *RADIUS*, que é usado principalmente para acesso à rede AAA. Usado principalmente como um sistema de autenticação para dispositivos de infraestrutura de rede.  

# 7. *SSO*
- *Single Sing-On*, um logon único que da acesso a vários serviços e aplicativos com uma única autenticação. 
- Como não é necessário fazer a autenticação em cada serviço, não é preciso ter nomes de usuário e senhas diferentes para acessar vários aplicativos e serviços. - O SSO é realizado com a autenticação em um servidor central que fornece um cookie/token que dá acesso a aplicativos configurados para usar SSO.   

# 8. ***Authorization***
- Determina ao que uma conta possui acesso. O usuário pode se autenticar em um sistema apresentando credenciais válidas, mas se o nome de usuário informado não estiver autorizado a acessar o sistema, o acesso será negado.
- Um padrão aberto conhecido para autorização e delegação de acesso é o **OAuth** usado por empresas como Google, Facebook e Microsoft. 

## 8.1 ***OAuth***
- *Open Authorization*, é um padrão aberto para os usuários concederem suas informações a sites e aplicativos terceirizados sem compartilhar credenciais, sendo uma forma de delegação de acesso, porque o acesso à conta do usuário é delegado a entidades externas.
- Para isso, o usuário deve confirmar que concorda em dar acesso a certas informações da conta para a entidade. ***Em geral, a solicitação mostra quais informações e acessos são solicitados***.   
    - **Após a confirmação, o provedor de identidade emite um token para entidade externa, que dá acesso às informações do usuário**. A entidade pode usar o token para acessar dados ou serviços oferecidos pelo provedor de identidade em nome do usuário.
    - **O OAuth é muito usado para que aplicativos terceirizados acessem as APIs de grandes empresas** da Internet, como Google, Microsoft e Facebook.
- O site que usa o *OAuth* pede permissão para usar o serviço, por exemplo, seu e-mail. Ele envia uma solicitação de OAuth ao seu provedor de e-mail. Quando você aprova a solicitação, o provedor emite um token de acesso ao site, que então pode acessar sua conta de e-mail. ***O token só permite acessar o e-mail, e não outros serviços da sua conta***.  
- ***As permissões do OAuth podem ser usadas em ataques de phishing para acessar contas sem comprometer as credenciais.*** Para isso, o invasor envia e-mails de phishing que parecem ser solicitações reais de autorização do OAuth, pedindo ao usuário permissão para acessar alguns aspectos da conta pelo OAuth. Quando o usuário permite acesso, o invasor pode acessar a conta com o token de autorização do OAuth.
    - *https://www.theverge.com/2017/5/3/15534768/google-docs-phishing-attack-share-this-document-with-you-spam*
- ***O OAuth é um sistema de autorização, e o OpenID é um sistema de autenticação.*** Embora sejam usados juntos, o OpenID Connect é uma camada de autenticação criada sobre o OAuth 2.0 para melhorar o OpenID e a integração com autorizações do OAuth.  

## 8.2 ACL
- *Access Control List* é um modo de definir permissões/autorização para objetos e um dos usos mais comuns é de permissão de sistemas de arquivos.
    - Um sistema de arquivos tem uma ACL, ***que é uma tabela ou um banco de dados com uma lista de entradas que especifica os direitos de acesso de indivíduos ou grupos a vários objetos***, como pastas, arquivos ou programas. Essas permissões de acesso individual por objeto são chamadas entradas de controle de acesso e compõem a ACL.
    - **Também podem restringir o acesso externo** a sistemas e limitar o tráfego de saída para impor políticas ou evitar transferências de dados não autorizadas. 
