---
{"dg-publish":true,"permalink":"/231120a-powershell-copiar-arquivos-listados-num-documento-para-outra-pasta/","dg-note-properties":{}}
---

parent: [[231017c Ajuda do Powershell _index top\|231017c Ajuda do Powershell _index top]]
tags: #ajuda #internas #tech #powershell 

```powershell
# embora os nomes de var falem em mover, este script só copia!
(cifrão)SubFolder = ".\tmp" # para onde irão os files
(cifrão)FileListFile = ".\to_move.tmp" # file que contém a lista; um file por linha; nome completo com extensão; se usar o npp para gerar a lista, tem de encoding em UTF8-BOM antes de salvar, senão vai dar ruim em todos os nomes acentuados!!!
[Array](cifrão)FilesToMove = Get-Content (cifrão)FileListFile
Foreach ((cifrão)File in (cifrão)FilesToMove) { (cifrão)File | Copy-Item -Destination (cifrão)SubFolder; }
```
