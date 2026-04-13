---
{"dg-publish":true,"permalink":"/zk-changelog/","dg-note-properties":{}}
---

v.8.2.15 (260329160247): tentando consertar 3 bugs: (a) **Bug 1 (Configuração de Fábrica do Micro):** Alteração no `zk_core.py` para remover a limitação de 80 colunas e a variável de ambiente forçada, permitindo que o Micro use a largura total da tela. (b) **Bug 2 (Basename na Captura):** Alteração no `zk.py` (função `menu_captura_lwf`, opção 'b') para remover a extensão do arquivo capturado (tem de ser só basename). (c) **Bug 3 (AttributeError Contexto):** Localizar a função correta no `zk_fileops.py` (v6.1.16-beta) e corrigir a chamada no `zk.py` (a função de capturar contexto do LWF na tela Home quebrou). Tentando integrar o módulo zk_dossier ao Home. Aparentemente os bugs estão resolvidos, mas falta testar todas as funções desde o zero.

v.8.2.14 (260328093429): tentando criar um módulo autônomo eye-candy chamado zk_classified.py para exibição chavosa de zettels. Última versão antes de tentar corrigir 3 bugs do CLIZK e integrar o zk_dossier, portanto é mais segura que a próxima.

v.8.2.13 (260327192301): Criando um zk_cinema para exibir vídeos, autônomo. Resto igual.

v.8.2.12 (260326200224): mexendo no Ultra para abrir links de assets e de internet. Experimental, funcionando, sem bugs aparentes. Outras funções não foram mexidas mas persistem no mesmo status da v. abaixo. Criado o módulo autônomo zk_quotes.

v.8.2.11 (260326170051): tentando aperfeiçoar um zk_slides, ainda módulo independente, assim como o murmurs, não integrados. O resto do projeto segue igual v.8.2.9, mesmo status. 

v.8.2.10 (260325142837): criando o zk_murmurs. Outras funções e scripts iguais e não testadas. 

v.8.2.9 (260325110148): tentando melhorar o zk_ssvhs. Integrado ao módulo Extra/Goodies. Outras funções não testadas. 

v.8.2.8 (260324210148): mudamos o zk_goodies para usar o iTerm2 permitindo a exibição das imagens no próprio terminal, sem janela popup. 

v.8.2.7 (260320215920): Alterações na aparência do Ultra. Outras funções não testadas. 

v.8.2.6 (260320214311): Ultra criado e testado e integrado satisfatoriamente ao CLIZK. Ultra funciona. Funções do CLIZK não re-testadas.

v.8.2.5 (260320164820): lutando para criar o Ultra mas o CLIZK está igual à versão anterior ainda.

v.8.2.4 (260320115614): Integrada a função zk_pdf para visualização de PDFs em modo retrô. Todas as funções testadas. Bugs que não prejudicam operação (q.v. [[projeto-ZKM-tasklist-to-do-list-do-novo-zkPython\|projeto-ZKM-tasklist-to-do-list-do-novo-zkPython]]. A captura de contexto do LWF está bugada, isso é o mais irritante. Status: SAFE.

v.8.2.3 (260320115139): Integrada a função kittyops para visualização de imagens em modo retrô.

v.8.2.2 (260319201603): Assumi controle do versionamento e changelog, serão atualizados manualmente. Conseguimos rebatizar o projeto para CLIZK (levou horas). Aparentemente tudo funciona. Status: SAFE.

v.8.2.1 (260318221157): Tela Home e módulos FileOps, System, Pile, Buffer: funcionais. Módulos Tags e Tasks: um bug cada, nada que comprometa o funcionamento. Pesquisas e refinações testados, OK. Falta revisar os demais módulos. Goodies só ativam por inteiro (barras de progresso, por exemplo) se carregados desde o prompt, a opção interna não ativa as barras. Próximo item: assumir o controle do changelog e do versionamento.

---
#projeto-ZKM #mac #proj_zetteltex [[projeto-ZKM-OZ-em-python-index\|projeto-ZKM-OZ-em-python-index]]