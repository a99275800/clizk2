---
{"dg-publish":true,"permalink":"/20231017192337-reaprendendo-powershell-do-zero-em-2023/","dg-note-properties":{}}
---

akin: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]
parent: [[231017c Ajuda do Powershell _index top\|231017c Ajuda do Powershell _index top]]
tags: #proj_zetteltex #zettelkasten #ajuda #internas #admin #tech #powershell 

## para por na tela o texto do file com acentos e sem zueira (encoding)

```powershell
gc '.\nome do file' -Encoding utf8
```
o `gc` printa o conteúdo; o `-Encoding utf8` faz a magia; o nome do file dá para autocompletar, mas tem de acertar a primeira letra do nome; não precisa por o `.\`, o PS completa isso! (Se teclar o Tab, né).
Se acrescentar um ` | more` no fim vai pondo tela por tela (só que não está funcionando). 
Esta opção:
```Powershell
gc 'Platão.md' -Encoding utf8 | %{ "(cifrão)((cifrão)_.ReadCount) (cifrão)_" } | more
```
imprime os números de linhas;
## pedir ao user que preencha uma var chamada (cifrão)1
```Powershell
(cifrão)1 = Read-Host "Wich line to grab? (or ask for [M]ore)"
```
Para ver o que a VAR contém, envia o nome dela: `(cifrão)1`, por exemplo
## busca palavras nos files da pasta
[[20231017191442 script Powershell para buscar pesquisar varias strings de texto numa pasta de files\|20231017191442 script Powershell para buscar pesquisar varias strings de texto numa pasta de files]]]
## este busca os files mas entrega a lista na interface gráfica
```powershell
dir -file -r -ea 0 'C:\Users\a9927\Dropbox\astolfo S2 alberto\OZ' | Select FullName | out-gridview
```
não permite fazer nada com os arquivos da lista gerada, salvo copiar para o clipboard, o que pode ajudar; na tal interface gráfica tem um campo de filtrar que pesquisa na lista e filtra, muito útil. Depois dá para selecionar os files filtrados e copiar para o clipboard.
```powershell
dir -file -r -ea 0 'C:\Users\a9927\Dropbox\astolfo S2 alberto\OZ' | Select FullName | out-gridview
```
```powershell
dir -file -r -ea 0 | Select Basename | out-gridview # esta opção age na pasta em que você estiver (caminho relativo, em vez de absoluto como acima) e lista só os basenames
```
## busca por string nos nomes dos files e deixa escolher um resultado para por nome dele no clipboard
[[busca por string nos nomes dos files e deixa escolher um resultado para por nome dele no clipboard\|busca por string nos nomes dos files e deixa escolher um resultado para por nome dele no clipboard]]
## para capturar apenas o nome e extensão de um file
```powershell
ls '.\Platão.md'  | Select Name # poderia por Basename em lugar de Name
```
## script para escolher aleatoriamente um file da pasta e mostrar seu conteúdo
```powershell
cls
(cifrão)a = dir "*.md" -Recurse | Get-Random
gc (cifrão)a -Encoding utf8 | out-host -paging
```
A parte o `out-host -paging` deveria funcionar como o `more` mas nenhum deles funciona aqui
## incrementando: escolhe zettel aleatório e abre (roda) no NPP
```powershell
cls
(cifrão)a = dir "*.md" -Recurse | Get-Random
start (cifrão)a
```
A parte o `out-host -paging` deveria funcionar como o `more` mas nenhum deles funciona aqui
## demo de funções no Powershell
[[20231019213023 demo de funcoes no Powershell\|20231019213023 demo de funcoes no Powershell]]]
## string para ler as últimas 5 linhas de um file
```powershell
Get-content -tail 5 -Encoding utf8 '.\nome_do_file'
``` 
## adicionar acrescentar string no clipboard sem replace
```powershell
	Set-Clipboard -Append <string> # poderia ser uma (cifrão)var
