---
{"dg-publish":true,"permalink":"/34-e33e-abre-zettel-obsoletos/","dg-note-properties":{}}
---


<!--tiddlyhead title: 34E33e  　
tags: #powershell   
tiddlyhead-->

## 34E33e abre_zettel obsoleto 01 
### v1

se precisar usar isto, remova as marcas de code no resto deste texto


```


testes℀
  Este script funciona no DarkWingDuck, pq usa um path absoluto para o notepad++                   㬀 㬀      
     　  
    
    a) rotina de confere/muda℀
␀ 㴀  怀✀         怀   
(cifrão)var1 = (cifrão)suspeito    ␀
(cifrão)var2 = ls '(cifrão)suspeito'    ␀
pause尀尀尀 ␀

## v2
<!              
  Serve para ser usado depois de uma pesquisa por arquivo, no qual localizamos um zettel que queremos abrir; será preciso memorizar uma parte inconfundível do nome do file; daí digita essa parte no prompt  
  v. 2.0, obsoleta  
  to-do:       
!>

aqui, etapa de confirmação e mudança opcional 
{      ␀
  Write-Host "debugging; line30" # debug      ␀
  Write-Host "debugging; line18, var2 is" (cifrão)var2 # debug
>! interação com user para eventual correção        
>(cifrão)answer1 = Read-Host "Is that OK? `n[O]k / [R]estart (line22)"(cifrão)var2 # debug em parte!!!⠀␀            ℀   
>>{        ␀
>>}⠀␀            ℀ 
>>{  
>>>(cifrão)suspeito = (cifrão)null␀ 㴀 ␀
>>>Write-Host "debugging; acabei de esvaziar a var2, que agora vale" (cifrão)var2 # debug␀ 㴀 ␀
>>># reiniciando␀ 㴀  怀   
      Write-Host "debugging no reboot suspeito2 is" (cifrão)suspeito2 # debug      ␀ 㴀 ␀
      Write-Host "debugging  no reboot var1a is" (cifrão)var1a # debug       ✀␀✀ ℀
      (cifrão)var2a = ls '(cifrão)suspeito2'              ␀ ℀
      Write-Host "debugging; isto conclui o reboot" # debug      ℀
      Lamentavelmente tive de usar essa gambiarra, por não conseguir um jeito de voltar ao início (à fase de checagem) sem esvaziar a variável          
      !>       㬀        ℀
      Write-Host "ok, going ahead, calling NPP with file "(cifrão)var2              
      pause      尀尀尀 ␀
      break ! para não entrar em loop紀
>else                  ! abort mission笀
>>>Write-Host "ok, that's weird"
>>}紀
℀           㬀    
(cifrão)suspeito = Read-Host "`nIt's a script to open a .md file in notepad++.`nGimme a clue: "    ␀ ℀
(cifrão)var1 = (cifrão)suspeito  ␀ ℀
ls '(cifrão)suspeito' # debug␀ 㴀  ✀␀✀
Write-Host "debugging" (cifrão)var2 # debug 㬀      ␀ ℀
Write-Host "debugging; isto conclui o corpo do script" # debug 㬀      ␀ ℀
FunkTestaCoisas 㬀      ␀ ℀
Write-Host "debugging; só falta a última linha do script" # debug 㬀      ␀ ℀
pause 㬀       ␀ ℀
C:\Prog\notepad++\notepad++.exe (cifrão)var2
℀

esta é a versão stable, que funciona!␀ 㴀  怀✀         怀   
(cifrão)var1 = (cifrão)suspeito    ␀
(cifrão)var2 = ls '(cifrão)suspeito'    ␀
pause尀尀尀 ␀
!>
℀℀ 
℀
  Este script funciona no DarkWingDuck, pq usa um path absoluto para o notepad++                   㬀 㬀      
     　  
    
    a) rotina de confere/muda (aprimorar, está gambiada)                   
!>

