---
{"dg-publish":true,"permalink":"/powershell-ajuda-dicas-boas-tiradas-de-videos/","dg-note-properties":{}}
---

tags: #proj_zetteltex #zettelkasten #ajuda #internas #admin #tech #powershell 
parent: [[231017c Ajuda do Powershell _index top\|231017c Ajuda do Powershell _index top]], akin: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]

1. para ver as opções de um comando qualquer, digite o começo do nome e `ctrl+space`
2. `ls *.md | Select BaseName | Format-Wide` faz uma lista com nome sem extensão e em duas colunas
3. Pode usar `(ls foo.md).BaseName` para fazer a mesma coisa
4. com o `ls | Select` pode usar as chaves `FullName` para pegar o caminho completo com extensão, ou `DirectoryName` para pegar só o caminho
5. use `Alias:` para ver a lista completa dos comandos e seus shortcuts
6. pegar os apps em uso ordenados por carga em CPU: `gps | Sort-Object CPU -Descending | Select-Object -First 20`
7. 