``` 
## para chamar dentro do script x uma function do script y
basta escrever o nome da function na linha onde ela deve ser executada, sem mais nada; mas o script y precisa estar previamente loaded `. .\scripty`
## comando wait
```powershell
Start-Sleep -s 1 # !!! este é o comando Wait!!!
``` 
## para apagar a 1ª linha de um files 
```powershell
(Get-Content (cifrão)file | Select-Object -Skip 1) | Set-Content (cifrão)file
``` 
## para ler apenas a 1ª linha de um file 
```powershell
(Get-Content (cifrão)file | Select-Object -First 1)
```
## substituir string de texto dentro de um files 
```powershell
    (cifrão)paraApagar = "innbox"
    (cifrão)paraPorNoLugar = ""
    ((Get-Content -path (cifrão)x -Raw) -replace (cifrão)paraApagar,(cifrão)paraPorNoLugar) | Set-Content -Path (cifrão)x -Encoding UTF8
``` 
## substituir uma linha inteira de um files 
supondo, claro, que você sabe exatamente qual o nº da linha; e não esquece aquele troço que o PS conta a 1ª linha como 0...
```powershell
  (cifrão)fileOfInterest = gc (cifrão)x
  (cifrão)linhaDasTags = (cifrão)fileOfInterest[2]
  (cifrão)linhaDasTagsNova = "(cifrão)linhaDasTags ktd" # esse ktd devia ser precadido por uma hashtag mas apaguei porque estava endoidando o Obsidian
  ((Get-Content -path (cifrão)x -Raw) -replace (cifrão)linhaDasTags,(cifrão)linhaDasTagsNova) | Set-Content -Path (cifrão)x -Encoding UTF8
