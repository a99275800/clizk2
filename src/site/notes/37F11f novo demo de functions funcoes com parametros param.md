---
{"dg-publish":true,"permalink":"/37-f11f-novo-demo-de-functions-funcoes-com-parametros-param/","dg-note-properties":{}}
---

tags: #tech #powershell
parent: [[souorfaoporenquanto\|souorfaoporenquanto]]

## 37F11f novo demo de functions funções com parâmetros param

demonstrando como funcionam as funções (subrotinas) e como elas podem ser chamadas de dentro de outra subrotina; se nunca for chamada a função nunca funciona

<! dicas sobre função:

  parece que usando `function FunkPerere((cifrão)path)` como nome de função é possível chamar uma função para atuar sobre um parâmetro contido numa Variable; mas talvez esse parâmetro tenha de ser um path...

  

  a definição da function tem de estar antes da sua chamada

!>

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

(cifrão)resp = Read-Host "escolha A, B ou C"

if((cifrão)resp -eq "a")

    {

        FunkHello

        FuncA

    }

elseif((cifrão)resp -eq "b")

    {

        FunkHello

        FuncB

    }

elseif((cifrão)resp -eq "c")

    {

        FunkHello

        FuncC

    }

else

    {

        FunkHello

        Write-Host "ok, vc escolheu errado"

    }

