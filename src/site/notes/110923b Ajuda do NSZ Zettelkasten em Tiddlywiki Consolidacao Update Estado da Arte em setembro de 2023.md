---
{"dg-publish":true,"permalink":"/110923b-ajuda-do-nsz-zettelkasten-em-tiddlywiki-consolidacao-update-estado-da-arte-em-setembro-de-2023/","dg-note-properties":{}}
---


akin: [[Projeto-Zetteltex-AKA-OZ-index\|Projeto-Zetteltex-AKA-OZ-index]]; [[Historia deste Zettelkasten e suas sucessivas versoes\|Historia deste Zettelkasten e suas sucessivas versoes]]
parent: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]
tags:  #zettelkasten #proj_zetteltex #tech #ajuda #internas 

Obsoleto, q.v. [[Historia deste Zettelkasten e suas sucessivas versoes\|Historia deste Zettelkasten e suas sucessivas versoes]]

## INTRO

Este file está bem incompleto, e vejo que não há um completo sobre. Veja por ora [[Historia deste Zettelkasten e suas sucessivas versoes\|Historia deste Zettelkasten e suas sucessivas versoes]].

### MIGRAÇÃO PARA BEEFTEXT

Depois de muito tempo parado, agora passei todos os [[arquivos auxiliares do NSZ projeto zettelkasten em tiddlywiki\|arquivos auxiliares do NSZ projeto zettelkasten em tiddlywiki]] para uma versão em BeefText (um auto-completador free que o TJ deixa instalar), para poder atualizar as coisas TiddlyWiki no PC do Fórum também.

>[!example]- texto obsoleto...
>Em princípio a ideia é em casa continuar usando o Lintalist, de modo que os tais [[arquivos auxiliares do NSZ projeto zettelkasten em tiddlywiki\|arquivos auxiliares do NSZ projeto zettelkasten em tiddlywiki]] precisam ser mantidos em sincronia com os do BeefText, que são 3 arquivos em formato `csv`, a saber:
>>`Beeftext_Combo_Export_titles.csv`
>>`Beeftext_Combo_Export_RQRs.csv`
>>`Beeftext_Combo_Export_TAGs.csv`
>DETALHE: Em princípio os 3 ficarão na mesma pasta em que ficam os auxiliares do Lintalist. 
>Isso tudo ainda em fase de teste.
>ATUALIZANDO: para não ter de fazer os backups dos "grupos" separadamente, e depois importar um por um, unifiquei todos os "combos" num só "grupo", chama `NSZ_TiddlyWiki_Full`. 

Obviamente acabei des-sincronizando as listas de tags e RQRs do BeefText e do Lintalist, e este foi abandonado. O jeito certo (ou pelo menos o jeito que estou usando) é atualizar a lista de tags, RQR etc. direto no combo do Beef, em vez de mexer nos antigos arquivos auxiliares, ou em verbetes aqui. Para saber qual a lista completa de tags, ou de índices, ou de RQR, abra `BeefText_for_NSZ_TiddlyWiki_all_combos.csv` na pasta de Astolfo do Dropbox. É um arquivo grande, porque funde tudo, mas é fácil de desmembrar porque sai em ordem alfa; as tagas começam com `!`, os RQSs com RQR e os índices começam com `x-`. É só manter esse padrão quando for acrescentar novos itens no Beef.

### E OS RQRSs, COMO FICAM?

Pois é, o único jeito de ter uma lista atualizada é exportar o combo `lista_RQRs` do BeefText, e daí abrir no NPP para usar macros e apagar as info supérfluas, etc. 

Pior, para manter a sincronia entre os vários PCs, tem de fazer backup dos três combos do Beef toda vez que alterar um deles, e manter salvos esses backups no Dropbox para ficar puxando. 

