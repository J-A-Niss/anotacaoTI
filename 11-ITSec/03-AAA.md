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
- Utiliza características da fisiológicas do indivíduo para o identificar.

# 2. **Authorization**
- Os recursos que uma identidade te da, por exemplo, autorização de administrador de sistemas. Usa-se o termo `auth-z`

# Para mais informações: *https://colab.research.google.com/drive/1VXLefLLdR5m24_X85E83KlRHeoHVpouo#scrollTo=PaWT3-hxwsuz*