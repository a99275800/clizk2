---
{"dg-publish":true,"permalink":"/busca-por-string-nos-nomes-dos-files-e-deixa-escolher-um-resultado-para-por-nome-dele-no-clipboard/","dg-note-properties":{}}
---

akin: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]
parent: [[231017c Ajuda do Powershell _index top\|231017c Ajuda do Powershell _index top]]
tags: #proj_zetteltex #zettelkasten #ajuda #internas #admin #tech #powershell 

o código está bem sujo e poderia ser enxugado, mas funciona

na pasta de assets salvo com nome de `search_and_clip.ps1`

```powershell
cls
(cifrão)nameToSearch = Read-Host "What are you looking for? (one word...)"
ls "*(cifrão)nameToSearch*" -Recurse | select basename > teste.tmp
ls "*(cifrão)nameToSearch*" -Recurse | select Name > testeFull.tmp
Write-Host "`n`nI'm function srxN and I found these:"
cat .\teste.tmp | %{ "(cifrão)((cifrão)_.ReadCount) (cifrão)_" } # função contalinhas!
(cifrão)1 = Read-Host "`nSet [line number] to clip, or [AOK] to go back..."
  if ( (cifrão)1.length -lt 1 ) { break }
  else {
    (cifrão)whatToDo = "c" # tinha uma escolha para abrir aqui, mas não vamos usar
  }
  (cifrão)2 = (Get-Content -Path .\teste.tmp -TotalCount (cifrão)1)[-1]
  # (cifrão)2 -split '\s' > srxn.tmp # splita o texto quebrando nos espaços # não queremos mais o nome do file quebrado em várias linhas!
  (cifrão)2 > srxn.tmp # então jogamos ele numa linha só
  (cifrão)b = gc .\srxn.tmp # joga o texto com nome da linha escolhida num file
  # Write-Host 'received this as (cifrão)b... ' (cifrão)b
  (cifrão)c = (cifrão)b
  # Write-Host 'received this as (cifrão)c... ' (cifrão)c
  # if ( (cifrão)whatToDo -eq "o" ) { start (cifrão)c.md }
  scb (cifrão)c  -EV Err -EA SilentlyContinue
  Write-Host "`nFunction srxN here... (cifrão)c - is now stored in the clipboard.`nBye, (cifrão)env:USERNAME."
```

