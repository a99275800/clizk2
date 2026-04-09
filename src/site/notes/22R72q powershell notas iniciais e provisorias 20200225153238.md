---
{"dg-publish":true,"permalink":"/22-r72q-powershell-notas-iniciais-e-provisorias-20200225153238/","dg-note-properties":{}}
---

tags: #proj_zetteltex #zettelkasten #ajuda #internas #admin #tech #powershell 
parent: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]

## 20200225153238 powershell notas iniciais e provisórias


se precisar usar isto, remova as marcas de code no resto deste texto

aprendendo powershell

pegar a data no formato zettel: ```Get-Date -Format dMMyyyyhhmmss```

setar variável: ```Set-Variable -Name "teste" -Value "puxa vida"```

ler arquivo: ```gc .\teste.txt``` (```cat``` idem)

append / acrescenta texto a ul arquivo já existente igual ao bat: ```"a casa da coxinha" >> .\teste.txt```

```Get-Clipboard``` é control v

busca por um arquivo ou arquivos com nome semelhante à string: ```ls | Where-Object {(cifrão)_.Name -like "tes'"}```

converte resultados de operações para html: ```Get-Process | ConvertTo-Html | Out-File "teste.html"```

criar pasta: ```New-Item -Path 'X:\Guru99' -ItemType Directory```

salva pasta atual: ```pushd```

volta para pasta salva: ```popd```

fazer esta configuração para poder rodar scripts, se o sistema proibir: ```Set-ExecutionPolicy -Scope CurrentUser Unrestricted```

para rodar um programa: ```start notepad.exe``` (embora só o nome do executável tb wk)

o mesmo para arquivos com extensão registrada: ```start "arquivotal.txt"```

!!!

```(cifrão)teste = Get-Date```

(grava o data na variável (cifrão)teste)

```(cifrão)process = Get-Process notepad```

captura a identidade de um processo e salva numa variável; aplicar um "método" usando a variável como parâmetros afeta o processo (kill pex)

depois

```(cifrão)process.Kill()```

