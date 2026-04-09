---
{"dg-publish":true,"permalink":"/231012b-novas-dicas-truques-e-testes-para-vs-visual-studio-code/","dg-note-properties":{}}
---


tags: #internas #zettelkasten #ajuda #admin  #vscode  #proj_zetteltex #proj_zetteltex #tech
parent: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]
akin: [[Internas\|Internas]]
akin: [[Projeto-Zetteltex-AKA-OZ-index\|Projeto-Zetteltex-AKA-OZ-index]]

## extensões que pode usar

12 de outubro de 2023 - depois que descobri que o VSCode se incompatibiliza com Beef e autocorr só consegui consertar depois de desabilitar todas as extensões. As que ainda funcionam vão abaixo:

1. Screenshot clipboard: para por imagens, mas é precário, tem de salvar a imagem na pasta /OZ/assets e depois usar o comando "pick" para escolher por nome; melhor que fazer tudo manual; a extensão "dendron" não funciona, esquece.


## testes com notas de rodapé no VSCode

**Notas que funcionam no Obsidian mas não no VSCode** (ao menos sem as extensões) Este é o tipo 1 de nota de rodapé[^1], que também pode ser assim, com espaço antes do colchete [^243] é *objeto* desta l

[^1]: hjsgdjfkhagsdkjhfgk jashdgfkjhgfkjhasd

[^243]: esta é a nota 2

**Testes direto no VSCode - 1** Este é o tipo 1 de nota de rodapé^[1a], que também pode ser assim, com espaço antes do colchete^[243a] é *objeto* - negativo, nenhuma funciona!

[^1a]: hjsgdjfkhagsdkjhfgk jashdgfkjhgfkjhasd

[^243a]: esta é a nota 2

**Testes direto no VSCode - 2** Este é o tipo 1 de nota de rodapé^[meu texto a], que também pode ser assim, com espaço antes do colchete ^[meu texto b] é *objeto* - negativo, nenhuma funciona!

[^1a]: hjsgdjfkhagsdkjhfgk jashdgfkjhgfkjhasd

[^243a]: esta é a nota 2

Até aqui, notar que nenhuma funciona no VSCode mas todas funcionam no Stackedit, por exemplo.

Uma vez habilitada a extensão "Markdown Footnotes", todas as opções passam a funcionar normalmente no VSCode. Resta saber por Quanto tempo a bosta do BeefText vai funcionar com essa mesma extensão habilitada... E todas funcionam no Obsidian.