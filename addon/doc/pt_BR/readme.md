# Monitor de Recursos (Resource Monitor) #

* Autores: Alex Hall, Joseph Lee, Kefas Lungu, Beqa Gozalishvili, Tuukka
  Ojala, Ethin Probst e outros colaboradores do NVDA

Este complemento fornece informações sobre carga da CPU, uso de memória e
outras informações de uso de recursos.

# Atalhos

Todos os comandos suportam o modo de fala sob demanda.

* NVDA+Shift+E: apresenta uso da ram (memória), carga média do processador,
  e informações de bateria caso disponível.
* NVDA+Shift+1: apresenta a carga média do processador e caso se tratem de
  CPUs multinúcleo (multicore) mostra a carga de cada núcleo.
* NVDA+Shift+2/5: apresenta espaço usado e total das memórias ram física e
  virtual.
* NVDA+Shift+3: apresenta espaço usado e o total das unidades fixas e
  removíveis.
* NVDA+Shift+4: apresenta porcentagem da bateria, status de carga, tempo
  restante (se não estiver carregando) e alerta caso a bateria esteja baixa
  ou crítica.
* NVDA+Shift+6: apresenta a arquitetura da CPU e os números da versão do
  Windows e do service pack.
* NVDA+Shift+7: apresenta o tempo de atividade do sistema (tempo desde a
  inicialização).
* NVDA+Shift+8: apresenta informações sobre a conexão sem fio, nome e
  intensidade do ssid ou nenhum ssid, se não houver nenhum disponível.

Você pode alterar essas teclas de atalho por meio da caixa de diálogo de
gestos de entrada.

## Notas de uso

Este complemento não substitui o gerenciador de tarefas e outros programas
de informações de sistema para Windows. Note também o seguinte:

* As informações de recursos não podem ser copiadas para a área de
  transferência se o complemento for executado em telas seguras.
* O uso da CPU é fornecido para processadores lógicos, não para núcleos
  físicos. Isso é perceptível nos processadores que usam Hyper-Threading, em
  que o número de CPUs é o dobro do número de núcleos da CPU. Em alguns
  computadores mais novos, nem todos os núcleos da CPU terão o
  hyper-threading ativado.
* Se houver atividade intença de disco, como ao copiar arquivos grandes,
  pode haver lentidão ao obter informações de uso do disco.
* Ao anunciar informações sobre a arquitetura do processador, “x86” e
  “AMD64” referem-se aos processadores Intel e AMD de 32 e 64 bits (x64),
  respectivamente.
* Esse complemento requer o Windows 10 22H2 (2022 Update/build 19045) ou
  posterior.
* Não há suporte para a instalação do complemento no Windows 10/11 LTSC.

## Version 25.07

* Made the add-on code more robust with help from Pyright (a Python static
  type checker).

## Version 25.06

* Improved connection status announcement when connecting to wireless
  networks (@danstiv).

## Version 25.02

* Restored limited support for Windows 8.1.
* Improved accuracy of used and total memory information announcement
  (@danstiv).
* NVDA will no longer appear to freeze briefly when performing memory usage
  command (NVDA+Shift+2/5) the first time after starting NVDA.
* Windows Insider Preview releases are no longer reported as "Windows
  Insider".

## Versão 24.08

* É necessário o NVDA 2024.2 ou posterior. Isso permite que a dependência do
  psutil seja removida do complemento, pois o NVDA o inclui.
* Atualizada a dependência do psutil para a versão incluída no NVDA 2024.2
  (6.0.0).
* Ruff substitui Flake8 como codificador.

## Versão 24.05

* Requer NVDA 2024.1 ou posteriores.
* O NVDA reconhecerá redes sem fio com métodos de autenticação WPA3, como a
  autenticação simultânea de iguais (SAE).

## Versão 24.04

* Atualização da dependência do psutil para a versão 5.9.8.
* Foi adicionado suporte ao modo de fala sob demanda para que as informações
  sobre recursos possam ser anunciadas nesse modo.

## Versão 23.11

* Rebaixamento da dependência do psutil para a versão 5.9.4 devido a
  problemas com anúncios de uso de memória.

## Versão 23.10

* Atualização da dependência do psutil para a versão 5.9.5.

## Versão 23.09

* O NVDA não registrará mais mensagens de erro de inicialização nos sistemas
  Windows Server quando os módulos de capacidade sem fio não estiverem
  disponíveis.

## Versão 23.06

* Foi corrigida a situação em que o resourceMonitor não funcionava
  corretamente devido à indisponibilidade de adaptadores sem fio.

