# Programas E Processos
## Programas
- Aplicações que o seu computador executa, como por exemplo um web browser.   

## Processos
- São programas sendo executados. É possível que se tenham varios processos no mesmo programa, como por exemplo varias abas no navegador e esses processos demandam recursos dos componentes físicos. Quando se inicia um processo, este processo recebe um ID. Processos podem ser iniciados pelo usuário ou correr no ***plano de fundo, esses as vezes são chamados de "Processos Daemon"***.
    #### Processos de Fundo/Daemon
    - Iniciados no plano de fundo, na qual o usuário não necessariamente interage.   

- Processos iniciam de modo diferente, por exemplo, ***no Windows*** o primeiro processo de modo de usuário não-kernel que é iniciado é o ***Subsistema de gerenciamento de sessão, ou smss.exe*** e é reponsável por organizar algumas coisas para que o OS funcione e começa o processo de login chamado de *winlogon.exe* juntamente com o *Subsistema de tempo de execução cliente/servidor chamado csrss.exe* ou *Client/Server Runtime Subsystem*, este que é responsável pela interação entre a GUI e a linda de comando.
- No Windows todo processo criado precisa de um pai, da qual o processo herda características como variáveis e configurações, que é coletivamente chamado de ***Ambiente***. Isso traz ao processo um bom começo, mas após isso o processo filho/criado funciona praticamente sozinho. Diferente do Linux, no Windows, os processos operam independentemente de seus pais. Processos podem ser encerrados clicando no X no canto superior direito ou com o comando [taskill](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/taskkill) no prompt. O comando [Get-Process](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-process?view=powershell-5.1) te da informações detalhadas sobre os processos atuais.   

### [Sinais](https://learn.microsoft.com/en-us/cpp/c-runtime-library/reference/signal?view=msvc-170)
- Usado para informar um processo que algo aconteceu, como por exemplo, para encerra-lo. Podem ser gerados com combinações de teclas do teclado e com outros processos ou software e um dos mais comuns é o **SIGINT** que significa *Signal Interrupt* e muitos processos podem ser interrompidos por um sinal enviado com *CTRL-C*   

#### [Explorador de Processos](https://learn.microsoft.com/en-us/sysinternals/downloads/process-explorer)
- Ferramenta criada pela Microsoft para auxiliar suporte técnico, admins e usuários para visualizar e gerenciar processos   

#### Gerenciador de Recursos
- Ferramenta nativa do windows usada para gerenciar recursos do sistema pela GUI. Da pra adquirir essas informações pelo powershell com o comando ['*Get-Process*'](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-process?view=powershell-5.1#outputs); este comando exibe todas informações, podendo tambem ser mais especificado com comandos mais específicos: '*Get-Process | Sort CPU -descending | Select -first 3 -Property ID,ProcessName,CPU*'

## Processos no Linux
- Em um ambiente Linux os processos tem um relacionamento parecido mas diferente, basicamente todo processo vem de outro processo. Quando se liga o computador Linux, o kernel inicia o *init* que tem um PID (process ID) de 1 e o init começa outros processos necessários para o funcionamento da máquina e geralmente quando o processo conclui a tarefa. O comando "*ps -x*" ta da informações dos atuais processos ocorrendo no Linux. O comando "*[ps](https://man7.org/linux/man-pages/man1/ps.1.html) -ef*" ***te da toda informação de todos processos, até mesmo os iniciados por outros usuários.***   

### Gerenciando Processos
- Processos podem ser gerenciados por comandos:
    - kill 'PID' | encerra o processo com um **SIGTERM** ou *Sinal de Terminação*, sem nenhuma flag pode causar corrupção de dados.
    - kill -KILL 'PID' | **REALMENTE** encerra o processo. *Com fogo e requintes de crueldade*. Se o *kill* pode causar dano, o **kill -KILL** *definitivamente* vai causar danos.
    - kill -TSTP 'PID' | Pausa o processo
    - kill -CONT 'PID' | retoma o processo 

#### [Gerenc Recursos](https://en.wikipedia.org/wiki/Load_(computing))
- O comando 'top' mostra os principais processos que mais estão usando recursos na máquina, tambem mostra um panorama de todas tarefas em execução ou inativas, tambem mostrando uso de CPU, Memoria *etc.* Outro comando importante é o '*uptime*' que mostra hora, tempo atual de uso, quantos usuários estão logados e a média de carga que mostra uma média na carga da CPU em intervalos de 1, 5 e 15 minutos. Outo comando importante é o '*lsof*' que lista arquivos abertos e quais processos os estão usando.   

## Registros
- Usado pelo OS para marcar eventos. Eventos podendo ser literalmente qualquer coisa que acontece ao sistema, de desligamentos à atualizações. Esses registros ocupam espaço por serem informação e portanto existe um sistema de rotação desses logs que deleta os mais antigos para fazer espaço para os mais novos, por meio do log rotate.
#### Visualizador Windows
- Usado pelo Windows para marcar os eventos que ocorrem.   

#### Visualizador Linux
- O Linux não possui a mesma GUI, os logs são registrados no */var/log*, com o comando
```
ls /var/log | a lista os logs dos eventos fica gravado aqui
```