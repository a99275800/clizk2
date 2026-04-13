---
{"dg-publish":true,"permalink":"/48-x35n-demo-de-functions-funcoes-com-parametros-param/","dg-note-properties":{}}
---

tags: #tech #powershell
parent: [[souorfaoporenquanto\|souorfaoporenquanto]]

## 48X35n demo de functions funções com parâmetros param

# demo de function com param

function OSx {

<!

.SYNOPSIS

    This function reads two parameters of your input line, then echoes that in the outpur line.

.DESCRIPTION

    OK, funciona assim: escreva um script com a(s) function(s) e dê nome aos parâmetros; carregue o script na memória do PS digitando

  

          . .\funcdemocomparam.ts1

          

    Parecerá que ele não rodou, mas fica salvo (as function ficam na memória). Daí, para usar uma delas, digita só

  

          nomeDaFunction param1 param2

  

    Pelo que entendi, nao precisa explicar que param1 é o param1, é só escrever a palavra ou termo que enche o param; pelo menos com o cmdlet write-host funciona

  

    muito boa ensinança sobre function aqui: https://ss64.com/ps/syntax-functions.html!

.PARAMETER DemoParam1

    Just type your stuff, man! See examples bellow.

    

.PARAMETER DemoParam2

    Just type your stuff, man! See examples bellow.

.EXAMPLE

    Use the script calling:

    

        . .\demo_func_with_params.ps1

    

    That load the functions present in the script body on the system memory. After that, you may call:

    

        osx "any text string" "another text string"

        

    to read the same in the output. C'mon, it's just a demo!

.EXAMPLE

    You may use as param a longer text string, using multiple lines and special characters, if put @" in the start, followed by an Enter, then your text (use Enter to brake lines) and "@ at the end.

.NOTES

    Author: Name

    Last Edit: 02/26/2020 15:26:38

    Version 1.0 - initial release of blah

    

!>

param( (cifrão)1, (cifrão)2 )

Write-Host "eu li (cifrão)1 e depois (cifrão)2"

}

function OSx2 {    ! esta cria um campo de texto complexo seguido de um nome de arquivo para salvar

param( (cifrão)1, (cifrão)2 )

Write-Host "eu li (cifrão)1 e depois (cifrão)2"

(cifrão)1 > .\(cifrão)2.tmp

Write-Host "seu arquivo foi salvo como "(cifrão)2".tmp na pasta "pwd

}

  

<!

  

!>