## Versão 23.05.1

o wlanReporter NVDA-addon agora faz parte do resourceMonitor!

* A maneira antiga de verificar as conexões sem fio foi substituída pela API
  do Windows do wlanReporter: https://github.com/kvark128/WlanReporter/ .

	* Depois de falar o nome e a força do SSID, o NVDA também informará o tipo
	  de segurança da sua rede.
	* O NVDA agora o alertará quando você se conectar e se desconectar de uma
	  rede sem fio.
	* O NVDA agora o alertará quando as conexões sem fio forem ativadas ou
	  desativadas.

## Versão 23.05

* adicionada a capacidade de detectar e apresentar o estado da rede sem fio
  conectada.

	* Anuncia o nome do SSID sem fio conectado.
	* Anuncia a força do ssid
	* Anuncia que o SSID não foi encontrado se nenhum for detectado.

## Versão 23.02

* Requer NVDA 2022.4 ou posteriores.
* É necessário o Windows 10 21H2 (atualização/compilação 19044 de novembro
  de 2021) ou posterior.

## Versão 23.01

* Requer NVDA 2022.3 ou posteriores.
* É necessário ter o Windows 10 ou posterior, pois o Windows 7, 8 e 8.1 não
  serão mais suportados pela Microsoft a partir de janeiro de 2023.
* Atualização da dependência do psutil para a versão 5.9.4.
* O NVDA anunciará a arquitetura real do processador (x86/AMD64/ARM64) como
  parte das informações da versão do Windows.
* Em sistemas de núcleo único, o NVDA não anunciará mais a carga do núcleo
  da CPU, pois a carga média da CPU é a mesma que a carga do núcleo.

## Versão 22.03

A versão 22.03 é a última versão estável compatível com o Windows 7 Service
Pack 1, 8 e 8.1.

* Requer NVDA 2021.3 ou posteriores.
* Uma mensagem de aviso será exibida ao tentar instalar o complemento no
  Windows 7, 8 e 8.1.
* Atualização da dependência do psutil para a versão 5.9.0.

## Versão 22.01

* Requer NVDA 2021.2 ou posteriores.

## Versão 21.10

* O NVDA 2021.2 ou posterior é necessário devido a mudanças no NVDA que
  afetam este complemento.

## Versão 21.08

* O requisito mínimo de versão do Windows agora está vinculado às versões do
  NVDA.
* As compilações do Windows 20348 e 22000 são reconhecidas como Windows
  Server 2022 e Windows 11, respectivamente.
* Nas compilações do Insider Preview, a versão do Windows, como "Windows
  10", não será usada. Em vez disso, o NVDA anunciará "Windows Insider".
* Em sistemas de 64-bit, a arquitetura do processador (x64 ou ARM64) será
  anunciada como parte das informações de versão do Windows.

## Versão 21.04

* Requer NVDA 2020.4 ou posterior.
* Atualizada dependência psutil para 5.8.0.
* Ao pressionar duas vezes os comandos do complemento para copiar a
  informação do recurso para a área de transferência, o NVDA anunciará o
  resumo do recurso que está sendo copiado.

## Versão 21.01

* Atualizada dependência psutil para 5.7.3.
* Mensagem encurtada da versão do Windows.
* No Windows 8.1, compilação.revisão será anunciado como parte da mensagem
  da versão do Windows, semelhante ao Windows 10.

## Versão 20.09

* O tempo de atividade do sistema agora é dado em dias, horas, minutos,
  segundos.
* A compilação do Windows Server Insider Preview 20201 ou posterior é
  devidamente reconhecida como uma compilação do Server Insider.

## Versão 20.07

* O Windows 10 versão 20H2 é reconhecido corretamente ao obter informações
  sobre a versão do Windows (NVDA+Shift+6).
* Mensagem simplificada da versão do Windows 10, ou seja, Windows 10 AAMM em
  vez de Windows 10verAAMM ao pressionar NVDA+Shift+6.

## Versão 20.06

* Foram resolvidos muitos problemas de estilo de codificação e possíveis
  erros com o Flake8.

## Versão 20.04

* Atualizada dependência psutil para 5.7.0.

## Versão 20.01

* Requer NVDA 2019.3 ou posterior devido ao uso ostensivo de Python 3.

## Versão 19.11

* Melhorada detecção de compilações do Windows Insider Preview,
  especialmente a 20H1 e posteriores.

## Versão 19.07

* Atualizada dependência psutil para 5.6.3.
* Alterações internas do comando status da bateria.