To run a command that contains a space in its name, enclose its filename in singlequotes (') and precede the command with an ampersand (&), known in PowerShell as

the invoke operator:

```& 'C:\Program Files\Program\Program.exe' arguments```

a program name in quotes is no different from any other string in quotes (daí nid & antes)

para listar as váriáveis de ambiente (fixas do sistema)

```Get-ChildItem env:```

para chamar essas bostas nao basta digitar o nome, pex HOMEPATH, tem que ser:

```(cifrão)env:HOMEPATH```

isto diz oi ao usuário:

```

(cifrão)myString = 'Hello, ' + (cifrão)env:USERNAME

(cifrão)myString

```

To define a here string (one that may span multiple lines), place the two characters @" at the beginning and the two characters "@ on their own line at the end.

For example:

```

(cifrão)myHereString = @"

This text may span multiple lines, and may

contain "quotes."

"@

```

### isso é um possível começo para a tentativa de fazer edição de texto no prompt; dá para escrever uma string de texto rico assim, e >> ela para um arquivo existente, ou > novo

Windows PowerShell supports escape sequences inside strings

```

`a The alarm character. Generates a beep when displayed on the console

`n A newline.

`r A carriage return. Newlines in PowerShell are indicated entirely by the `n character, so this is rarely required.

`t A tab.

```

!!!

pede ao usuário que preencha (digite) o valor de uma variável

```(cifrão)directory = Read-Host "Enter a directory name"```

isto serve para saber qual tecla o user apertou, mas só funciona no console, não no ISE

```(cifrão)key = (cifrão)host.UI.RawUI.ReadKey("NoEcho,IncludeKeyDown")```

como passar um nome de arquivo como argumento para um comando do PowerShell

The answer is to define a variable to hold the argument value, and

just use that in the place you used to write the command argument; You can use the same technique when you call a PowerShell cmdlet, script, or function:

```

(cifrão)filename = "c:\path\to\other\file.txt"

Get-Acl -Path (cifrão)filename

```

acha a string 'populismo' em todos os '.md da pasta

```Select-String -simple 'populismo' .\'.md | more```

esta versão faz o mesmo, mas usa uma variável, (cifrão)xyz, que podemos pedir a user para preencher

```Select-String -simple (cifrão)xyz .\'.md | more```

embora esta seja a versão recomendada pelo escritor:

```Get-ChildItem '.md -Recurse | Select-String 'bolsonaro' | more```

que tb se escreve assim:

```dir '.txt -rec | sls pattern | more```

!!!

ss64.com/ps

ótimo saite com help

isso aí detecta quando uma determinada tecla é pressionada

--------------------------------------------

```

Add-Type -AssemblyName WindowsBase

Add-Type -AssemblyName PresentationCore

choose the abort key

(cifrão)key = [System.Windows.Input.Key]::LeftCtrl

  

Write-Warning "PRESS (cifrão)key TO ABORT!"

  

do

{

  (cifrão)isCtrl = [System.Windows.Input.Keyboard]::IsKeyDown((cifrão)key)

  if ((cifrão)isCtrl)

  {

    Write-Host

    Write-Host "You pressed (cifrão)key, so I am exiting!" -ForegroundColor Green

    break

  }

  Write-Host "." -NoNewline

  Start-Sleep -Milliseconds 100  # comando Wait

} while ((cifrão)true)

```

-----------------------------------------

A linha abaixo dispara um script vbs, que devia sendkeys, e funciona, mas só para escrever letras na linha de comando (os Enter não vão); depende da presença do file sendkeys.vbs (q.v.)

```cscript SendKeys.vbs```

para ver uma lista das variáveis vigentes:

```get-childitem -path variable:```

----------------------------

usamos isto aqui em caso de desespero, para colar uma linha de comando, que nao funciona quando passada de dentro de um script, no Clipboard, para daí colar no prompt e dar enter lá:

```

Set-Clipboard -Value "Set`-Variable `-Name `"npp`" `-Value `"C:`\Prog`\notepad`+`+`\notepad`+`+`.exe`" -Option AllScope"

```

----------------------------

-------------------------------------

dá para search string assim:

```

Get-ChildItem -Path .\'.md | Select-String -Pattern 'harari' > apaga.tmp

```

salva resultado no arquivo apaga.tmp

tb dá para salvar o resultado numa variável:

```

(cifrão)minhaVar = Get-ChildItem -Path .\'.md | Select-String -Pattern 'harari'

```

A vantagem desse last método é que permite puxar coisas de dentro da (ou sobre a) variável:

````

PS> (cifrão)A = Get-ChildItem -Path "(cifrão)PSHOME\en-US\'.txt" | Select-String -Pattern 'PowerShell'

PS> (cifrão)A

C:\Program Files\PowerShell\6\en-US\default.help.txt:3:    PowerShell Help System

C:\Program Files\PowerShell\6\en-US\default.help.txt:6:    Displays help about PowerShell cmdlets and concepts.

C:\Program Files\PowerShell\6\en-US\default.help.txt:9:    PowerShell Help describes PowerShell cmdlets

PS> (cifrão)A.Matches

Groups   : {0}

Success  : True

Name     : 0

Captures : {0}

Index    : 4

Length   : 10

Value    : PowerShell

PS> (cifrão)A.Matches.Length

8

PS> (cifrão)B = Get-ChildItem -Path "(cifrão)PSHOME\en-US\'.txt" | Select-String -Pattern 'PowerShell' -AllMatches

PS> (cifrão)B.Matches.Length

9

````

-------------------------------------

nao consegui fazer funcionar o profile!

o start profile deve ficar aqui:

```Current User, All Hosts    (cifrão)Home\[My ]Documents\Profile.ps1```

 You can use the (cifrão)Profile variable in many commands. For example, the

    following command opens the "Current User, Current Host" profile in

    Notepad:

notepad (cifrão)profile

NOVO! este artigo ensina: ev 020320a

e ainda ensina a habilitar um menu AutoComplete estilo linux bash!

To see the current values of the (cifrão)Profile variable, type:

        (cifrão)profile | get-member -type noteproperty

        

Add commands that make it easy to open your profile. This is especially

       useful if you use a profile other than the "Current User, Current Host"

       profile. For example, add the following command:

           function pro {notepad (cifrão)profile.CurrentUserAllHosts}

Para apagar um alias:

          remove-item -path alias:nomedoaliasaremover

          

para ver todos os aliases vigentes

          get-item -path alias:

-------------------------------------

veja "demo_func_with_params.ps1"

muito boa ensinança sobre function aqui: https://ss64.com/ps/syntax-functions.html

### usa o ls para capturar diretamente o caminho path filename nome completo de um arquivo file sem precisar de gambiarras:

`(cifrão)a = ls "vars'.ps1'" | Format-List -property FullName`

também seria possível usar ```Format-List -property Extension``` ou ```Directory```

Para ver todas as -property de uma coisa pela ```Format-List -property '```

E para pegar só o nome sem a extensão, e vice-versa, tem um truque

`(cifrão)a = ls .\arquivo.ext` permite depois: `(cifrão)a.BaseName` que dá "arquivo" e `(cifrão)a.Extension` que dá "ext"

aliás, é mais simples isto:

`dir | select BaseName`

aliás, se você tecla `dir | select` è dá um espaço, pode ir dando tab para ver a lista das propriedades seleciónáveis; e se der uma vírgula depois da primeira que escolheu, pode ir colocando outras !!!

CARALHO!!!!!

para fazer uma variável setada dentro de um script sobreviver e perdurar após a execução do script, coloque ```-Scope Global``` na setagem

Se for setar na forma abreviada, faça assim:

```(cifrão)global:myVar = "xongas"```

By default, all variables created in functions are local, they only exist within the function, though they are still visible if you call a second function from within the first one.

To persist a variable, so the function can be called repeatedly and the variable will retain it's last value, prepend (cifrão)script: to the variable name, e.g. ```(cifrão)script:myvar```. To make a variable global prepend (cifrão)global: to the variable name, e.g. ```(cifrão)global:myvar```

Este é um jeito de quebrar uma linha de comando em várias linhas, para poder comentar item por item:

```

Get-ChildItem               <! list the items               !> `

    -Path   (cifrão)env:windir     <! of the Windows system folder !> `

    -Filter g'.dll          <! that are DLLs                !> `

    -Recurse                <! and search all subfolders    !>

```

Comment based help:

https://ss64.com/ps/syntax-comments.html

exemplo em "buscador.ps1"

para chamar usa ```man nomedoscript.ps1``` e pode acrescentar ```-Examples``` ou ```-detailed```

mas o comment precisa estar na 1ª linha do script

dá para por isso em funções, veja exemplo em "demo_func_with_params.ps1" (o help tem de ser a primeira linha no corpo da função, depois da 1ª chave)

criando scriptblocks

cria como se fosse variable:

```(cifrão)newThing = { Write-Host "Hi! I am in a scriptblock!" }```

È para chamar chama assim (veja o &!!):

```& (cifrão)newThing```

Se você criar scriptblock com param, assim:

```(cifrão)userMsg = { param((cifrão)scriptblockuser) Write-Host "Processing user (cifrão)scriptblockuser..." }```

O user pode, depois, na linha de comando, chamar dando o param:

```& (cifrão)userMsg "fulano de tal"```

Poderia haver mais de um param, tipo:

```param((cifrão)1, (cifrão)2, (cifrão)3)```

Não esquecer que, nesses casos, o script precisa estar previamente carregado na memória, o que se faz como se fosse para usar funções:

```. .\nome_do_script_que_contem_o_scriptblock.ps1```

Aqui há um exemplo que usa vários comandos dentro do scriptblock, onde aprendemos 3 coisas:

```

(cifrão)GetInfo = {

  (cifrão)tag1 = Read-Host 'Enter tag ! or Q to quit'

  if ((cifrão)tag1 -eq 'Q'){Return}

  cls

  sc.exe \\(cifrão)tag1 start RemoteRegistry

  cls

  Start-Sleep -s 2

  cls

  systeminfo /S (cifrão)tag1 | findstr /B /C:"OS Name" /C:"System Boot Time" /C:"System Up Time"

  Get-EventLog system -computername (cifrão)tag1 -InstanceId 2147489657 -Newest 10 |

    ft EventID,TimeWritten,MachineName -AutoSize

  .(cifrão)GetInfo

 }

&(cifrão)GetInfo

```

1º: ifs simples que só tem uma insturção podem ser numa só linha, como ali

2º: parece que dá para usar if sem elseif e else

3º para chamar o scriptblock de dentro do scriptblock mesmo usa ```.(cifrão)``` em vez de ```&(cifrão)``` para evitar que ele loop desde cima

isto usa um scriptblock para criar uma opção de rebootar ele mesmo:

```

(cifrão)commands = {

    Write-Host "do some work"

    (cifrão)again = Read-Host "again?"

    if ((cifrão)again -eq "y"){

        &(cifrão)commands

    } else {

        Write-Host "end"

    }

}

```

Como na linha de reboot usa &(cifrão) e não .(cifrão) ele volta no início

scriptblock é também call "anonymous functions"; vantagem: não precisa ficar no começo do file

veja: isto funciona, com dois ifs e nenhum else ou elseif:

```

(cifrão)x = Read-Host "tecle A"

if((cifrão)x -eq "a"){Write-Host "gênio"}

if((cifrão)x -eq "b"){Write-Host "gênios"}

Write-Host "acabei aqui"

```

isto lista files só com 2 colunas, nome e data:

```ls | Select Name, LastWriteTime```

Se você lista um file para dentro da var, pode pedir pelas -property da var:

```

(cifrão)a = (Get-ChildItem c:\docs\sample.txt)

Write-Host (cifrão)a.fullname (cifrão)a.length (cifrão)a.lastwritetime

```

Para achar os method de um file .ps1 pede:

```Get-ChildItem '.ps1 | Get-Member -membertype method```

Ali descobrimos que ele aceita/tem o method ```MoveTo```

então podemos mandar: ```(cifrão)a.MoveTo("c:\demo files\MyDemoFile.txt")``` (supondo que colocamos esse file na var (cifrão)a)

method são as coisas que o objeto faz ou que dá para fazer com ele

isto serve para jogar um texto num arquivo de dentro de um comando if:

```if ((cifrão)demo -eq (cifrão)null) {Echo 'result' > demo.txt} # this will work```

você pode transcrever uma sessão de PowerShell para um file, assim:

```Start-Transcript -path c:\docs\Text3.txt```

Se precisar passar results ou variáveis enchidas na execução para um arquivo externo, e não der para usar > e >>, estude ```Out-File```

para acabar com os caracteres sujos na parte acentuada, quando usa gc / cat, peça o encoding UTF 8, assim:

```gc "'111143'.md" -Encoding UTF8```

OU: !!!

The output encoding from PowerShell cmdlets is controlled by the (cifrão)OutputEncoding variable, which is by default set to ASCII. You can try to change it to say UTF8:

```(cifrão)OutputEncoding = [ System.Text.Encoding]::UTF8```

Usa só ```(cifrão)OutputEncoding``` para`saber qual está em vigor

```(cifrão)OutputEncoding = [Console]::OutputEncoding``` não entendi nada...

best artigo sb ts:

https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8

onde diz que nao tem jeito, e sugere ts:

```(cifrão)PSDefaultParameterValues['Out-File:Encoding'] = 'utf8'```

===SURPRISE!!

Estas duas linhas (tiradas de https://github.com/PowerShell/PowerShell/issues/4681) parecem ter resolvido o caso!!!

`[Console]::InputEncoding = [System.Text.UTF8Encoding]::new()`

`[Console]::OutputEncoding = [System.Text.UTF8Encoding]::new()`

ou não ... :(

dá para xg as cores na saída ecoada:

```Write-Host "gênios" -ForegroundColor DarkGreen -BackgroundColor White```

parece q pode usar `-f` e `-b` abreviado

The `(cifrão)_` is a variable created automatically by PowerShell to store the current pipeline object; daí pode-se referir a uma (propriedade?) desse objeto: ```Get-ChildItem '.txt | where {(cifrão)_.length -gt 100}```; (cifrão)PSItem é o mesmo

```| Out-Host -paging   ``` é o mesmo que ```more```

esse jeito de listar dá uma saída interressante, só nomes:

```ls | Format-Table -Property name,value -wrap | more```

se abrir um prompt do DOS "cmd" dá para rodar o caret assim:

``"C:\Users\Alberto Luis Marques\AppData\Local\Google\Chrome\Application\chrome_proxy.exe"  --profile-directory=Default --app-id=fljalecfjciodhpcledpamjachpmelml``

Se usar o comando abaixo ele executa um comando dentro de um cmd.exe

`cmd.exe /c comandoprarodar` (por exemplo ``cmd.exe /c dir``

histórico:

`h` para ver a lista numerada

`r xxx` onde xxx é um número da lista, para rodar aquele comando do histórico

para esvaziar uma variable, em vez de removê-la e recriá-la depois:

`clear-item Variable:MyTestVariable`

teoricamente `(cifrão)a = (cifrão)null` deveria resolveir também

add-content

parece um substituto mais forte para > e >>

`add-content -path pets.txt -value (get-content c:\docs\cats.txt)`

copia o conteúdo do cats para o pets

e isto pode ser importante: A function to write one line of text to a log file:

```

function ALog([string] (cifrão)line)

{

   (cifrão)mainLogFile = ".\apaga.tmp"

   Add-Content -Path (cifrão)mainLogFile -Value (cifrão)line

}

PS> . .\nomedoscript.ps1

PS> ALog "minha linha de texto lindo"

```

`Write-Output (cifrão)env:username`

escreve o nome do user

uma amostra de if com mais de uma condição (duplo parênteses); e veja que length e

(cifrão)null podem ser avaliados; e o else pode vir na mesma linha

```

(cifrão)a = Read-Host "e aí"

if(((cifrão)a -ne "(cifrão)null") -and ((cifrão)a.length -ne 1)) { Write-Host (cifrão)a } else { Write-Host "erro" }

```

resumindo, imprime a resposta se não for vazia nem de tamanho 1 dígito

para fazer as merdas das variáveis vazarem persistirem após rodar o script ou scriptblock ou function: Child scopes get access to all the

variables in the parent scope, but changing those variables in the child scope doesn’t

change the version in the parent scope. To create a variable that remains even after the script exits, create it in the GLOBAL scope:

```(cifrão)GLOBAL:variable = value```

To change a scriptwide variable from within a function, supply SCRIPT as its scope name:

```(cifrão)SCRIPT:variable = value```

no pc do fórum o path é:

C:\Users\alms\AppData\Local\Microsoft\WindowsApps

basta por script ali e ele vira global!

para descobrir o path de um PC usa:

`[Environment]::GetEnvironmentVariable("Path", "User")`

captudando substrings "partes de textos" de nomes de arquivos para poder fazer links depois; supondo que um nome completo de file zettel (com ID padronizada) esteja na var (cifrão)a, `(cifrão)a.substring(0,14)` retorna a ID (ie, os 13 1ºs caracteres da var); e `(cifrão)a.substring(15)` retorna o nome todo excluída a ID e o espaço em branco depois dela. v. https://ss64.com/ps/substring.html

depois pode usar `(cifrão)length = (cifrão)a.length` para por a length da (cifrão)a na var (cifrão)lengthm, e daí o comando `(cifrão)a.substring((cifrão)length -3,3)` retorna ".md", isto é, a extensão.

E este: `(cifrão)a.split(".")` divide o nome em duas linhas, no lugar do ponto, na linha 1 fica o nome sem extensão;

isso não estava funcionando porque a cmdlet entrega o resultado do ls como objeto e não como texto; acho que dá para resolver explicitando que a variável a ser enchida com ao resultado da busca tem de ser uma string, assim:

`[string](cifrão)a = ls "'testento'.'"`

Para alterar o prompt e mostrar path atual:

```

function prompt {

    (cifrão)(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }

      else { ** }) + 'PS ' + (cifrão)(Get-Location) +

        (cifrão)(if ((cifrão)NestedPromptLevel -ge 1) { '>>' }) + '> '

}

```

E este faz um prompt qe muda de cor aleatoriamente:

```

function prompt {

    (cifrão)color = Get-Random -Min 1 -Max 16

    Write-Host ("PS " + (cifrão)(Get-Location) +">") -NoNewLine `

     -ForegroundColor (cifrão)Color

    return " "

}

```

Minha versão preferida de prompt por ora: `function prompt { Write-Host ("PS " + (cifrão)(Get-Location) +">") -ForegroundColor DarkGreen -BackgroundColor White }`

esta linha concatena duas variáveis eliminando espaços entre elas (cola uma na outra)

`write-host (cifrão)one (cifrão)two -separator **`

da mesmo forma se você usasse `Write-Host (2,4,6,8,10,12) -Separator "\\ perereca \\ "` ele printaria os conteúdos colocando "\\ perereca \\" entre cada um deles

dá para pré-estabecer param para scripts, não só para function; v. este exemplo:

```

param ( (cifrão)target )

if ( (cifrão)target -eq (cifrão)null ) {

  (cifrão)target = Read-Host "WTF, bro?! Where is my param?"

}

cat "(cifrão)target" | more

```

Se um dia quiser ver melhor o tal no negócio wshell ou wsscript

https://github.com/danieldonda/PowerShell/wiki/WScript.Shell

pelo que entendi F7 e F8 mostram as últimas coisas digitadas (histórico, mas não de comandos rodados)

fontes

Glass TTY VT220

para pegar números aleatórios até máximo de mil e por na var (cifrão)a

`(cifrão)a = get-random -maximum 1000`

para letras aleatórios

`get-random -input a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z  -count 1`

`get-random -input A, B, C, D, E, F, G, H, I, J, K, L, M, N, O, P, Q, R, S, T, U, V, W, X, Y, Z  -count 1`

formatos de tempo data

pega nº de segundos decorridos desde 01011970:

`get-date -UFormat %s`

pega semana do ano: `get-date -UFormat %V`

pega dia do ano: `get-date -UFormat %j`

só os dois últimos dígitos do ano: `get-date -UFormat %y`

pega só os segundos: `get-date -UFormat %S`

v. "idgenerator_newstyle.ps1" que usa isso tudo

para pegar uma data "normal", dd/mm/yyyy: `get-date -UFormat %d/%m/%Y`

projetos em curso:

t3 = try pegar os link do last catched, isolar, por numa var o escolhido; se algo ruim acontecer, a versão que funciona "aleluia!!!" está em "t3_v20200313103219.zip"; versão final em "pegalink.ps1"

?? = buscador que salva os arquivos que têm matches num folder provisório, e nesse folder busca uma 2ª string, salva os files num 2º folder provisório, e nele search uma 3ª string se preciso, e só printa o resultado no fim, até lá só vai copiando os files matches e separando dos demais para permitir uma nova search; como no fim printaria só as lines com a 3ª string, acho que o resultado a printar deve ser só uma lista de files

### editar texto no console terminal:

se vc chama um cmd (nao wk no PowerShell) e manda:

`type con > apaga.tmp`

ele deixa vc escrever à vontade, com quebras de linha e caracteres especiais, e coloca lá dentro, para salvar dê `Ctrl+Z` e Enter.

Se quer append num file que já existe, coloque >> evd >

Dá para chamar pelo PS, assim:

`cmd.exe /c type con > apaga.tmp`

estamos escrevendo no apaga.tmp

Ele funciona bem, desde que você não tente voltar para trás; uma vez que você deu Enter, aquela linha está passada e não pode ser mexida mais. Merda total. Em compensação deixa colar, mas só um pouco, umas três linhas ou quatro, e não reconhece as quebras de linha copiadas.

para ler uma certa linha de um certo file:

`(gc .\listags.txt)[12]`

para ler da linha 9 até a 14, pex:

`get-content listags.txt | select -first 5 -skip 9`

mas sobre isso:

https://stackoverflow.com/questions/14759649/how-to-print-a-certain-line-of-a-file-with-powershell`

menu interativo em PowerShell, v. 73E90g, o artigo está salvo no evernote ev 73E90g; tem um outro, com interface gráfica, 53W77k

AUTOCOMPLETAGEM

Parameter AutoComplete: In PowerShell, when you define a Function, any of your parameter names are automatically compiled and available via autocompletion. (no prompt, bem entendido)

temos um exemplo de autocompletion para os itens constantes do validade-set de cada param, usando tabs, mas não gera menu; 25F71v autocomplete em powershell usa validate set em param de function

para abrir um folder (a pasta) no explorer `ii .`

ATALHOS DE TECLADO

para ver todas as teclas de atalho shortcuts Keyboard

`Get-PSReadlineKeyHandler`

Seleta das melhores:

letra + flecha para cima : srx no histórico pelas entradas que começam com letra

ctrl+r : srx m histórico deixa preencher

ctrl+a : seleciona linha inteira

um exemplo de foreach:

```

get-service | foreach-object {

  if ((cifrão)_.status -eq "stopped") { write-host -f red (cifrão)_.name (cifrão)_.status }

  else { write-host -f green (cifrão)_.name (cifrão)_.status }

}

```

um exemplo de comparação alternativa de condições if que fiz nno braço:

`if ( ( (cifrão)target -eq "coe" ) -or ( (cifrão)target -eq "?" ) ) { &(cifrão)coeRoutine }`

nao esqueça dos parênteses duplos!

MEU KIT zettelKASTEN:

já temos um criador de novo zettel (com ps1 auxiliares para pegar tags com autocomplete)

um catcher para ler os zettel

um buscador

um abridor (para abrir no npp)

um criador de tags novas

PLANO DE MUDAR OS NOMES DOS zettel PARA O ESTILO novo

Por ora, este comando troca "34" para "43" nos nomes de todos os files da pasta: `Get-ChildItem (cifrão)Directory -Recurse | Foreach-Object { Rename-Item (cifrão)_.FullName ((cifrão)_.FullName -replace "34","43")}`

veio daqui: https://serverfault.com/questions/696935/powershell-change-filename-using-first-10-characters-and-mask

esta versão é capaz de pegar os 14 algarismos e jogar no fim da linha; mas o põe depois do .md (!) não consegui fazer funcionar trocando Name por BaseName (!)

```

(cifrão)directory = 'C:\Users\alms\Dropbox\ESCRITOS\zettelkasten\teste'

Get files only

(cifrão)dirs = Get-ChildItem (cifrão)directory

write-host (cifrão)dirs

# loop through each file name

foreach ((cifrão)d in (cifrão)dirs){

    (cifrão)jobNum = (cifrão)d.Name.Substring(0,14)

    (cifrão)restante = (cifrão)d.Name.Substring(15)

    Rename-Item (cifrão)d.Name "(cifrão)restante (cifrão)jobNum"

}

ls

```

essa porra aí funciona no ise MAS NO PS simples não (!)

esta abaixo para resolver, com gambiarras: consegue por a extensão no final, mas com um espaço antes do ponto... testada só na ISE

```

(cifrão)directory = 'C:\Users\alms\Dropbox\ESCRITOS\zettelkasten\teste'

Get files only

(cifrão)dirs = Get-ChildItem (cifrão)directory

# loop through each file name

foreach ((cifrão)d in (cifrão)dirs){

    (cifrão)jobNum = (cifrão)d.Name.Substring(0,14)

    (cifrão)extensao = ".md"

    (cifrão)restante = (cifrão)d.Name.Substring(15)

    Rename-Item (cifrão)d.Name "(cifrão)restante (cifrão)jobNum (cifrão)extensao"

}

Get-ChildItem (cifrão)Directory -Recurse | Foreach-Object { Rename-Item (cifrão)_.FullName ((cifrão)_.FullName -replace ".md 2"," 2")}

```

Parece que isto serve para renomear em casos de strings repetitivas simples:

`Dir | Rename-Item -NewName {(cifrão)_.name -replace "beach_","surfing_trip"}`

Dá para usar -Whatif nesse renames!:

`Get-ChildItem -Filter "'.md" -Recurse | Rename-Item -NewName {(cifrão)_.name -replace 'besta', 'bolso' } -whatif`

RESOLVIDO; a solução que funcionou é o "renovaStyle.ps1"; explicações lá; algumas coisas foram feitas no NexusFile pq era mais simples (v. tb o "renovaEncyclo.ps1", mais simples).

esta linha mágica converte um arquivo utf8 para ansi de modo que o ps consegue ler e não precisaremos abandonar o maldito caret (que só entende UTF8)

`Get-Content -Path "origem.md" -Raw -Encoding utf8 | Out-File "destino.md" -Encoding utf8`

inexplicavelmente depois percebi que a linha manda pegar utf8 e converter para utf8 mesmo! mas assim funciona! mas se troca por ansi, funciona igual! :0

agora incorporar isso no catcher!

nota: se coloca ANSI no final, evd utf8, o darkwingduck diz que nao existe,e trava o script. Se deixa UTF8 lk formato de destino, funciona (!!)

**' update

dmg basta usar `gc 'nomedofile' -Raw -Encoding utf8 | more` para obter uma saída acentuada, não precisa toda aquela gambiarra de conversor !!!!

resumo das expressões lógicas booleanos avaliação comparação eval para param e variáveis:

- Assignment : += -= '= /= ## -- (e.g. ++(cifrão)int or (cifrão)int## or (cifrão)int += 1)

- Equality : -eq -ne -gt -ge -lt -le

- Matching : -like -notlike (wildcard), -match -notmatch (regex; (cifrão)matches contains matching strings)

- Containment : -contains -notcontains -in -notin

- Type : -is -isnot

- Logic : -and -or -xor -not or ! (e.g. (cifrão)a -and (cifrão)b or -not (cifrão)a or !(cifrão)a)

- Replacement : -replace (replaces a string pattern)

v. também <https://github.com/danieldonda/PowerShell/wiki/Operadores-Condicionais-e-L%C3%B3gicos>

uma coisinha simplinha que funciona com um buscador na linha de comando:

`(cifrão)a = "algumacoisa"`

`(cifrão)b = ls '(cifrão)a'.md | select Basename | more` (lista os resultados com algumacoisa)

`(cifrão)b` (lista os resultados armazenados na var)

a function "rask" no zettel_functions.ps1 mostra como acrescentas linhas em um file usando a linha de comando

`(cifrão)a = ls "'(cifrão)target'"`

### cacete! parece que essas aspas cercando o alvo de busca fazem toda a diferença entre get uma string com o caminho ou um objeto complexo que nao presta para nada!!

`Get-ChildItem | Foreach-Object { "Chama-se: " + (cifrão)_.BaseName }`

Isso lista os files e dá os BaseName usando uma cmdlet Foreach-Object

exemplo de looping usando a função `while` que funciona (tem que . .\carregar antes de chamar a function testaloop)

```

function testaloop {

    (cifrão)response = ""

    while((cifrão)response -ne "QUIT")

    {

    (cifrão)response = Read-Host "Type something"

    }

}

```

## olha que genial, isto cria uma linha de --- com a exata largura da var (cifrão)header:

```

(cifrão)header = "Report for Today"

(cifrão)myString = "(cifrão)header`n(cifrão)('-' ' (cifrão)header.Length)"

```

tb dá p/ mk isto aqui: `(cifrão)myString = ('-' ' 89)` para multiplicar o - 89 vezes!!

subexpressions

variables dentro de (), que o ps calcula antes, e preenche o valor da variables

pex `(cifrão)a = "por favor escreva " + ( ls "'mitoco'" )` escreve a frase e o dir do file chamado mitoco

nao entendi direito como faz, mas jogar a saída numa out-string pega só os caminhos, sem frescuras (como texto e nao como objeto)

```

(cifrão)output = New-Object System.Text.StringBuilder

Get-ChildItem .\'(cifrão)a' -Recurse |

Foreach-Object { [void] (cifrão)output.AppendLine((cifrão)_.BaseName) }

(cifrão)output.ToString()

```

no caso do exemplo, vc tem de fornecer o param `(cifrão)a`, que pode ser uma string de texto com espaços e caracteres especiais

parece que gera uma string chamada output e ela é uma string de texto, e nela vai apensando as linhas para cada resultado.

ESTUDANDO STRING SELECT

When the output of a Select-String command is sent down the pipeline to another Select-String command, the receiving command searches only the text in the matched line.

Example 9: Find all pattern matches. This example shows how the AllMatches parameter finds each pattern match in a line of text. By default, Select-String only finds the first occurrence of a pattern in a line of text. This example uses object properties that are found with the Get-Member cmdlet.

(cifrão)A.Matches

Value    : aquiloquevocêmandouachar!

talvez dê para aproveitar a opção -Delimiter do Get-Content

isto aqui faz a mesma coisa que fazemos com o buscador de conteúdo content:

`gc '.md | Where-Object {(cifrão)_ -like **harari**}`

olha que interessante

este comando: `ls 17'.md -Recurse | select BaseName` gera um tipo de relatório, com título para encher o saco

este outro: `ls 17'.md -Recurse -Name` gera a mes a lista mas só os nomes, sem frescuras!

só que isto aqui acha 4 files: `ls "'astrologia'" -Recurse | select Name`

e isto aqui não acha nenhum! `ls "'astrologia'" -Recurse -Name`

ou seja, a opção de baixo, melhor pra mim, não recursa! cacete!

o -Recurse funciona com uma opção -File (o velho dir do DOS) mas não com a chave -Name

se usar `ls "'astrologia'" -Recurse -File` ele recursa, mas pega os fullpaths de tudo, e entrega numa única linha de texto!; daí, usando esta expressão, consegui extrair desa linha única só as IDs novas, cada uma numa linha:

`(cifrão)regex = '\d\d\w\d\d[?a-z]'`

se você faz `ls "'(cifrão)1'" -Recurse | select basename > teste.tmp` o file recebe um array, um file em cada linha, com cabeçalho;

mas se faz assim também resulta em array com cabeçalho:

```

(cifrão)a = ls "'(cifrão)1'" -Recurse | select basename # voltamos à versão antiga

(cifrão)a | more

echo (cifrão)a teste.tmp

```

A 1ª linha pega o texto integral do file, a linha 2 pede só a linha 1 do file e a 3ª pede a linha 16; e funciona#### (a ideia veio de https://www.business.com/articles/powershell-read-text-files/) (m vdd o nº (1) pega a 2ª linha do arquivo e o nº [16] pega a line 17)

```(cifrão)a = gc .\buscador.ps1

(cifrão)a[1]

(cifrão)a[16]

```

The -like command is like -match except it does not use regex. It uses a simpler wildcard pattern where ? is any character and ' is multiple unknown characters.

`(cifrão)message -like **error**`

 string replacement:

 PS> `(cifrão)message = "Hi, my name is Dave."`

 PS> `(cifrão)message.replace('Dave','Kevin')`

 Hi, my name is Kevin.

 

isto aqui splita um texto no espaços em branco:

`(cifrão)a = "06P45y teste de nome idiota"`

`(cifrão)a -split '\s'`

vai dar uma coisa assim:

```

06P45y

teste

de

nome

idiota

```

daí podemos jogar isso num file, e depois grabar só a 1ª linha:

```

(cifrão)a -split '\s' > teste.tmp

(cifrão)b = gc .\teste.tmp

(cifrão)b[0]

```

vai dar 06P45y, que é o queremos, a id do file; e sem usar regex!!!

MAS daria para conseguir o mesmo result (capturar uma ID de 6 dígitos no início de uma linha contendo um nome completo de file) usando regex assim (supondo que (cifrão)2 contenha uma linha tipo "06P45y teste de nome idiota":

```

echo (cifrão)2 > srxn.tmp

(cifrão)regex = '^[a-z0-9]{6}' ! pega ID nova ou velha tudo na mm linha com espaços; o segredo para extirpar o resto do nome é o ^ no começo da expressão: ele informa que o match tem de estar num começo de linha!

select-string -Path .\srxn.tmp -Pattern (cifrão)regex -AllMatches | % { (cifrão)_.Matches } | % { (cifrão)_.Value } > srxn2.tmp

Write-Host 'deu isto'

gc srxn2.tmp # debug

pause # debug

```

https://www.regular-expressions.info/refwordboundaries.html

aprendi a pesquisar por string no content do file e entregar uma lista numerada dos files matcheados, evd uma lista das linhas contendo o match; v. "zs2.ps1"

achei um jeito de copiar files constantes de uma lista para uma pasta, o que é a base da ideia da pesquisa recursiva## v. "copia_arquivos_para_subfolder.ps1"; o projetos respectivo (da search recursiva) vai em t3.ps1

PASSOS:

1. capta até 5 param na cmdline

2. joga cada um em um param do script

3. enche param vazios com nadaveh

4. faz a busca normal em zp pelo param1

5. lista os results em teste.tmp

    até aqui é a rotina normal (exceto o passo 1), mas em vez de cair na rotina de entrega

6. copia os files matcheados para \tmp

7. seta o folderToSearch para \tmp????

7. cd para \tmp

8. faz nova search, dentro do \tmp,  pelo param2, lista os results em teste.tmp

9. copia os files matcheados para \tmp2

10. cd para \tmp2

8. faz nova search, dentro do \tmp2,  pelo param3, lista os results em teste.tmp

9. copia os files matcheados para \tmp3

10. cd para \tmp3

11. faz nova search, dentro do \tmp3,  pelo param4, lista os results em teste.tmp

9. copia os files matcheados para \tmp4

10. cd para \tmp4

11. 11. faz nova search, dentro do \tmp4,  pelo param5, lista os results em teste.tmp

9. move o teste.tmp do \tmp4 para o zp

10. cd zp

11. deleta os tmp todos

11. rotina de entrega

sobre isso acima:

**notar que daria para fazer tudo isso** (ie, uma search por vários termos e operador booleano AND) com uma linha só de comando, como se vê em <https://stackoverflow.com/questions/43450914/how-to-use-findstr-in-powershell-to-find-lines-where-all-words-in-the-search-str>

A solução para achar se um file contém uma string foi achada em:

<https://stackoverflow.com/questions/18633666/powershell-using-contains-to-check-if-files-contain-a-certain-word/18634071>

e implementada no catcher v10.4.7; em suma, é:

```

  (cifrão)target = gc srxn.tmp

  (cifrão)wordToFind = '^(09)'

  (cifrão)containsWord = (cifrão)target | %{(cifrão)_ -match (cifrão)wordToFind}

  If((cifrão)containsWord -contains (cifrão)true) { Write-Host "sim!" }

  else {  Write-Host "no!"  }

```

uma solução para grabar só os 1ºs 6 caracteres de 1 linha de texto (no caso, o file só tinha 1 linha, logo pegamos um link)

```

(cifrão)data = get-content "srxn.tmp"

(cifrão)y = foreach((cifrão)line in (cifrão)data) {

    (cifrão)line.substring(0, 6) ## 0 é o caracter 1, e 6 é o 6 mesmo, porque ele não significa o 6º caractere, mas o 6º contado do 1º algarismo, o 0; Se pusesse 2,6 em vez de 0,6, ele pularia os 2 primeiros e pegaria os 6 seguintes, o que é útil se na linha que contém o link houver [[ no início!

}

ls (cifrão)y'

```

sobre regex e lookarounds (olhar em volta, como Lookbehind (olhar atrás) e lookahead (olhar à frente)),v.

<https://github.com/ziishaned/learn-regex/blob/master/translations/README-pt_BR.md#o-que-%C3%A9-uma-express%C3%A3o-regular>

melhor instrução sobre tutorial de regex, em português

[[58H35s]] bom exercício para grabar todas as tags de um zettel, estejam em que linhá estiverem, independente de haver 2 ou mais numa linha, sem repetições, em ordem alfabética, tudo numa linha com espaço em branco separando; aprendi a cortar a 1ª line de um file, concatenar linhas, usar regex, ordenar, pegar substrings de linhas do texto;

<# funções de conta linhas e acusa script, para usar em debugagem

  no file que vai usar essas funções cole estas 4 linhas:

  

      (cifrão)a = Get-CurrentFileName

      (cifrão)c = ls "(cifrão)a" -Name

      (cifrão)b = Get-CurrentLineNumber

      Write-Host "`(Debug info: this is line"(cifrão)b "of script"(cifrão)c"`)" -foregroundColor gray

!>

function Get-CurrentLineNumber { (cifrão)MyInvocation.ScriptLineNumber }

function Get-CurrentFileName { (cifrão)MyInvocation.ScriptName }

listar files por ordem decrescente de data (só '.md), recursivo:

`gci -rec -file '.md | sort LastWriteTime -Descending | select-object name,lastwritetime | more`

esta versão pega os últimos 30 (o que cabe numa tela)

`gci -rec -file '.md | sort LastWriteTime -Descending | select-object name,lastwritetime | Out-File "listfiles.tmp" | cat "listfiles.tmp" -First 30`

Este comando lista os files da pasta, recursivamente, e ordena coloca põe em ordem por tamanho size Length:

`gci | Sort-Object -Property Length | Select -First 15`

para rodar um script em segundo plano (background); mas tem de abrir uma janela para executar isso, senão fecha a sua janela atual

`Powershell.exe -windowstyle hidden -file C:\iis_test.ps1`

uma função para pedir uma choice com time limit e default option:

```

function Read-KeyOrTimeout {

    Param(

           [int](cifrão)seconds = 5,

        [string](cifrão)prompt = 'Hit a key',

        [string](cifrão)default = 'A'

    )

    (cifrão)startTime = Get-Date

    (cifrão)timeOut = New-TimeSpan -Seconds (cifrão)seconds

    Write-Host (cifrão)prompt

    while (-not (cifrão)host.ui.RawUI.KeyAvailable) {

        (cifrão)currentTime = Get-Date

        if ((cifrão)currentTime -gt (cifrão)startTime + (cifrão)timeOut) {

            Break

        }

    }

    if ((cifrão)host.ui.RawUI.KeyAvailable) {

        [string](cifrão)response = ((cifrão)host.ui.RawUI.ReadKey("IncludeKeyDown,NoEcho")).character

    }

    else {

        (cifrão)response = (cifrão)default

    }

    Write-Output "You typed (cifrão)((cifrão)response.toUpper())"

}

Read-KeyOrTimeOut

```

para saber em que nível de prompt nestado estamos:

`Get-Variable NestedPromptLevel`

àliás `Get-Variable` lista todas as vars vigentes

para abrir um saite e escolher o navegador não-padrão:

```

(cifrão)a = "www.nomedosaite,com"

start-process "C:\Program Files\Mozilla Firefox\firefox.exe" (cifrão)a

```

teoricamente ts deveria rodar um script em 2º plano

`(cifrão)myjob = start-job -filepath .\t3.ps1`

e teoricamente isto pegaria o result

`(cifrão)results = receive-job -job (cifrão)myjob`

PARECE UTILIÍSSIMO

ensina os Powershell equivalentes do awk do linux, que serve, pex, para manter várias entradas de banco de dados num csv (entre as vírgulas ficam as colunas) e resgatar só uma determinada coluna, ou o total, ou só os registros que contém certa info...

<http://windows-powershell-scripts.blogspot.com/2009/06/awk-equivalent-in-windows-powershell.html>

tirado dali para wk com nosso majorHistoryList

```

Get-Content .\majorHistoryList.csv | %{ (cifrão)_.Split('`|--`|')[0,12,16]; }

0 é data

4 é id

8 é basename

12 é fullname.ext

16 é pater

(cifrão)whatoToFind = Read-Host "what?"

Get-Content .\majorHistoryList.csv | %{ if ((cifrão)_.Split('|--|')[-1] -match "[(cifrão)whatoToFind]") { (cifrão)_; } } # na linha acima, -1 é o last field; se trocar por 12 é o fullname; falta saber como preencher o (cifrão)whatoToFind q é um regex

# notar que o split num csv devia ser vírgula mas no nosso é |--|

```

olha que interessante, para append data num file, equivalente a `echo x >> y`

`add-content -value (get-content D:datalarge.txt) simple.txt`

interessante: isso gc o file numa janelinha à parte tipo popup e selecionável!

`gc file.ext | Out-GridView -OutputMode Multiple -Title "Logon for Last 10 Users"`

[[50H94u]] cheat sheets de comandos do powershell

debugstuff padrão:

!----------------------------------------!

  Write-Host ** # debug

  Write-Host ** # debug

  Write-Host '---------------------------------------------------------------------' # debug

  Write-Host '(cifrão)algo is' (cifrão)algo # debug

  gc (cifrão)algo # debug

  Write-Host '---------------------------------------------------------------------' # debug

  Write-Host ** # debug

  Write-Host ** # debug

  pause # debug

!----------------------------------------!

para obter informação app o computador:

`(cifrão)thisComputer = Get-CimInstance -ClassName Win32_ComputerSystem`

depois você pode usar `(cifrão)thisComputer.name`, por exemplo, para saber o nome da máquina

usar isso para automatizar a escolha de máquina no pathfixer

com esta linha dá para pegar os last 20 LWF, grabar a partir da cl, e abrir num delivey completão:

`gc .\minorHistoryList.tmp -tail 20 | get-unique > tmp.tmp | funkGlobalDelivery tmp.tmp 2`

quando entra num "more" de ujm file com milhões de linhas, para ir direto para o final tecla h e depois q

[[59Y58j]] powershell to display determinadas linhas de um file (24/04/2020)

----------------------------------------

```powershell
(cifrão)a = gc .\catcherTemporaryFileList.tmp | sls -simple 'prestígio

(cifrão)a.LineNumber # retorna o número da linhá que contém o match

gc teste2.tmp | select -Skip 3 (para ler o file começando da line 4 em diante)

```


para apagar as linhas em branco empty lines num arquivo:

`(gc file.txt) | ? {(cifrão)_.trim() -ne "" } | set-content file.txt`

? is an abbreviation for "where-object". Essentially, an "if" statement

-ne is an operator that means "not equal to"

trim() is a method removes lines that contain spaces but nothing else which is what I needed in my case.

**tentando criar uma busca com duas palavras dois termos:**

entrega 2 de 4 results (aparentemente não pega tags)

Get-ChildItem -Filter **.md' -Recurse | Get-Content | Where-Object {  (cifrão)_ -like **bolsonaro** -and  (cifrão)_ -like **datafolha** } | foreach-object { echo (cifrão)_.filename }

achou 1 entre 4 results:

Get-ChildItem -Filter '.md -Recurse | Select-String -Pattern '^(?=.'\bbolsonaro\b)(?=.'\bdatafolha\b).'(cifrão)'

achou 177 de 4 results:

(Get-ChildItem -File -Filter '.md -Recurse |

  Select-AllStrings -SimpleMatch bolsonaro, datafolha).Count

Get-ChildItem -Recurse '.md | Select-String "bolsonaro" | Select-Object -Unique Path

parece funcionar, mas é um OR evd um AND:

(Get-ChildItem -File -Filter '.md -Recurse |

  Select-String -SimpleMatch -Pattern 'bolsonaro', 'datafolha') | foreach-object { echo (cifrão)_.filename } |get-unique

  

  

  

  

  

  

  

  

no notepad## npp para achar quebras de linhas da busca extendida:

`\n\r`

para limpar, no notepad++, os arquivos de frases grifadas do google play books

isto é para apagar as linhas com as datas:

`^[0-9]{1,2}\s(de)\s.'`

isto pega as linhas com números de páginas

`^[0-9]{1,4}(cifrão)`
```