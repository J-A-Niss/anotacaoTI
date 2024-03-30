# Pacotes   

## Windows
- Modo pela qual software é transmitido para usuários; normalmente por meio de um ***arquivo.exe (executável) que contém instruções para o computador executar quando é aberto***. São criados de acordo com o [Executável Portátil ou formato PE](https://en.wikipedia.org/wiki/Portable_Executable). Arquivos .exe não só contem instruções, mas contem tambem quaisquer outros arquivos necessários para que o .exe execute do modo correto, fotos, comandos, operações e talvez um ***.msi ou Microsoft Install Package, usado para guiar o Windows Installer, que é usado na instalação, remoção e manutenção de programas do windows***. Além do wizard guiando o usuário na interface, o msi cria instruções   

### Arquivo compactado
- Composto de varios arquivos compactados e comprimidos em um unico; e arquivos compactados são o cerne/fonte de software comprimidos em arquivo.

## Linux
- Existem diferentes distribuições e cada uma pode usar um tipo diferente de pacote. **O usado pelo Ubuntu é o debian, ou .deb**. 7zip tambem está disponível ao Linux através do 'p7zip-full'
- [tar](http://www.linfo.org/tar.html) - usado para extrair arquivos no Linux, como o 7zip
- apt ou Advanced Package Tool - ***gerenciador de pacote do linux*** 

### Gerenciadores de pacotes
- Para auxiliar com pacotes de dependencias, o Linux possui gerenciadores de pacotes, cujo proposito é lidar com essas dependencias do modo mais rapido, automático e fácil possível.

## Dependencias
- Ocorre quando um software necessita de outros para funcionar direito por exemplo: *um jooj dependendo de um motor de física para fazer calculações e uma biblioteca de renderização para exibir os gráficos na tela.* Nesse caso uma ***biblioteca é um modo de empacotar varios códigos uteis que alguem escreveu*** e no windows essas bibliotecas são chamadas de [biblioteca de vínculo dinâmico ou DLL](https://en.wikipedia.org/wiki/Dynamic-link_library). A vantagem é que uma DLL pode ser usada por varios programas diferentes. [Apesar, ainda sim existe a possibilidade de ocorrerm problemas com DLL](https://en.wikipedia.org/wiki/DLL_Hell).
### [SxS - Side by side assembly](https://learn.microsoft.com/en-us/previous-versions//aa376307(v=vs.85)?redirectedfrom=MSDN)
- São grupos de recursos providenciados à aplicações juntos.