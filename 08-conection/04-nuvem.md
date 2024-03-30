# [A Nuvem](https://en.wikipedia.org/wiki/Cloud_computing)   

- Conceito tecnicamente intangível, mas é definido por: ***Abordagem tecnológica na qual recursos computacionais são alocados de modo compartilhável com intuito que varios usuários usem o que precisam, quando precisarem.*** Dentro da nuvem, um de seus maiores conceitos é a **virtualização do hardware**, criando a possibilidade de separa a maquina física da máquina lógica.   

## [Virt. do Hardware](https://en.wikipedia.org/wiki/Hardware_virtualization)   

- Uma máquina física denominada *Host* executa varias instâncias denominadas *Guests*. Plataformas de virtualização usam algo chamado de *hypervisor*. [**Hypervisor**](https://en.wikipedia.org/wiki/Hypervisor) é um software que execute e gerencia máquinas virtuais que tambem oferece aos Guests uma plataforma operacional virtual idêntica à do hardware físico. Com a virt. um unico computador pode agir como host de varias instâncias independentes, cada uma com seu proprio OS que roda de modo idêntico ao que se espera de rodar um OS num hardware propriamente dito.  

- Essencialmente a virtualização permite que voce divida recursos de máquinas do mesmo cluster; imaginando que um negócio precisa de um servidor para email com 8gb de RAM, um para dns com 8gb RAM, um para banco de dados que só estão disponíveis modelos com 32 gb de RAM e outra máquina para outro banco de dados tambem com 32 gb de RAM, seriam necessário 4 servidores com 80gb RAM, que não só não seriam totalmente usados como tratiram um custo desnecessário. Agora, com a nuvem pode se contratar um serviço ja com os servidores interconectados que podem hospedar servidores virtualizados para cada função necessária, um para email, DNS e bancos de dados, esses servidores físicos dividindo seus recursos entre si de modo que não haja desperdicio de recursos disponiveis.   

- ***Essencialmente a nuvem permite que voce terceirize esse aspecto à uma empresa especializada em manter servidores, pelo meio da contratação do servidor de modo remoto, ao invés de voce precisar fisicamente ter um disponível***   

- Neste exemplo foi usada uma ***nuvem publica***, um cluster de máquinas administrado por uma empresa; no caso de uma ***nuvem particular*** a unica diferença é que é propriedade, mantido e usado por uma unica empresa. Existe tambem ***nuvem híbrida*** na qual empresas podem manter material mais sensível numa parte particular, mas disponibilizar tambem uma parte ao publico.   

### X como um serviço   

- X podendo ser qualquer coisa, no caso abordado, seria a *Infraestrutura como serivço*, na qual voce não precisa necessariamente se preocupar em construir e manter sua propria rede ou servidores. **Pode tambem ser a plataforma e até mesmo o software**. Armazenamento tambem é uma alternativa muito popular sendo terceirizada à nuvem.