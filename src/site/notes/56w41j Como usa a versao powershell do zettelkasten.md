---
{"dg-publish":true,"permalink":"/56w41j-como-usa-a-versao-powershell-do-zettelkasten/","dg-note-properties":{}}
---

akin: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]
parent: [[231017c Ajuda do Powershell _index top\|231017c Ajuda do Powershell _index top]]
tags: #proj_zetteltex #zettelkasten #ajuda #internas #admin #tech #powershell 

## 56w41j Como usa a versão powershell do zettelkasten

use o programa Terminus, ou o Terminal do Windows

Tem de carregar um shell powershell, não serve DOS

roda o "pathfixer.ps1", que deverá estar numa pasta reconhecida pelo PATH do Windows

quando acaba de rodar ele, tem de dar um control+v enter para acionar os comandos que ele deixa guardados na área de transferência

carrega o "zettel_functions.ps1" usando ". .\zettel_functions.ps1" enter

**ATENÇÃO: não adianta digitar só "zettel_functions.ps1", se esquecer do ". .\" antes, nada funciona!!!**

**outra coisa**, a função acima não roda se vc primeiro não alternar para a pasta Z (a sede do zettelkasten, onde estão os `*.ps1`); se as fases anteriores deram certo, basta digitar `gz enter` que vai.

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

Para criar uma tag não adianta escrevê-la dentro de um arquivo, tem de usar o "tc", veja "tc coe"

Para um arquivo aparecer na lista de índices tem de ter a palavra "index" no nome do arquivo; use "isi foo" para ver se foo está entre os índices

pode usar "istag foo" para ver se existe a tag foo