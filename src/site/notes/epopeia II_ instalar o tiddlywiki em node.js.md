---
{"dg-publish":true,"permalink":"/epopeia-ii-instalar-o-tiddlywiki-em-node-js/","dg-note-properties":{}}
---


tags: #tiddlywiki #ajuda #proj_zetteltex 
parent: [[150621z Tiddlywiki stuff _index\|150621z Tiddlywiki stuff _index]]

 

instalar o node.js é uma epopeia à parte; tem um link [[aqui\|aqui]], mas só consegui depois que instalei "completo" com o tal chocolatey e as mil coisas que vêm com ele; e tem de rodar o node num prompt "normal", ie, cmd.exe, powershell e terminus não servem (o Terminus funcionou, depois de reiniciar, mas bem entendido: tem de rodar um shell cmd.exe dentro do Terminus)

roda o node e usa as instruções para criar um wiki novo (não consegui carregar um pré-existente) (depois que você cria o bicho, e desde que o server esteja off, dá para mover/renomear a pasta cujo nome é o nome do wiki a chamar no terminal)

tem de exportar todos os tiddles em json a partir do nsz "normal"

daí joga o json gigante no wiki novo, para importar todos os tiddlers

exporta do velho e importa no novo todos os plugins, temas e paletas de cores, favicon, 

as macros, botoeira, tudo que começa com (cifrão) não é exportado/importado automaticamente, tem de fazer manualmente

tem de copiar os dados e preencher manualmente as coisas do painel de controle (title, subtitle, fontes)

o CSS do vanilla tem de copiar e colar em cima do css do novo wiki

GRANDE PROBLEMA, parece que esse node ferra todos os scripts do AHK inclusive o Lintalist! Dúvida sobre isso, comportamento estranho... O autocorr, por exemplo, às vezes trava; às vezes se reiniciar funciona; o Lintalist na primeira vez apagou uns bundles; melhor tomar cuidado e fazer backup direto!

milagrosamente o node salva cada tiddler num arquivo de texto separado, e aceita inclusão de novos tiddlers, e edição deles "por fora", no editor de texto### Mas note que para mexer nos tiddlers por fora tem de primeiro fechar o servidor (dar control+c no terminal para encerrar o "serviço listen")

para voltar ao "sistema antigo", basta gerar uma "cópia estática" dentro do node, e essa cópia é um HMTL do estilo antigo.

tudo vai muito bem, até descobrirmos que quando usamos o tal node o Lintalist e o autocorr param de funcionar; isto é, param de funcionar no navegador e no VSCode; porque no npp funciona perfeitamente; uma merda; tentando contornar; sim que se carrega primeiro a desgraça do nsz-node no navegador, depois dá para carregar de novo o Lintalist e o autocorr, e eles funcionam; mas varia... (atualização 2/7/2021: tem funcionado, mas precisa reiniciar várias vezes, e talvez o problema não seja nem o node nem o vscode, mas alguma coisa do trabalho)