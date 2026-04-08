---
{"dg-publish":true,"permalink":"/56w41k-manual-ajuda-terminus-terminal-como-usar-a-versao-powershell-do-zettelkasten/","dg-note-properties":{}}
---

tags: #proj_zetteltex #zettelkasten #ajuda #internas #admin
parent: [[20180805220719\|20180805220719]]

## 56w41j Como usa a versão powershell do zettelkasten

use o programa Terminus, ou o Terminal do Windows

Tem de carregar um shell powershell, não serve DOS

roda o "pathfixer.ps1", que deverá estar numa pasta reconhecida pelo PATH do Windows

quando acaba de rodar ele, tem de dar um control+v enter para acionar os comandos que ele deixa guardados na área de transferência

carrega o "zettel_functions.ps1" usando ". .\zettel_functions.ps1" enter

convém (opcional) carregar agora a função "updateIndexList", digitando isso e enter; isso demora

Agora faz um backup geral rodando "backupero.ps1" ( ou seja ". .\backupero.ps1" enter)

está pronto para usar

o script que se usa para ler/buscar zettels é o catcher.ps1, que você chama com "zc" mais o que está buscando (um endereço ou ID específico e certo). Chame "zc coe" para ver a ajuda.

o script de criar zettels é "novozettel.ps1"; chame "zn coe" para ver a ajuda

para busca por palavra usa "ss palavra"; chame "ss coe" para ajuda

o "zs coe" é ajuda de uma versão antiga da busca, que ainda funciona

pode usar "zf coe" para ver a ajuda do zettel_functions, tem muita coisa importante lá

em relação ao último zettel utilizado (pelo ZC geralmente) for yout convenience, data are stored:

    - the file object in.. (cifrão)x (nome completo do file)

    - the ID in............(cifrão)z (and in the clipboard) (usa essa ID para chamar o ZC)

    - the content in.......(cifrão)y (texto dele)

    - the parent in........(cifrão)w

    - the tags in..........(cifrão)lwft

    - the caption in.......(cifrão)lwfc

    - the fullpath in......(cifrão)lwfp

    - the basename in......(cifrão)k

    

  Para ver uma lista completa do conteúdo dessas variáveis, "funkRescueSavedDataForCheck"

