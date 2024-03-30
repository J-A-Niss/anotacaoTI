# BIOS - Basic Input Output Services (serviço básico de entrada e saida)      

- Software que ajuda a inicializar o hardware do computador e faz o sistema operacional funcionar. Diferente de um programa, a BIOS ta salva num chip na placa mãe chamado de *read-only memory chip*, ou chip ROM. Quando o sistema é carregado os drivers são carregados direto do disco rígido

- Atualmente existe uma outra parte da BIOS chamade de UEFI, Unified Extensible Firmware Interface, ou interface de firmware unificada extensível.   

## UEFI    

- Possui a mesma função de inicializar o computador como a BIOS, mas é mais moderno e tem melhor compatibilidade com componentes mais novos e a maioria dos hardware atual ja possuem UEFI embutido.   

## POST - Power On Self Testing (autoteste de inicialização)    

- Teste feito pela BIOS durante o boot para descobrir qual hardware esta no computador e acontece **antes** da BIOS inicializar qualquer hardware ou carregue qualquer driver essencial.    

- Se houver algum problema não há como exibi-lo na tela, porque nesse ponto a BIOS ainda não inicializou o driver de vídeo então nesse caso o computador emite uma serie de bipes que pode ajudar a identificar um possível problema.    

- Um unico bipe indica que tudo foi iniciado sem problemas, mais de um bipe pode indicar um erro de POST; diferentes marcas de placa-mãe possuem diferentes "códigos" de bipe então consultar o manual da placa é recomendado. ***Porém, nem todas placas mãe possuem alto-falante embutido, então pode ser que ocorra o boot sem um bipe***     

## Bateria CMOS    

- Guarda informações básicas como data, hora e preferencia de inicialização, podendo ser alterado entrando no menu de configuração da BIOS ou do CMOS.   

## MENU BIOS   

- Menu que disponibiliza as configurações da BIOS, diferentes computadores possuem diferentes modos de acesso, mas normalmente é uma tela antes do boot do computador indicando uma tecla a ser pressionada para abrir o menu. Desse menu pode-se alterar as configuração da BIOS.

## Reimaging **(Restauração)**    

- Restuara os dados do sistema, e é um processo que limpa e reinstala o sistema operacional e normalmente é feito com algum programa armazenado externamente, como num CD  Pendrive ou até mesmo um servidor acessível pela rede. Para acessar esses programas se usa a BIOS para falar ao computador realizar o boot a partir do dispositivo externo.

## Drivers     

- Programa usado por dispositivos externos para mandar instruções que o processador precisa para compreender os comandos enviados