``` 
## script para achar e substituir strings dentro de um file
 [[powershell ps1 script para achar e substituir strings dentro de um file\|powershell ps1 script para achar e substituir strings dentro de um file]]
## linha para listar so 10 arquivos alterados por último (só basename)
```powershell
ls *.md | Sort-Object LastWriteTime -Descending | Select-Object -First 10 | Select Basename
```
Se ecoar isso para dentro de um txt, e apagar a 1ª linha (onde estará escrito (BaseName) e a 2ª que terá ------------, temos uma lista que pode ser usada para criar links internos.
## linha para ver os 10 processos rodando com mais carga em CPU
gps | Sort-Object CPU -Descending | Select-Object -First 10
## para contar quantos files `*.md` há na pasta 
```powershell
(Get-ChildItem *.md).Count
```
## para achar uma palavra nos nomes de files mas retornar apenas a lista dos basenames dos matches, não os fullnames (bom para criar links)
```powershell
Get-ChildItem | where { (cifrão)_.Basename | Select-String -Pattern "(cifrão)bosta" 
} | select -expand basename
```
## acrescentar `[[` no início de cada linha de (cifrão)file
```powershell
Get-Content -Path (cifrão)file |
>>     ForEach-Object {
>>         (cifrão)_ -replace ( "^.*" , "`[`[`(cifrão)0" )
>>     } | Set-Content -Path (cifrão)newfile
```
onde os dois abre colchetes precedidos de backtick são a expressão a antepor ao início de cada linha, e o resto dos símbolos significa "resto do texto da linha". Pode substituir os colchetes por outra coisa
A rotina acima funciona, mas não sei porque. Notar que tivemos de mudar isso num outro script quase igual:
```powershell
(cifrão)paraApagar2 = "[`[`[]" # vamos deletar abrecolchetes (lembre-se: um caracter literal, ou uma sequência de caracteres literais, tem de estar dentro de colchetes, logo um colchete literal tem de estar dentro de uma casinha de colcletes não-literais)
	(cifrão)paraApagar3 = "[`]`]]" # vamos deletar fecha-colchetes
    (cifrão)paraPorNoLugar2 = "" # e substituir por nada
    ((Get-Content -path (cifrão)file -Raw) -replace "(cifrão)paraApagar2",(cifrão)paraPorNoLugar) | Set-Content -Path (cifrão)outroNewFile -Encoding UTF8 # fazendo a substituição
```
Aí, não funcionou. Como diz no comment: quando se trata de regex (expressões regulares) um caracter literal, ou uma sequência de caracteres literais, têm de estar dentro de colchetes, logo um colchete literal tem de estar dentro de uma casinha de colcletes não-literais
## editar texto no console terminal:
A REVISAR / CONFERIR: se vc chama um cmd (nao wk no PowerShell) e manda:
`type con > apaga.tmp`
ele deixa vc escrever à vontade, com quebras de linha e caracteres especiais, e coloca lá dentro, para salvar dê `Ctrl+Z` e Enter.
Se quer append num file que já existe, coloque >> evd >
Dá para chamar pelo PS, assim:
`cmd.exe /c type con > apaga.tmp`
estamos escrevendo no apaga.tmp
Ele funciona bem, desde que você não tente voltar para trás; uma vez que você deu Enter, aquela linha está passada e não pode ser mexida mais. Merda total. Em compensação deixa colar, mas só um pouco, umas três linhas ou quatro, e não reconhece as quebras de linha copiadas.
## criar uma nested powershell promt e rodar um file 
```Powershell
powershell -File .\test3.ps1
```
 
Pode por isso dentro de um script que funciona
Em vez de um  um file, poderia por `-Command` e um comando
## um editor interno no PS?
```Powershell
Install-Module -Scope CurrentUser psedit
```
## para concatenar (juntar) as linhas de um file 
veja abaixo jeito mais simples 
```Powershell
(cifrão)fileToBeCoisado = ".\apaga isto bem depressa.md"
(cifrão)resultFile = "OZ_concatenateTempFile.tmp"
(cifrão)text = (Get-Content (cifrão)fileToBeCoisado ) -join "`l`l"
echo (cifrão)text > (cifrão)resultFile
(cifrão)paraApagar = "llll" # não sei porque, aquele `l`l do -join acima vira llll no texto...
(cifrão)paraPorNoLugar = "`(...`) " # e substtuí-la pelos fecha-colchetes
((Get-Content -path (cifrão)resultFile -Raw) -replace (cifrão)paraApagar,(cifrão)paraPorNoLugar) | Set-Content -Path (cifrão)resultFile -Encoding UTF8 # fazendo a substituição
(cifrão)paraApagar = "ll" 
(cifrão)paraPorNoLugar = " - " # e substtuí-la pelos fecha-colchetes
((Get-Content -path (cifrão)resultFile -Raw) -replace (cifrão)paraApagar,(cifrão)paraPorNoLugar) | Set-Content -Path (cifrão)resultFile -Encoding UTF8 # fazendo a substituição
(cifrão)paraApagar = "- - " 
(cifrão)paraPorNoLugar = "" # e substtuí-la pelos fecha-colchetes
((Get-Content -path (cifrão)resultFile -Raw) -replace (cifrão)paraApagar,(cifrão)paraPorNoLugar) | Set-Content -Path (cifrão)resultFile -Encoding UTF8 # fazendo a substituição
gc (cifrão)resultFile
del (cifrão)resultFile
```
Tenho certeza de que isso é jequice e tem um jeito mais fácil 
## como pesquisar comandos cujo nome não sabemos completamente 
```Powershell
Get-Command | Where { (cifrão)_.Name -like '*Process*' }
```
Esse `where` é bem útil, funciona com todos os comandos, e o `-like` eu também não sabia. Veio daqui: https://www.youtube.com/watch?v=IYUQBMkJlmc&t=235s
```Powershell
Get-Command '*process*'
```
faz a mesma coisa
## para apagar as 2 primeiras linhas de um arquivo
``` Powershell
(Get-Content (cifrão)provisResultFile | Select-Object -Skip 2) | Set-Content (cifrão)provisResultFile # isto deleta as duas primeiras linha de file (linha de título)
```
funciona!
## para juntar todo o arquivo numa linha só (concatenar), jeito mais simples
```Powershell
  Get-Content .\blu.blu | foreach { # para concatenar o arquivo todo numa linha só
   (cifrão)out = (cifrão)out + (cifrão)_ + " " # acrescenta o espaço em branco entre as tags
  }
```
PARECE QUE ISSO NÃO FUNCIONA
## para pegar só uma determinada linha do fileOfInterest 
```Powershell
(cifrão)linhaDoParent = (cifrão)fileOfInterest[3] # 3 é a linha 4, porque a contagem começa em 0
```
## jeito simplinho de substituir strings dentro de uma variável
```Powershell
(cifrão)paterLimpasMesmo2 = (cifrão)paterLimpas.replace(']]','')
```
## pegar a data no formato dd/mm/aaaa 
```Powsershell
get-date -UFormat %d/%m/%Y
```
## pegar só os caracteres 2 a 55 de uma string 
```powershell
(cifrão)b = (cifrão)a.substring(2,55)
```
daria para pegar um pedaço de uma propriedade de um file, assim:
```powershell
(cifrão)a = (cifrão)umFileValido.basename.substring(0,6)
```
## para checar se uma var ou string contém um Número
```powershell
(cifrão)a -is [int]
```
## único jeito de expandir uma var e concatenar com letras, espaços, texto em geral:
```powershell
(cifrão)asterisco = '*'
(cifrão)b = (cifrão)asterisco+(cifrão)nossaVariavelAExpandir+(cifrão)asterisco
```
N.B.: se você digita isto: `Get-ChildItem *(cifrão)parteConfiavelDoNomeDoFile*` o PS aceita (ou seja, pode concatenar assim se for um comando; mas não funciona se quiser usar a mesma informação `*(cifrão)parteConfiavelDoNomeDoFile*` para encher uma segunda var, nesse caso tem de usar a gambiarra acima)
## conferir se o conteúdo da var está dentro de um validate set
```powershell
(cifrão)asterisco = '*'
(cifrão)userAnswerBetweenAsterisks = (cifrão)asterisco+(cifrão)lineNumberSelected+(cifrão)asterisco
(cifrão)validateSet = "1 2 3 4 5 6 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60 61 62 63 64 65 66 67 68 69 70 71 72 73 74 75 76 77 78 79 80 81 82 83 84 85 86 87 88 89 90 91 92 93 94 95 96 97 98 99 100 101 102 103 104 105 106 107 108 109 110 111 112 113 114 115 116 117 118 119 120 121 122 123 124 125 126 127 128 129 130 131 132 133 134 135 136 137 138 139 140 141 142 143 144 145 146 147 148 149 150 151 152 153 154 155 156 157 158 159 160 161 162 163 164 165 166 167 168 169 170 171 172 173 174 175 176 177 178 179 180 181 182 183 184 185 186 187 188 189 190 191 192 193 194 195 196 197 198 199 200 201 202 203 204 205 206 207 208 209 210 211 212 213 214 215 216 217 218 219 220 221 222 223 224 225 226 227 228 229 230 231 232 233 234 235 236 237 238 239 240 241 242 243 244 245 246 247 248 249 250 251 252 253 254 255 256 257 258 259 260 261 262 263 264 265 266 267 268 269 270 271 272 273 274 275"
(cifrão)isOrNotValid = (cifrão)validateSet -like (cifrão)userAnswerBetweenAsterisks
if ( (cifrão)isOrNotValid -eq (cifrão)false ) { echo "fudeu" } else { echo "deu bom" }
```
## para captar / contar o total de linhas de um file 
```powershell
(Get-Content 'meufile' | Measure-Object -Line).Lines
```
## apagar as linhas em branco de um file 
```powershell
gc .\file1.txt | where {(cifrão)_ -ne ""} > .\file2.tmp
```
## lê só a última linha de um file 
```powershell
Get-content (cifrão)file -tail 1.
```
## pega o texto de um arquivo pulando a 1ª linha e as últimas 4
```powershell
(cifrão)fileContent = Get-Content .\someFile.txt
(cifrão)fileContent[1..(cifrão)((cifrão)fileContent.Count - 4)]
```
a 1ª é excluída porque dentro dos colchetes  aparece o `1..` e suponho que a contagem comece no zero, se quisesse excluir as duas primeiras colocaria `2..` . E no `Cont - 4` o 4 pode ser substituído pelo número de linhas que quisermos cortar
## para tocar um beep
```powershell
Write-Host -NoNewLine "`a"
```
## uma barra de progresso progressbar
```powershell
for ((cifrão)i = 1; (cifrão)i -le 100; (cifrão)i++ ) {
    Write-Progress -Activity "Loading Zettelkasten" -Status "(cifrão)i% Complete:" -PercentComplete (cifrão)i
    Start-Sleep -Milliseconds 5
}
```
precisa por dentro de um loop como esse `for` aí
pode ajustar os milisegundos, acho
## ecoa as linhas do file uma por uma com pausa de milissegundos regulável
```powershell
foreach((cifrão)line in Get-Content .\nomeDoFile.ext) {
    if((cifrão)line -match (cifrão)regex){
        echo (cifrão)line
		start-sleep  -Milliseconds 45
    }
}
```
aí menciona um regex que não consta do exemplo, mas testei e funciona sem encher essa variável 
suponho que no lugar do `echo (cifrão)line` etc daria para por qualquer comando que possa ser aplicável à linha
## toy: lista os arquivos com falsa progress bar 
```powershell
# Specify after how many (additional) output objects to update the
# progress display, so as not to spend too much time on updating.
(cifrão)updateEveryN = 35 # escolha a quantas operações vai atualizar
Write-Progress -Activity 'Procressing' -Status '0 object(s) received...'
# Simulate a long-running command
(cifrão)countReceived = 0
# abaixo, escolha a operação, eu escolhi um ls mas podia ser apenas 1..100 | Foreach  etc; os milliseconds podem ser mudados
(ls *.md).Basename | ForEach-Object { Start-Sleep -MilliSeconds 300; (cifrão)_ } |
  ForEach-Object {
    # Every N objects, update the count of objects received so far 
    if (0 -eq ++(cifrão)countReceived % (cifrão)updateEveryN) {
      Write-Progress -Activity 'Processing' -Status ('{0} object(s) received...' -f (cifrão)countReceived)
    }
    # Write-Host (cifrão)_ -NoNewLine # Pass the output object through.
    Write-Host (cifrão)_ # Pass the output object through.
  }
Write-Progress -Complete '(unused)'
```
serve só como brinquedo, falso protetor de tela
## contar o nº de palavras numa string de texto
```powershell
 (cifrão)a | Measure-Object -word
```
Tem de jogar a string na var (cifrão)a. Se é um file, tem de concatenar para converter numa string só, primeiro.
## dois jeitos de pesquisar por string no conteúdo dos files 
forma antiga
```powershell
Get-ChildItem *.md | where { (cifrão)_ | Select-String -Pattern (cifrão)loveMeTender } | Select-Object Name >> ResultList.tmp
```
a opção acima ecoava uma linha de título "Name" no alto da lista de resultados; a forma infra elimina isso.
```powershell
(Get-ChildItem *.md | where { (cifrão)_ | Select-String -Pattern (cifrão)loveMeTender }).Name >> ResultList.tmp
```
## como procurar uma string só nos nomes dos files mas filtrando por tipo de file 
```powershell
Get-ChildItem *.md -Name | where { (cifrão)_ | Select-String -Pattern "(cifrão)masQueBelaVariavel" } >> OZ_searchResultList.tmp
```
a versão anterior não tinha o `*.md` e pescava todos  os tipos de arquivos
## escrever uma lista de números de 1 a 100 numa mesma linha 
```powershell
(cifrão)a = 1..100
	Write-Host (cifrão)a -NoNewLine
```
## jeito mais simples de apagar as linhas em branco de um file
```powershell
(Get-Content meufile.txt) | 
Where-Object {(cifrão)_ -match '\S'} | 
Out-File .\apagajah2.tmp
```
