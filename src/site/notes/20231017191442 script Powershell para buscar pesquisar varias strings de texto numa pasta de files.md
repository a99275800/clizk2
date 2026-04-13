---
{"dg-publish":true,"permalink":"/20231017191442-script-powershell-para-buscar-pesquisar-varias-strings-de-texto-numa-pasta-de-files/","dg-note-properties":{}}
---

akin: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]
parent: [[231017c Ajuda do Powershell _index top\|231017c Ajuda do Powershell _index top]]
tags: #proj_zetteltex #zettelkasten #ajuda #internas #admin #tech #powershell 

## básico

```powershell
Get-ChildItem |
  where { (cifrão)_ | Select-String -Pattern 'Bolsonaro' } |
  where { (cifrão)_ | Select-String -Pattern 'Orban' }
```

supõe que você aciona ele dentro do folder do OZ

Se você acrescenta a flag `-Name` ele dá uma lista só de nomes, que é o que queremos (**não mesmo**; se acrescenta -Name como abaixo, o que acontece é que ele pesquisa só nos nomes de files, não no content):

```powershell
Get-ChildItem -Name | where { (cifrão)_ | Select-String -Pattern "palavraquerida" }
``` 

Para pesquisar no content e obter uma lista só com nomes, faz assim:

```powershell
Get-ChildItem |
  where { (cifrão)_ | Select-String -Pattern "Harari" } |
  where { (cifrão)_ | Select-String -Pattern "sapiens" } |
  Select-Object name
``` 

## um script para buscar até 5 palavras

na pasta assets salvo com nome de `search_five.ps1`

```powershell
(cifrão)adress = 'C:\Users\a9927\Dropbox\astolfo S2 alberto\OZ' #esta linha e a seguinte supondo que o script está no subfolder assets dentro do folder OZ
cd (cifrão)adress
(cifrão)1 = Read-Host "Wich to search (1)? (or space for none)"
(cifrão)2 = Read-Host "Wich to search (2)? (or space for none)"
(cifrão)3 = Read-Host "Wich to search (3)? (or space for none)"
(cifrão)4 = Read-Host "Wich to search (4)? (or space for none)"
(cifrão)5 = Read-Host "Wich to search (5, last one)?"
Get-ChildItem |
  where { (cifrão)_ | Select-String -Pattern (cifrão)1 } |
  where { (cifrão)_ | Select-String -Pattern (cifrão)2 } |
  where { (cifrão)_ | Select-String -Pattern (cifrão)3 } |
  where { (cifrão)_ | Select-String -Pattern (cifrão)4 } |
  where { (cifrão)_ | Select-String -Pattern (cifrão)5 }
Remove-Variable (cifrão)1 -EA SilentlyContinue
Remove-Variable (cifrão)2 -EA SilentlyContinue
Remove-Variable (cifrão)3 -EA SilentlyContinue

```