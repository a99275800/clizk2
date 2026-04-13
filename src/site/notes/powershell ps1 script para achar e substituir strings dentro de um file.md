---
{"dg-publish":true,"permalink":"/powershell-ps1-script-para-achar-e-substituir-strings-dentro-de-um-file/","dg-note-properties":{}}
---

akin: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]
parent: [[231017c Ajuda do Powershell _index top\|231017c Ajuda do Powershell _index top]]
tags: #proj_zetteltex #zettelkasten #ajuda #internas #admin #tech #powershell 

```powershell
(cifrão)input_path = '.\apagateste.md' # este é o file alvo da operação!!!
(cifrão)output_file = '.\xxx_teste.tmp'
(cifrão)output_file2 = '.\xxx_teste2.tmp'
(cifrão)output_file3 = '.\xxx_teste3.tmp'
(cifrão)regex = '\[(.*?)\]' # este é o código regex que é o motor da operação da linha adiante, ele é que determina o que vai ser filtrado pelo comando
select-string -Path (cifrão)input_path -Pattern (cifrão)regex -AllMatches | % { (cifrão)_.Matches } | % { (cifrão)_.Value } > (cifrão)output_file # pega todas as strings dentro do file que contenham qualquer texto entre os sinais [ e ]
gc (cifrão)output_file

(Get-Content (cifrão)output_file).replace('[[', '') | Set-Content (cifrão)output_file2 # este comando substitui a string `[[` pela string vazia
(Get-Content (cifrão)output_file2).replace(']', '') | Set-Content (cifrão)output_file3 # idem, agora com a string `]`
echo "`n"
echo "`n"
echo "`n"
gc (cifrão)output_file3

del .\xxx_test*.tmp # só por capricho
``` 