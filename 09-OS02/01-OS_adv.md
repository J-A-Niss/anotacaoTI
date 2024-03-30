# OS Avançado
   
## Linux
- O interpretador da ***Command Line Interface ou CLI*** do Linux é chamada de *shell* e a lingua usada para interação é o *Bash*. A ***Graphical User Interface ou GUI*** do Linux é parecida com a do windows, de modo que navegar nas duas é muito parecido.
   
#### [Documentação Powershell](https://learn.microsoft.com/pt-br/powershell/)
   
### PowerShell
- CLI do windows. Não compreende espaços, precisando usar outros carácteres com '' ou `
```
    - ls                    - lista os diretórios
    - ls C:\                - mesma coisa mas em um diretorio especifico
    - Get-Help ls           - mostra os possiveis parametros do ls
    - Get-Help ls -Full     - mostra todos parametros e oque fazem
    - ls -Force             - mostra os arquivos ocultos
    - pwd                   - 'print working directory' indica qual diretório voce esta
    - cd                    - 'change directory' usado para mudar de diretório para o diretório desejado, podendo ser um caminho relativo ou absoluto
    - ~                     - usado para referenciar o diretório principal 'home'
    - mkdir                 - 'make directory' usado para criar diretório
    - history               - demonstra os comandos usados, as setas do teclado tambem preenchem essa função. ctrl+R tambem desempenha essa função
    - clear                 - limpa a tela
    - cp                    - copia; tambem precisa do arquivo a ser copiado e o local para copiar "cp folder01 c:\Users\user\desktop\"
    - *                     - usado como coringa para 'tudo' que for de um determinado parametro, como por exemplo *.jpg
    - cp -Recurse           - copia o conteudo de um diretório junto ao diretório em si "cp folder01 c:\Users\user\desktop\ -Recurse"
    - -Verbose              - usado para trazer mais explicações ao comando, quando o comando não tem nenhum output na tela
    - mv                    - 'move' usado para mudar arquivo de lugar e renomear documento 'mv .\documento1.txt documento2.txt'
    - rm ou remove          - remove um arquivo, NÃO MANDA PRO LIXO, REMOVE PERMANENTEMENTE
    - -Recurse              - bandeira usada para afetar todos arquivos dentro de um diretório
    - cat                   - 'concatenate' visualiza o conteudo de um arquivo
    - more                  - mostra todo conteudo do arquivo com um outro programa, dentro do shell. Enter avança uma linha por vez, espaço uma página e a tecla q encerra
    - -Head                 - mostra só o começo do arquivo
    - -Tail                 - mostra o final do arquivo
    - Get-Alias 'comando'   - mostra qual o comando completo, ao invés do pseudonimo
    - sls ou Select-String  - encontra palavras ou outras sequencias de caracteres e arquivos
    - -Filter               - filtra resultados com base em um parametro, por exemplo '-Filter *.exe' para arquivos executáveis
    - Get-LocalUser         - Lista usuários da máquina
    - Get-LocalGroups       - Lista grupos da máquina
    - Get-LocalGroupMember  - Lista os membros de um grupo, como por exemplo: 'Get-LocalGroupMember Administradores'
    - net                   - usado para criar usuários e alterar senhas; 'net user "nome" * /add' ou 'net user "nome" * /del' para deletar
    - /?                    - traz mais informação sobre um comando usado 

