---
{"dg-publish":true,"permalink":"/58-h35s-ps1-script-powershell-para-pegar-todas-as-tags-de-um-zettel-estejam-em-que-linha-estiverem-e-ordenar-sem-repeticoes-numa-linha-so/","dg-note-properties":{}}
---


<!--tiddlyhead title: 58H35s
tags:  #tech #powershell #custom ! !   
tiddlyhead-->

## 58H35s ps1 script powershell para pegar todas as tags de um zettel estejam em que linha estiverem e ordenar sem repetições numa linha só 
!## ## # ## ### coloque isso num PS1 para entender


*se precisar usar isto*, remova as **marcas de code** no resto deste texto

```

℀ ℀ 嬀␀ 㴀 ✀⠀尀℀嬀尀⠀℀尀✀

! [regex](cifrão)regex = '\!'℀ ␀⠀✀⠀尀℀嬀尀⠀℀尀✀   笀␀嘀紀

! Select-String (cifrão)regex .\teste.tmp -All | Select Matches > xyz.tmp℀ ℀  

! (cifrão)regex℀ 

℀   尀    ⠀尀℀嬀尀⠀℀尀   笀␀嘀紀

Get-Content -Path .\teste.tmp | Select-String -Pattern '(\!)[\w]'[^\s]' | foreach {(cifrão)_.Matches.Value} # 'esta wk b só pega o 1º de cada linha!℀   尀    ✀⠀尀℀嬀尀✀⠀℀尀✀   笀␀嘀紀 ℀      먀   ℀         

Get-Content -Path .\teste.tmp | Select-String -Pattern '(\!)[\S]** | foreach {(cifrão)_.Matches.Value} # esta wk b só pega o 1º de cada linha!

sls .\teste.tmp -patt '(\!)[\S]** -All | select lineNumber,fileName,matches |ft -auto # boa, acha tudo, só não me dá o texto dos matches, apenas dados sobre eles, mas acha todos ✀
(cifrão)ask = (cifrão)null␀ 㴀    ⠀  
if ( (cifrão)ask.length -lt 3 ) { (cifrão)ask = "teste.tmp" }   ␀ ℀
pause # debug␀ 㴀  ✀␀✀ 
Write-Host "file is" (cifrão)file # debug ℀
Get-Content (cifrão)file -Raw -Encoding utf8 | Out-File "log.conversor" -Encoding utf8      # porque não adianta grabar tudo com acentuação errada!␀ 㴀 尀
Write-Host "and now file is" (cifrão)file # debug ℀

sls (cifrão)file -patt '(\!)[\S]** -All | foreach {(cifrão)_.Matches.Value} # solução achada aqui <https://stackoverflow.com/questions/804754/how-do-i-return-only-the-matching-regular-expression-when-i-select-stringgrep> # isto wk perfeita/ b põe cada tag numa linha separada; e também se houver títulos começando com ### pega todos! e pega ) no fim da palavra! ␀  ✀⠀尀℀嬀尀✀✀    笀␀嘀紀   ℀      ℀     
Write-Host "`n`n`nblu after 1st search is" # debug  ℀
Write-Host "`n`n" # debug ℀
Get-Content blu.blu | Sort-Object -Unique | Get-Unique | Set-Content blu2.blu℀        ℀  ℀ 㬀        ℀  㬀    㬀 ℀℀℀℀        먀   㬀            㬀     ℀  ꨀ 㬀        ꨀ 

℀ ␀ 㴀  

(cifrão)apagandoAPrimeiraLinha = (cifrão)fileOfInterest[1,']℀  ␀  
⠀         ℀   ꨀ    

até aqui conseguimos: só as tags, sem repetições, pegando em qualquer parte do file, apagando os ! que não são tags, sem cortar letras, ótimo; mas tudo um em cada linhas; falta unificar isso em uma linha só com espaço em branco separando
# para concatenar o arquivo todo numa linha só 尀   笀
 (cifrão)out = (cifrão)out + (cifrão)_ + " "紀
(cifrão)out| Out-File .\blu2.blu

Write-Host "`n`n" # debug    ℀
gc blu2.blu # debug℀  怀怀 ℀

pause # debug℀        ℀  ℀ 㬀        ℀  㬀    

Write-Host "`n`n" # debug℀      ℀

gc blu.blu # debug℀  怀怀 ℀

pause # debug

! Get-Content blu.blu | Get-Unique | Set-Content blu2.blu # apaga linhas duplicadas! gambiarra; ainda não deu certo, sobram uns 3 !, ns pq; vamos à gambiarra 2℀ ℀  怀怀 ℀

! Write-Host "blu2 unified 3 is" # debug℀ ℀   ℀

! Write-Host "`n`n" # debug℀ ℀  ℀

Get-Content blu2.blu | Get-Unique | Set-Content blu.blu # apaga linhas duplicadas! gambiarra; ainda não deu certo, sobram uns 3 !, ns pq; vamos à gambiarra 2℀  怀怀 ℀

Write-Host "blu unified 4 is" # debug℀   ℀

Write-Host "`n`n" # debug℀  ℀

sls blu.blu -patt '(\!)(\w)'(?!/s)' -All | foreach {(cifrão)_.Matches.Value} > blu2.blu # esta versão ainda pega todos os ! mas em linhas separadas, e vou usar uma gambiarra para apagá-los, abaixo℀        ℀  ℀ 㬀        ℀  㬀    

Write-Host "after 2ns search blu is" # debug℀   ℀

pause # debug

```
