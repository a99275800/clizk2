---
{"dg-publish":true,"permalink":"/20231018131112-obsidian-scripts-de-powershell-feitos-e-a-fazer-para-o-oz-2/","dg-note-properties":{}}
---



akin: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]], [[Obsidian to-do list\|Obsidian to-do list]]
parent: [[231017c Ajuda do Powershell _index top\|231017c Ajuda do Powershell _index top]]
akin: [[231011a Obsidian - ajuda caput\|231011a Obsidian - ajuda caput]]
tags: #proj_zetteltex #zettelkasten #ajuda #internas #admin #tech #powershell 


## feitos

1. `sx5` - busca **por content** até 5 strings e entrega lista numerada para escolher um
1. `sx2` - busca **por content** até **2 strings** e entrega lista numerada para escolher 
1. `OLO` - *open last one*, abre no npp file cujo nome foi salvo no clipboard por um dos searchadores
1. `RLO` - *read last one*, mostra na tela file cujo nome foi salvo no clipboard por um dos searchadores
2. `GRZ` - *grab random zettel* pega um zettel randomicamente e lê na tela
3. `SFN` - *search file names*: busca só nos filenames por uma string apenas, que tem de ser passada como param1 .
4. `SFN2` - *search file names for 2 strings*: busca por até duas strings nos filenames apenas.
1. `SXC` `- `*search file content for 1 string*: busca por uma string só nos contents, mas tem de ser passada como param.
1. ``noname` - rotina interna no FOP para gerar lista dos files que fazem remissão ao (cifrão)LWF
4. o pathfixer 
5. o backupero
1. `noname` - rotina interna do FOP para capturar lista de links citados no (cifrão)LWF e clipar ou rodar esse links
1. `noname` - rotina interna do FOP para acrescentar texto no (cifrão)LWF

## a fazer

2. um para criar novos zettels conforme template !important
3. um para ir salvando num file nomes de files achados para depois usar a lista para alguma coisa
4. alguma coisa para não ter de digitar .\ nem tab antes de rodar um script (function loader?)
5. um que permita acessar o menu de fileOps a partir do prompt passando uma UIUI como param para ele achar esse file e colocar como LWF para ser operado
6. as LOGOPS especialmente uma para recuperar a lista dos últimos (cifrão)LWF
7. um para backupear o OZ inteiro para a pasta bostoca
