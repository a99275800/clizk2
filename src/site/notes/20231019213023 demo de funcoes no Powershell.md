---
{"dg-publish":true,"permalink":"/20231019213023-demo-de-funcoes-no-powershell/","dg-note-properties":{}}
---

akin: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]
parent: [[231017c Ajuda do Powershell _index top\|231017c Ajuda do Powershell _index top]]
tags: #proj_zetteltex #zettelkasten #ajuda #internas #admin #tech #powershell 

```powershell
# demonstrando como funcionam as funções (subrotinas) e como elas podem ser chamadas de dentro de outra subrotina; se nunca for chamada a função nunca funciona

<# dicas sobre função:

  parece que usando `function FunkPerere($path)` como nome de função é possível chamar uma função para atuar sobre um parâmetro contido numa Variable; mas talvez esse parâmetro tenha de ser um path...
  
  a definição da function tem de estar antes da sua chamada

#>

function FunkHello
{
  Write-Host "hello there!"
}
function FuncA
{
  Write-Host "sou a função A"
}
function FuncB
{
  Write-Host "sou a função B"
}
function FuncC
{
  Write-Host "sou a função C"
}
$resp = Read-Host "escolha A, B ou C"
if($resp -eq "a")
    {
        FunkHello
        FuncA
    }
elseif($resp -eq "b")
    {
        FunkHello
        FuncB
    }
elseif($resp -eq "c")
    {
        FunkHello
        FuncC
    }
else
    {
        FunkHello
        Write-Host "ok, vc escolheu errado"
    }
``` 

sldkfjlaksdf