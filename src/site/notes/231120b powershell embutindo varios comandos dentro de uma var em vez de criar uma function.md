---
{"dg-publish":true,"permalink":"/231120b-powershell-embutindo-varios-comandos-dentro-de-uma-var-em-vez-de-criar-uma-function/","dg-note-properties":{}}
---

parent: [[231017c Ajuda do Powershell _index top\|231017c Ajuda do Powershell _index top]]
tags:  #ajuda #internas #admin #tech #powershell 

## embutindo vários comandos dentro de uma (cifrão)var em vez de criar uma function 

É uma var, a var `(cifrão)cabecalho`, mas pode ser usada como se fosse uma função; Se chama ela com `(cifrão)cabecalho`, só escreve o texto na tela; mas se chama com um & antes, assim: `&(cifrão)cabecalho`, ela é executada no lugar da chamada, e depos o PS segue executando as linhas seguintes; o `(cifrão)SCRIPT:` antes do nome cabecalho é para dizer que essa var só vale dentro desde script, não é global, é local! Como isto é uma var e não uma func, não precisa comandos complicados para saber quando volta ao ponto do call ou para onde vai depois de executada, sempre volta ao ponto da call.

```powershell
(cifrão)SCRIPT:cabecalho = { # function (cifrão)cabecalho
  Write-Host "`n "
  Write-Host "//  OZ Functions Script, v. (cifrão)version                                                  //" -foregroundcolor White -backgroundcolor DarkGray
}
``` 
Não esqueça do sinal de `=` depois no nome e antes da chave.