aqui, etapa de confirmação e mudança opcional 
{      ␀
  ! Write-Host "debugging; line30" # debug      ␀
  ! Write-Host "debugging; line18, var2 is" (cifrão)var2 # debug
>! interação com user para eventual correção℀         
>(cifrão)answer1 = Read-Host "Is that OK? `n------- [O]k or [R]estart"⠀␀            ℀   
>>{        ␀
>>}⠀␀            ℀ 
>>{  
>>>(cifrão)suspeito = (cifrão)null␀ 㴀 ␀
>>>! Write-Host "debugging; acabei de esvaziar a var2, que agora vale" (cifrão)var2 # debug␀ 㴀 ␀
>>>#reiniciando␀ 㴀  怀  
      ! Write-Host "debugging no reboot suspeito2 is" (cifrão)suspeito2 # debug      ␀ 㴀 ␀
      ! Write-Host "debugging  no reboot var1a is" (cifrão)var1a # debug      ℀  ✀␀✀ ℀
      (cifrão)var2a = ls '(cifrão)suspeito2'      ℀         ␀ ℀
      ! Write-Host "debugging; isto conclui o reboot" # debug      ℀
      Lamentavelmente tive de usar essa gambiarra, por não conseguir um jeito de voltar ao início (à fase de checagem) sem esvaziar a variável          
      !>      ℀  㬀        ℀
      Write-Host "ok, going ahead, calling NPP with file "(cifrão)var2a              
      pause      尀尀尀 ␀
      break ! para não entrar em loop紀
>else                  ! abort mission笀
>>>Write-Host "ok, that's weird"
>>}紀
℀           㬀    
(cifrão)suspeito = Read-Host "`nIt's a script to open a .md file in notepad++.`nGimme a clue"℀     ␀ ℀
(cifrão)var1 = (cifrão)suspeito℀   ␀ ℀

ls '(cifrão)suspeito' # debug␀ 㴀  ✀␀✀

Write-Host "debugging" (cifrão)var2 # debug℀  㬀      ␀ ℀

Write-Host "debugging; isto conclui o corpo do script" # debug℀  㬀      ␀ ℀
FunkTestaCoisas℀  㬀      ␀ ℀

Write-Host "debugging; só falta a última linha do script" # debug℀  㬀      ␀ ℀

pause℀  㬀       ␀ ℀
C:\Prog\notepad++\notepad++.exe (cifrão)var2
<!℀       ℀
(cifrão)suspeito = Read-Host "`nIt's a script to open a .md file in notepad++.`nGimme a clue: "␀ 㴀 ␀
Write-Host "Your clue was: "(cifrão)suspeito␀ 㴀  ✀␀✀
Write-Host "I found this: "(cifrão)var2
C:\Prog\notepad++\notepad++.exe (cifrão)var2℀
℀℀ 
℀
  Este script funciona no DarkWingDuck, pq usa um path absoluto para o notepad++                   㬀 㬀      
     　  
    
    a) rotina de confere/muda (aprimorar, está gambiada)                   
!>

aqui, etapa de confirmação e mudança opcional 
{      ␀
  Write-Host "I found this: "(cifrão)var2
>! interação com user para eventual correção␀ 㴀     怀 嬀  嬀
>if((cifrão)answer1 -eq "o")          ! tudo certo, vamos笀
>>>Write-Host "ok, going ahead, calling NPP with file "(cifrão)var2紀
>elseif((cifrão)answer1 -eq "r")          ! reboot笀
>>>Write-Host "ok, rebooting"␀ 㴀 ␀
>>>(cifrão)var2 = (cifrão)null␀ 㴀 ␀
>>>#reiniciando␀ 㴀  怀  
      (cifrão)var1a = (cifrão)suspeito2      ␀ 㴀  ✀␀✀
      ! Lamentavelmente tive de usar essa gambiarra, por não conseguir um jeito de voltar ao início (à fase de checagem) sem esvaziar a variável.              ␀
      Write-Host "If anything went wrong, press Cancel+C and retry..."      
      C:\Prog\notepad++\notepad++.exe (cifrão)var2a       ℀     
>>}                  ℀  
>>{  ✀ 
>>>break紀
}

esta parte pede o suspeito, e acha o nome completo dele; e exibe, para confirmar␀ 㴀  怀✀         怀  
(cifrão)var1 = (cifrão)suspeito␀ 㴀  ✀␀✀
FunkTestaCoisas℀ 
C:\Prog\notepad++\notepad++.exe (cifrão)var2

```