```

#### [Mais sobre Powershell](https://github.com/PowerShell/PowerShell/blob/master/docs/learning-powershell/README.md)
      
#### Caminhos
- Pode ser relativo ou absoluto; relativo do ponto do diretório que se encontra, absoluto do ponto de vista que inclui TODO caminho, desde o drive até o diretório desejado:
```
absoluto - C:\Users\User\Desktop\Frontend
relativo - \Frontend
```
   
### [Powershell](https://www.powershellgallery.com/)
- CLI do Linux. Tambem não compreende espaços, use '' ou \
```
    - ls                    - lista diretórios, como por exemplo "ls ~\Desktop"
    - ls --help             - lista as opções
    - man ls                - 'manual', usado para mostrar as paginais de modo manual, chamadas de manpages no linux
    - ls -l                 - significa long, e traz informações detalhadas sobre os arquivos
    - -a                    - 'all', mostra todas opções, incluso os arquivos ocultos
    - pwd                   - 'print working directory' indica qual diretório voce esta
    - cd                    - 'change directory' usado para mudar de diretório para o diretório desejado, podendo ser um *caminho relativo ou absoluto*
    - ~                     - usado para referenciar o diretório principal (home)
    - mkdir                 - 'make directory' usado para criar diretório
    - history               - demonstra os comandos usados, as setas do teclado tambem preenchem essa função. ctrl+R tambem desempenha essa função
    - clear                 - limpa a tela
    - -r                    - mesma função do -Recurse no powershell
    - mv                    - 'move' usado para mudar arquivo de lugar e renomear documento 'mv .\documento1.txt documento2.txt'
    - cat                   - 'concatenate' visualiza o conteudo de um arquivo
    - less                  - ironicamente funciona que nem o more no windows, mostrando todo conteudo do documento por meio de um outro programa dentro do shell
    - /palavra              - dentro do comando 'less' isso pesquisa uma palavra específica
    - q                     - dentro do comando 'less' sai do modo de analise de conteudo
    - head                  - idem ao windows
    - tail                  - idem ao windows
    - grep                  - procura palavra dentro de arquivo
    - echo                  - funciona como 'Write-Output' basicamente mostra o que ta sendo escrito com o teclado na tela
    - $null                 - literalmente nulo|nada
    - Get-Help about_redirection - traz mais informações sobre os comandos
    - >>                    - redirecionador de acréscimo
    - |                     - canaliza um comando a saída de um comando para outro
    - sudo ou superuserdo   - usa privilégio Root no linux para fazer meio que qualquer coisa
    - passwrd -e 'user'     - força a expiração da senha do usuário ao logar na conta, fazendo com que o usuário precise troca-la
    - sudo useradd 'nome'   - adiciona novo usuário 
    - sudo userdel 'nome'   - remove o usuário
    - dpkg                  - debian package
    - -i                    - install, flag usada no final, por exemplo: sudo dpkg -i 'pactoe'.deb
    - -r                    - remove, flag que remove um pacote, por exemplo: sudo dpkg -r 'pacote'
    - 7z e 'arquivo.xxx'    - extrai o arquivo por meio do 7zip

```  

- Em Linux o primeiro usuário é o considerado Root, ou 'superuser', esse é o que possui todos privilégios da máquina, parecido com admin. 

### [Vim](https://www.vim.org/)   

## Users
- Usuários se separam em dois:
    1. *Normal ou usuário*; este possui restrições quanto ao uso da máquina
    2. *Admins*; este possui acesso irrestrio quanto ao uso da máquina    

### Dominio Windows
- Rede de computadores, usuários e arquivos adicionados à um banco de dados central. Admins pode ver essas contas e computadores de qualquer máquina do domínio.   

### Permissões
#### Windows
- No Windows, permissões para arquivos e diretórios são concedidas com [ACLs, ou Access Control Lists](https://learn.microsoft.com/pt-br/windows/win32/secauthz/access-control-lists?redirectedfrom=MSDN) e DACLs, Descretionary Access Control Lists. SACLs ou System Access Control Logs tambem são usados para dar permissões, na qual fica registrado no log de eventos quando um acesso é feito. **Basicamente ACLs decidem quem pode fazer "o oque"**   
- [Permissões especiais](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732880(v=ws.11)?redirectedfrom=MSDN)

#### Linux
- Tem 3 permissôes:
    1. **Ler** permite que veja o conteudo do arquivo/pasta            | r
    2. **Escrever** permite escrever/reescrever conteudo de arq/pasta  | w
    3. **Executar** permite executar conteudo de arq/pasta             | x
- Uma  **SetUID**, permite executar arquivos com permissão root        | s
- SetGID permite que o grupo execute o arquivo                         | tty
- Sticky Bit permite que possam alterar arq/pasta mas não possa deletar nada    

## Gerar Imagen
- Signifca formatar uma máquina copiando de outra máquina. Isso pode ser feito de varios modos. Um dos modos é clonagem disco, que essencialmente copia um disco em outro e um dos softwares mais populares para isso é o clonezilla, software de codigo aberto que pode ser usado para fazer backup e restaurar uma ou varias máquinas, outra popular é a *Symantec Ghost*. Diferentes ferramentes usam diferentes métodos, um desses é [clonagem disco-a-disco](https://en.wikipedia.org/wiki/Comparison_of_disk_cloning_software), onde se conecta um HD externo à máquina que quiser clonar.
- Em Linux, uma ferramenta é o [*dd*, comando usado para copiar arquivos](https://man7.org/linux/man-pages/man1/dd.1.html).