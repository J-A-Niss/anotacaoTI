# Guia do Windows Defender
# 1. **Microsoft 365 Defender**
## 1.1 Serviços do Microsoft 365 Defender
- O Defender oferece segurança com um pacote integrado de ferramentas.
    - *Ele tem ferramentas para evitar ataques, detectar ameaças, investigar violações de segurança e coordenar estratégias de resposta eficazes. O portal do Defender também oferece um centro de ação para monitorar incidentes e alertas, bem como para análise e busca de ameaças.*
- ***Defender* para endpoint**: protege os endpoints da rede, incluindo servidores, estações de trabalho, dispositivos móveis e IoT. Oferece proteções preventivas, detecção de violações, análises automatizadas e serviços de resposta a ameaças.
- **Gerenciamento de vulnerabilidades do Defender**: protege recursos, incluindo hardware, software, licenças, redes e dados. Fornece inventário de recursos, descoberta de vulnerabilidades, avaliação de configuração, priorização com base em riscos e ferramentas de correção.
- ***Defender* para Office 365**: protege o Microsoft 365 (antigo Office 365), incluindo o Exchange, o Outlook, arquivos e anexos. Protege contra ameaças maliciosas de mensagens de e-mail, links (URLs) e ferramentas de colaboração.
- ***Defender* para identidade**: protege a identidade e as credenciais do usuário. Detecta, identifica e investiga ameaças avançadas, identidades comprometidas e ações maliciosas realizadas por ameaças internas ou com identidades de usuários roubadas.
- **Proteção de identidade do Azure Active Directory**: automatiza a detecção e a resolução de riscos de identidade para proteger identidades baseadas em nuvem no Azure.
- ***Defender* para aplicativos de nuvem**: protege aplicativos de nuvem ao fornecer pesquisas de visibilidade aprofundadas, controles robustos de dados e proteção avançada contra ameaças.

### 1.1.1 Como usar o Microsoft 365 Defender
- Pode se usar o Defender para monitoraração e segurança de TI.
    - Você pode personalizar a página inicial do Portal do Defender por funções de trabalho. É possível selecionar vários cards de segurança para exibição na página inicial da função. Por exemplo, você pode verificar cards para monitoramento:
        - **Identidades**: monitore identidades de usuários em busca de comportamentos suspeitos ou arriscados.
        - **Dados**: acompanhe atividades de usuário que representam um risco à segurança de dados.
        - **Dispositivos**: verifique alertas, atividades de violação e outras ameaças em dispositivos conectados à rede da organização.
        - **Aplicativos**: observe como os aplicativos da nuvem são usados na organização.
        - **Incidentes**: revise ataques com dados abrangentes de incidentes.
        - **Alertas**: visualize alertas compilados do pacote do Microsoft 365.
        - **Caça** avançada: verifique se há arquivos suspeitos, malware e atividades arriscadas.
        - **Análise** de ameaças: visualize informações sobre ameaças atuais à segurança cibernética.
        - **Pontuação** segura: tenha uma pontuação calculada para sua configuração de segurança e recomendações sobre como melhorar sua pontuação.
        - **Central** de aprendizado: acesse facilmente os tutoriais de segurança do Microsoft 365 e outros materiais de aprendizado.
        - **Relatórios**: acesse informações para proteger melhor a organização.
- O Microsoft 365 Defender agrega e organiza esses dados de monitoramento para fornecer detalhes sobre onde os ataques começaram, quais táticas maliciosas foram usadas, o escopo dos ataques e outras informações relacionadas a incidentes.

## 1.2 Microsoft 365 Defender em ação
- Para cada tipo de ataque malicioso, é apresentada uma possível resposta do Microsoft 365 Defender, que ilustra como o pacote de segurança pode agir:

### 1.2.1 ***Uma tentativa de phishing entra por e-mail***:
- Um funcionário de uma organização recebe um e-mail de uma empresa que parece ser legítima, como um banco. O e-mail pode afirmar que há um problema com a conta do funcionário e que ele deve clicar em um determinado link para resolver o problema. No entanto, o e-mail de phishing contém um link para um site malicioso que um invasor disfarçou para parecer um banco de verdade. Se o funcionário clicar no link para visualizar o site, o site solicitará que o usuário digite as credenciais da conta ou outras informações sensíveis. Essas informações são transmitidas para o invasor. **O Microsoft Defender** para Office 365 monitora o Exchange e o Outlook para detectar o golpe de phishing enviado por e-mail. O funcionário e a equipe de suporte de TI são alertados sobre essa tentativa de ataque de phishing.   

### 1.2.2 ***Malwares inseridos por mídias sociais***: 
- Um funcionário clica em um link atraente postado no aplicativo de mídia social favorito dele. O link aciona o download automático de um arquivo de malware para o laptop do funcionário.**O Microsoft Defender** para endpoint monitora assinaturas de malware suspeito no laptop do funcionário. Ao detectar o malware, o Defender para endpoint alerta o funcionário e a equipe de suporte de TI da organização sobre o malware e divulga o local do endpoint.   

### 1.2.3 ***Um invasor intercepta as credenciais de login de trabalho de um funcionário***: 
- Um funcionário acessa a conta de trabalho usando o laptop e um ponto de acesso Wi-Fi aberto de um café movimentado. Um invasor está no mesmo café para interceptar e coletar informações desprotegidas que fluem pelo ponto de acesso Wi-Fi aberto. O invasor consegue as credenciais da conta de usuário do funcionário e as usa para invadir a conta de trabalho do funcionário. O criminoso começa um ataque mal-intencionado na rede do empregador. **O Microsoft Defender** para identidade pode detectar a mudança repentina de atividade na conta de usuário do funcionário. O Defender para identidade alerta o funcionário e a equipe de suporte de TI sobre a identidade comprometida do usuário.   

### 1.2.4 ***Um vírus entra em uma unidade de nuvem por um upload de arquivo***: 
- Um funcionário faz sem saber o upload de um arquivo infectado com um vírus para a unidade de armazenamento em nuvem do trabalho. Quando o funcionário abre o arquivo da unidade de nuvem, o vírus é ativado e começa a alterar as configurações de segurança dos outros arquivos na unidade de nuvem dos funcionários. **O Microsoft Defender** para aplicativos de nuvem detecta o padrão incomum de atividade e alerta o funcionário e a equipe de suporte de TI sobre a atividade suspeita na conta da nuvem.   

## 1.3 Controle de conta de usuário (*UAC*)
- O UAC permite que os administradores criem contas de usuário padrão com direitos e privilégios de acesso limitados para os usuários finais. Essa configuração pode impedir que os usuários instalem programas não autorizados, alterem as configurações do sistema, adulterem firewalls e muito mais. 
    - **Para executar essas tarefas, as credenciais de administrador devem ser fornecidas**. 
    - **Para controles menos restritivos, o UAC oferece a opção de conceder privilégios administrativos locais** aos usuários finais para atividades aprovadas que exigem privilégios de administrador. 
    - **Para controles mais restritivos, o UAC pode exigir que as credenciais de administrador globais** sejam inseridas em cada alteração administrativa que o usuário tentar fazer.