## Versão 18.12

* Alterações internas para suportar futuras versões de NVDA.

## Versão 18.10

* O código ficou mais compatível com o Python 3.
* Atualizada dependência psutil para 5.4.7.
* Ao obter capacidade de disco e uso de memória, o NVDA não mais dará erros
  se estiver usando um computador ou um serviço com mais de um petabyte de
  RAM ou tamanho de disco.
* Os valores para uso de memória e disco são mostrados com até duas casas
  decimais (por exemplo, 4,00 GB em vez de 4,0 GB).
* Detecção aprimorada de compilações (builds) do Windows Insider Preview.

## Versão 18.04

Versão 18.04.x é a última versão a suportar versões anteriores ao Windows 7
SP1.

* Última versão para suporte ao Windows Server 2003, Vista e Server 2008.
* Melhor detecção de versões do Windows 10 e distinção entre compilações
  (builds) públicas e Insider Preview.

## Versão 17.12

* Adicionado suporte para processadores ARM 64-bit no Windows 10.

## Versão 17.09

Importante: A versão 17.09.x é a última versão que suporta o Windows XP.

* Última versão a executar em Windows XP.
* Windows 10 compilação 16278 e posteriores são reconhecidas como versão
  1709. Uma versão menor deste complemento será lançada assim que a
  compilação estável da versão 1709 for lançada.

## Versão 17.07.1

* Reintroduzido suporte a Windows XP (quebrado desde a versão 17.02).

## Versão 17.05

* Anúncio do tempo de atividade do sistema (o tempo passado desde a última
  inicialização; NVDA+Shift+7).

## Versão 17.02

* Atualizada dependência psutil para 5.0.1.
* Ao verificar o uso de discos, o NVDA não vai mais apresentar uma mensagem
  de erro em alguns sistemas onde uma mídia removível não é reconhecida
  apropriadamente (por exemplo quando um cartão não está inserido num leitor
  de cartões).

## Versão 16.08

Começando na versão 16.08, os lançamentos do complemento serão mostrados
como ano.mês.revisão.

* Agora são reconhecidas apropriadamente várias revisões do Windows 10 (ex.:
  1607 para a compilação 14393).
* Compilações revisadas do Windows 10 (após instalar atualizações
  cumulativas) são reconhecidas apropriadamente (exemplo, 14393.51).
* Se usando compilações Insider Preview, tal fato é reconhecido.

## Mudanças na 4.5

* Repositório do complemento movido para o GitHub (pode ser encontrado em
  https://github.com/josephsl/resourcemonitor).
* O Windows Server 2016 é reconhecido adequadamente.

## Mudanças na 4.0

* Atualizada dependência psutil para 2.2.1.
* Aprimorado largamente o desempenho ao obter informações de carga da CPU.
* Adicionado suporte ao reconhecimento de Windows 10.
* No Windows 10, o número de compilação também será anunciado.
* Você pode usar o gestor de complementos para acessar a ajuda do
  complemento.

## Mudanças na 3.1

* O Monitor de Recursos suporta oficialmente Windows 8.1.
* Atualizadas traduções.

## Mudanças na 3.0

* Atualizada dependência psutil para 1.2.1.
* Anunciar versão atual de Windows, arquitetura da CPU e service pack se
  houver (NVDA+Shift+6).
* Capacidade de alterar as teclas de atalho do complemento (NVDA 2.13.3 ou
  superior).
* Capacidade de copiar as informações dum recurso individual para a área de
  transferência pressionando duas vezes o comando do recurso.

## Mudanças na 2.4

* Novos idiomas: Chinês (simplificado), Ucraniano.
* Atualizadas traduções.

## Mudanças na 2.3

* Adicionada tradução Búlgara.

## Mudanças na 2.2

* Acrescentadas as seguintes traduções: Árabe, Alemão, Aragonês, Coreano,
  Croata, Eslovaco, Esloveno, Espanhol, Finlandês, Francês, Galego,
  Holandês, Húngaro, Japonês, Italiano, Nepalês, Português (Brasil), Russo,
  Tâmil e Turco.

## Mudanças na 2.1

* Atualizada dependência psutil para versão 0.6.1.
* Corrigida lentidão ao obter informações sobre unidades de disco.
* Enxugamento de código.

## Mudanças na 2.0

* adicionado suporte a traduções e comentários para tradutores.

## Mudanças na 1.0

* Versão Inicial

[1]: https://www.nvaccess.org/addonStore/legacy?file=resourceMonitor
