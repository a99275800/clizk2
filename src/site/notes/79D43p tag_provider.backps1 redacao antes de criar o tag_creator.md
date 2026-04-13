---
{"dg-publish":true,"permalink":"/79-d43p-tag-provider-backps1-redacao-antes-de-criar-o-tag-creator/","dg-note-properties":{}}
---


<!--tiddlyhead title: 79D43p      
tags: #tech #custom #powershell   
tiddlyhead-->


xxxapagar
## 79D43p tag_provider ps1 redação antes de criar o tag_creator 
Da próxima linha em diante, redação oficial, não mexa nem reformate

℀ ℀℀℀                  ℀℀℀ ⠀                   ℀℀℀ ℀℀℀

#### MUITO IMPORTANTE ### não altere nada antes do final da tag "admin", o pedaço que diz℀       　

tem de ficar exatamente com está aí. é que a gambiarra "tag_creator.ps1" depende de achar essa string, para inserir as tags novas logo depois da vírgula que está depois de ℀  


```

function f { #xyz  ⠀
        嬀嘀⠀　　␀
      嬀嘀⠀　　␀
        嬀嘀⠀　　␀
        嬀嘀⠀　　␀
        嬀嘀⠀　　␀
  )  ℀ 嬀␀ 㴀 ␀␀␀␀␀ ℀
  [string](cifrão)gambiarra = " `!"  嬀␀ 㴀 ␀␀␀␀␀␀␀␀␀␀
  scb (cifrão)tags   怀         怀
  Get-Clipboard   怀    怀怀          怀            怀怀
}
Write-Host "`n`nThis is a nested Powershell instance. `nPlease call `"f`{space`}`{some letter`}`{tab`}`" and choose the tags.`nYou may choose up to 5 of them, or let some blank.`nYour choices will be stored in the clipboard after `{Return`}.`n"


```