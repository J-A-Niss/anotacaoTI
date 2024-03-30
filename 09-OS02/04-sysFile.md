# Sistema de arquivos
- Usado para rastrear arquivos e seu armazenamento em disco e sem um sistema desses o OS não sabe com organizar arquivos. Existem varios, mas dois são considerados como o padrão, ***NFTS para Windows e o ext4 para o Linux***. Compatibilidade entre sistemas é mínimo então caso tenha uma unidade com um sistema incompatível, será necessário formatar a unidade. Felizmente existe o sistema [exFAT](https://learn.microsoft.com/en-US/windows/win32/fileio/exfat-specification) que suporta a leitura e gravação de dados dos 3 sistemas principais.

## [Disco](https://learn.microsoft.com/en-us/sysinternals/downloads/du)
### Windows
#### Partição
- Uma parte do disco, alocada para algum fim específico, como por exemplo, um OS diferente do principal. *Lembrando que uma partição formatada se torna um volume.* Outro componente é a tabela de partição (table) que informa o OS como o disco ta particionado, este por sua vez pode ser **MBR ou Registro Mestre de Inicialização e o GPT ou Tabela GUID**; estes esquemas decidem como estruturar a informação das partições.
    - **MBR** é o mais tradicional, sendo usado no Windows, só permite volumes de até 2TB e utiliza um conceito de partição primária, das quais, só permite 4 no disco, e caso precise de mais, é necessario faer uma extensão de uma das 4 partições. Considerado mais antiquado e está sendo substituido pelo GPT
    - **GPT** aceita limites maiores que 2TB, só possui um tipo de partição da qual não tem limite.   

### [NFTS](https://learn.microsoft.com/pt-br/windows/win32/fileio/master-file-table?redirectedfrom=MSDN)
-  NTFS é o formato de sistema de arquivos nativo do Windows. Então o NTFS armazena e representa os arquivos com os quais estamos trabalhando no sistema operacional. O NTFS usa algo chamado de "tabela mestra de arquivos", ou ***MFT***, para manter tudo em ordem.
- [Links Simbólicos](https://learn.microsoft.com/pt-br/windows/win32/fileio/creating-symbolic-links?redirectedfrom=MSDN)
- [Links Rígidos](https://learn.microsoft.com/pt-br/windows/win32/fileio/hard-links-and-junctions?redirectedfrom=MSDN)
#### Formatando e particionando um disco.
- Windows possui um programa de fabrica chamado de Utilitário de Gerenciamento de Disco. Este processo tambem pode ser feito por meio da [CLI, através do diskpart](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc766465(v=ws.10)?redirectedfrom=MSDN).
```
Diskpart                                    | acessar o modo de particionamento de disco pela CLI
list disk                                   | para listar os discos disponíveis
select disk X                               | para escolher o disco
clean                                       | remove toda e qualquer partição do disco
create partition primary                    | cria uma partição primaria no disco selecionado
active                                      | torna a particão selecionada em primária
format FS=NTFS label=my-thumb-drive quick   | format formata a partição, FS para file system, label para o nome e quick para tipo de formatação

```
[Para mais informações](https://support.microsoft.com/en-us/topic/default-cluster-size-for-ntfs-fat-and-exfat-9772e6f1-e31a-00d7-e18f-73169155af95)   

## Montar
- Signifca tornar algo acessível ao computador, como por exemplo, conectar um dispositivo USB.   

#### [Virtual Memory](https://en.wikipedia.org/wiki/Memory_paging#Windows_NT)
- O modo pela qual o OS providencia a memoria física disponível às aplicações que funcionam no computador; basicamente é feito por meio de mapeamento de endereços virtual-para-o-físico e isso facilita a vida do programa que precisa usar a memoria e não precisa se preocupar sobre quais partes da memoria está sendo usada por outros programas tambem não precisando rastrear onde os dados usados estão localizados na RAM.
- Isso tambem permite ao computador '*usar mais memoria do que foi instalado*' por meio de uma tecnica que consiste dedicar uma parte do HD para uma base de armazenamento de dados em blocos, chamados páginas (não são paginas de browser) e quando uma pagina não esta sendo usada é desalocada, ou seja, copiada da memoria para o disco rigido. ***Basicamente põe o que não ta sendo usado muito frequentemente no disco, porque RAM é muito demandada*** no Windows isso é lidado com o *Gerenciador de Memoria*  

### Linux
- Existem comandos diferentes que podemos usar, um que suporta tanto MBR quanto GPT é o Parted, este possuindo dois modos:
    1. Interativo, este lança um programa específico para interagir com a ferramente
    2. CLI, neste voce só executa comandos, ainda no shell   

```
sudo parted -l                  | lista os discos conectados no computador
sudo parted /dev/sdb            | inicia a ferramente parted
print                           | mostra o atual local na CLI
mklabel gpt                     | cria uma label
mkpart                          | cria uma partição
mkfs                            | formata a partição
sudo mount /dev/sdb /my_usb/    | monta o dispositivo, nesse caso, o my_usb. este comando não monta a unidade de modo permanente
umont /dev/sdb                  | desmonta o dispositvo, no caso, é importante desmontar a unidade antes de desconecta-la fisicamente
cat /etc/fstab                  | abre a unidade de montagem automatica
sudo blkid                      | abre as UUID, ou Universally Unique ID.
mkswap                          | determina nova partição para ser usada como espaço de swap
swapon                          | ativa o swap
du-h                            | disk usage, mostra o uso de disco
```
- o comando ***mkpart*** necesista das seguintes informações:
    1. o tipo da partição
    2. o tipo de arquivo
    3. inicio do disco
    4. final do disco
- de modo que fica: *mkpart primery ext4 1MiB 6GiB*   

#### Montando
- o comando não *mount* não monta a unidade permanente e automaticamente, necessitando modificar um arquivo chamado [*/etc/fstab*](https://en.wikipedia.org/wiki/Fstab)  

### [Swap Space](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/installation_guide/s2-diskpartrecommend-ppc#id4394007)
- Equivalente do Linux ao Virtual Memory, usado para a mesma coisa.  

### inode
- Funciona que nem o MFT do windows; armazenando os metadados dos arquivos, basicamente tudo sobre um arquivo, exceto o nome e os dados dele.

##### [Desfragmentação Linux](https://www.howtogeek.com/115229/htg-explains-why-linux-doesnt-need-defragmenting/)
- Basicamente não é lá muito necessário

##### [fsck](https://en.wikipedia.org/wiki/Fsck)
- file system check; tambem não é muito recomendado