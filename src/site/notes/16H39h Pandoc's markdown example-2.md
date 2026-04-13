---
{"dg-publish":true,"permalink":"/16-h39h-pandoc-s-markdown-example-2/","dg-note-properties":{}}
---


<!-- // icx Pandoc's markdown example \

Alberto Santos \

v. 20/06/2018 10:14.

--------------------------------------------------------------- Linha pandocável

>

pandoc -f markdown -t html "(cifrão)(FULL_CURRENT_PATH)" -o "(cifrão)(CURRENT_DIRECTORY)\(cifrão)(NAME_PART).html" -s --toc -N -S

>(A linha acima funciona com o comando "Run" interno do NPP++, que é acionado com o atalho F5. Dê um F5, cole a linha acima e dê enter. As linhas abaixo funcionam de forma similar. Para o comando acima é bom gravar um atalho no menu "Run" do NPP++, geralmente com o atalho 'Ctrl Alt Shift P'.

>Mas ATENÇÃO: essas bostas só funcionam se o texto estiver encoded em UTF-8!

<p>>A linha acima pandoca para html. Abaixo comandos para pandocar para Word)</p>

pandoc -f markdown -t docx "(cifrão)(FULL_CURRENT_PATH)" -o "(cifrão)(CURRENT_DIRECTORY)\(cifrão)(NAME_PART).doc" -s --toc -N -S

----------------------para ver o pandocado use o F5 do NPP## com a linha abaixo:

"(cifrão)(CURRENT_DIRECTORY)\(cifrão)(NAME_PART).html"

>A linha acima serve para ver o html. Para ver o docx pandocado use esta:

"(cifrão)(CURRENT_DIRECTORY)\(cifrão)(NAME_PART).doc"

---------------para abrir o html pandocado no NPP## use o F5 com a linha abaixo:

"(cifrão)(NPP_DIRECTORY)\notepad++.exe" "(cifrão)(CURRENT_DIRECTORY)\(cifrão)(NAME_PART).html"

--------------------para abrir a pasta que contém este doc use o F5 nesta linha:

"(cifrão)(CURRENT_DIRECTORY)"

-------------------------------------------------------------------------------

Escrito com Pandoc Markdown e Notepad## 

v. 30/05/2015, 22h39m..

fcx // --> 

 

Pandoc's markdown example <!-- // por alguma razão misteriosa não dá para formatar o título 1 no NPP, vira uma loucura. Ideia: usar, sempre que possível, só título 2 e 3.  // -->

<!-- //  icx Escopo  // --> 

<!-- // não esqueça de deixar uma linha em branco entre isto aqui e os sustenidos abaixo, senão ferra tudo! Também não precisa economizar no assunto das linhas em branco, porque quando converter para html o PM emenda tudo, apaga as linhas em branco; então pode usá-las à vontade, para manter os assuntos separados e destacados // --> 

## Escopo deste documento {#scopus}

_Comecemos por isto: se você está lendo isto num navegador de internet, está errado. Tem que achar o arquivo com extensão .md, e abri-lo no Notepad++, de preferência usando a linguagem específica (um xml chamado Pandoc_MD_ alguma coisa)._ <!-- // Hoje, 26/02/2016, 10h33m., estamos usando "Pandoc MD Zen 4a" // -->

Este documento quer demonstrar as funcionalidades do Pandoc's Markdown (adiante chamado PM) e criar uma sintaxe para ele no Notepad## (adiante, NPP). 

Há também algumas dicas de uso do próprio NPP.

<!-- //  fcx escopo  // -->

<!-- //  icx npp  // -->

### Ajuda específica do NPP {#npphelp}

Não sei por quanto tempo vai funcionar, mas consegui fazer as porcarias dos chaveamentos de seção funcionar dentro de marcas de comentário, como acima. Então, tecle `Alt = 0` para fechar as chaves (_fold_), e `Alt + Shift + 0` para reabrir. `Ctrl + Alt + F` fecha só a seção atual, e `Ctrl + Alt + Shift + F` abre só a seção atual. Tem outras teclas de atalho a respeito, olhe na ajuda no NPP. (Em 20/06/2018 10:53 essa parte de  `Ctrl + Alt + F` que fecha só a seção atual, e `Ctrl + Alt + Shift + F` que a reabre não funciona; mas `Alt + +` e `Alt + -` estão fazendo o serviço (?!).

Conselho de amigo: só use chaves para os níveis mais baixos de títulos (os títulos que contêm texto, não são só sobretópicos sem texto), isto é, não use chaves dentro de chaves. Isso não dá certo.

Pode usar o `Ctrl + F2` para criar um marcador rápido, e `F2` para saltar entre os marcadores rápidos (ou `Shift + F2` para saltar regressivamente. É útil para marcar as linhas de cabeçalhos das seções, e saltar rapidamente entre elas. 

Para criar uma espécie de índice navegável das seções de um documento, use a opção `Localizar em arquivos` (`Ctrl + Shift + F`), coloque o sinal de header na linha de pesquisa (isto é, o `! ! !` ou o `!` se quiser uma pesquisa mais completa), e clique no botão `Localizar todos no documento atual`. Vai abrir uma janelinha em baixo com a lista, clique no header para saltar até lá.

> Aliás, sobre o acima, se você reunir todos os arquivos do projeto numa mesma pasta, o truque fornece uma lista com os mapas navegáveis dos títulos de todos eles, o que é bem útil para saltar de um para o outro. 

O arquivo XML que preparei (o mais novo se chama __"Pandoc_MD_7d_BlackB.xml"__)  cria um setup de linguagem de programação colorido para usar no NPP. Vá em "Linguagem", "Defina sua linguagem", importe o xml acima, ou os outros que houver, e depois escolha-o na lista do menu "Linguagem" para ter formatação colorida (segundo parece, em 20/06/2018 10:58 o mais novo é "PandocZenburnNew01.xml").

Nesse setup de cores incluí dois marcadores, kkk e to-do que aparecem com destaque no texto e também servem como itens de pesquisa navegáveis para você se localizar no texto. Só que não funcionam se você colocar vírgula ou qualquer pontuação logo depois. O 1º é para marcar o lugar onde estou trabalhando agora. O 2º é para deixar anotados lugares onde ficaram coisas por fazer. Se colocar essas tags dentro de comentários, pode ir exportando versões provisórias sem que elas incomodem (mas aí elas não aparecem destacadas (em 20/06/2018 10:59 aparecem, sim, destacadas, dentro dos comentários)).

As macros e atalhos do NPP ficam salvas neste arquivo: D:\Users\alms\AppData\Roaming\Notepad++\shortcuts.xml

<!-- //  fcx npp // -->

## Formatação em geral {#formatação}

<!-- //  icx headers // --> 

<!-- // como não consegui um jeito funcional de fazer chaves dentro de chaves, temos duas opções: 1) por o começo da chave de subtítulo acima da chave do título maior, para não ficar aparecendo o título maior solteiro, deschavado, quando foldeia; ou 2) fazer como está aqui, e deixar os títulos maiores aparecendo, o que pode ser útil, de certo modo // -->

 

### Formatando headers {#formhead}

 > 

Como demonstrado acima, é possível colocar marcadores para 'batizar' os títulos (as palavrinhas entre chaves que estão logo depois do título do header), de forma a poder depois criar âncoras para eles. Esses links são usados pela Table of Contents, gerada pelo PM. 

Notar que o PM faz os links automaticamente se você não batiza os headers. Então, para gerar a TOC não precisa batizar. Só batize se quiser criar links internos.

Aqui, por exemplo, coloco este link interno para a âncora do [escopo](# scopus). (essa hashtag devia estar colada na palavra scopus mas estava endoidando o obsidian)

Também poderia fazer os links internos com um mapa de referências ao fim, como aqui: [sobre as tabelas] (vou por o mapa de referência logo abaixo, mas poderia por ao fim da página).

[sobre as tabelas]: # tabelas (essa hashtag devia estar colada na palavra tabelas mas estava endoidando o obsidian)

<!-- // a linha acima é o mapa de referências, que poderia estar no final do texto! Muita atenção: não pode por coisas que comecem com tag html, como por exemplo este parágrafo aqui, logo depois do mapa de referências, senão o link para de funcionar## // -->

Note, contudo, que, ao exportar, e sob pena de dar errado: 

1. **os headers têm que ficar encostados na margem** (eu sempre esqueço isso, e é **muito importante**),

2. tem que haver uma linha em branco (totalmente em branco) antes de cada header (**importante**).

Tanto faz quantas linhas em branco você deixa entre este parágrafo e o título a seguir, o PM formata tudo emendadinho (apaga as linhas em branco). Então, deixar linhas em branco é útil para enxergar as divisões entre os parágrafos quando você está trabalhando no NPP.

<!-- //  fcx headers // --> 

  

### Padrões de formato de texto {#formtex}

<!-- //  icx ênfase // --> 

#### Ênfase {#emph}

  

Estes é o padrão para **negrito**.

Quanto ao _itálico_, é _assim_ que faz, mas não achei um jeito de mandar o NPP destacar isso. Tentei usar __underline dupla__, mas isso não gera itálico, gera strong, isto é, negrito. Usar underline simples como operador no NPP endoida a formatação inteira, nem tente! Usei xxx_isto_xxx, que o NPP entende, mas quando exporta, se não apaga os x primeiro, o PM não entende. Podia fazer <i>assim</i>, mas qual a vantagem?

Dá para fazer **_negrito itálico_** assim, mas o NPP não sabe destacar isso.

   > Embora você possa usar a antibarra como caracter de escape. Por exemplo \' não é interpretado como marcador.

Estes são os padrões para ~~strikeout~~ e ~subescrito~ e este para xxx^sobrescrito^xxx. Notar que os dois últimos não aceitam espaços em branco dentro da área demarcada[^050820181647]. O sobrescrito seria somente aquele \^ antes e depois, mas estava deixando a formatação maluca, então mudei acrescentando aqueles xxx. **Tem que apagar os xxx antes de exportar**.

[^050820181647]: atualização em 05/08/2018 16:48: o plugn para npp que estou usando atualmente para gerar html a partir de markdown aceita espaços em branco dentro das marcas de strikeout e sobrescrito.

 

<!-- //  fcx ênfase // --> 

 

 

<!-- //  icx blockquote // --> 

 

#### blockquote {#blockquote}

  

  > Este é o padrão blockquote. <!-- // afasto sempre o blockquote três espaços da margem, para ele ficar fácil de identificar no rascunho, mas isso é opcional; se colocar o sinalzinho colado na margem ele entende do mesmo jeito  // --> 

   > > Pode usar o duplo recuo (duas angle-brackets) para nestar.

   > Notar, ademais, que a sintaxe PM exige: <!-- // se não deixa esta linha em branco abaixo a lista numerada não funciona // -->

   > 1. que a marcador de blockquote fique a no máximo 3 espaços da margem esquerda

   > 1. que entre um e outro marcador de blockquote haja um espaço em branco. 

Como demonstrado acima, pode-se inserir listas numeradas ou buletadas em blockquotes.

 

 <!--   endsec formtex  -->

<!-- //  fcx blockquote // -->  

 

 

<!-- //  icx listnum // --> 

 

### lista numerada {#lnum}

  

Quanto a isso, só funciona se:

1. o número ficar encostado na margem esquerda,

1. pode usar outros padrões de numeração mas tem que utilizar uma chave de extensão quando for exportar

>a. Admite sublistas nestadas como esta

>a. e pode marcar os itens com qualquer número, que ele numera certo na exportação. 

>>i. como visto acima, pode marcar as sublistas com letra, que ele entende,

>>i. e as sub-sublistas com 'romanos', que ele entende também. 

>

Observe que é possível fazer listas 'apertadas' como a acima, e 'frouxas'

1. como esta aqui, que tem

1. maior espaço entre as linhas

1. para ajudar na leitura

  

<!-- //  fcx listnum // --> 

  

  

<!-- //  icx listbullet // --> 

  

### lista buletada {#lnum}

  

Quanto a isso, só funciona se:

' o marcador ficar encostado na margem esquerda,

' pode usar outros padrões de numeração mas tem que utilizar uma chave de extensão quando for exportar

>+ Admite sublistas nestadas como esta

>+ e isto. 

>>- e também admite isto, um item de lista que 

>>

>>>tem mais de um parágrafo

>>- e isto. 

>

Observe que é possível fazer listas 'apertadas' como a acima, e 'frouxas'

' como esta aqui, que tem

' maior espaço entre as linhas

' para ajudar na leitura

  

<!-- //  fcx listbullet // --> 

  

  

<!-- //  icx footn // --> 

  

### Notas de rodapé {#foot}

   

Aqui vai uma demonstração de nota de rodapé.

Here is a footnote reference,[^1] and another.[^longnote]

Lembre de não colocar ponto depois do colchete final da linha acima.

Também há uma sintaxe simplificada: Here is an inline note.^[Inlines notes are easier to write, since you don't have to pick an identifier and move down to type the note.]

O mais genial da sintaxe de rodapé do PM é que você pode por qualquer número nas chamadas de notas, ou pode numerar todas com 1. Basta que no final você numere as notas <a name="mark1"></a> certo^[Não sei se entendi isso que eu mesmo escrevi; acho que significa que quando você vai escrever as notas lá no final do texto, tem que escrevê-las na mesma ordem em que elas são chamadas no corpo do texto, senão ferra tudo. Então, se você não tem certeza de qual a posição da nota atual, e vai fazer um texto enorme com muitas notas, é melhor fazê-las com identificadores únicos.], ele faz o resto automaticamente.

Agora vamos tentar isto[^testinho], para ver se dá para por a nota aqui no parágrafo seguinte, e mesmo assim ela aparecer no local esperado, quando tudo acabar.

[^testinho]: yyy Genial. Pode escrever o texto da nota num parágrafo separado, logo abaixo do corpo do texto (na verdade pode escrever em qualquer parte do texto), que o PM passa ele para baixo na hora de exportar.  Só não tente fazer blockquote, que não funciona. _Agora só falta achar um jeito de destacar a formatação_. Estou tentando os 3 y, que até funcionam, só que tem que apagar mais isso antes de exportar.

Embora o sistema de notas de rodapé inline ou identificada por nome, como exemplificado acima, seja prático, tem uma desvantagem: no wordpress as notas são convertidas numa lista numerada, e ficam coladas uma na outra, sem espaçamento. Não consegui consertar. Já quando faz as notas do jeito tradicional, numerando-as em ordem e colocando as notas numeradas no fim, o wordpress entende o que é para fazer e coloca espaçamento entre uma nota e outra. Então, a segunda técnica é melhor, para posts <!-- // não procede; tentei hoje e nas duas técnicas o wordpress faz uma lista colada de merda // -->. Para exportar para word, não faz diferença.

Qualquer coisa que você escrever depois das notas (daquela seção do final onde geralmente coloca as notas) será reposicionada automaticamente antes das notas de rodapé. O PM sempre colocará as notas no final do documento, não interessa em que parte do documento rascunho elas estão. 

  

<!-- //  fcx footn // --> 

  

<!-- //  icx links // -->  

  

### Links {#links}

  

**Atenção: só funcionam links cujo endereço comece com `http://`. Se começar com `www` não vai.**

   

An inline link consists of the link text in square brackets, followed by the URL in parentheses. (Optionally, the URL can be followed by a link title, in quotes.)

This is an [link google](http://google.com), and here's [one with

a title](http://fsf.org "click here for a good time!").

There can be no space between the bracketed part and the parenthesized part. The link text can contain formatting (such as emphasis), but the title cannot.

Qualquer coisa assim <http://google.com> também é um link.

An explicit reference link has two parts, the link itself and the link definition, which may occur elsewhere in the document (either before or after the link).

The link consists of link text in square brackets, followed by a label in square brackets. (There can be space between the two.) The link definition consists of the bracketed label, followed by a colon and a space, followed by the URL, and optionally (after a space) a link title either in quotes or in parentheses.

O mais legal é que ele oculta mesmo as listas de endereços (começadas com link1, link2, etc., no exemplo abaixo).

Here are some examples [link1], [link2], [link3], [link4]:

[link1]: http://www.yahoo.com  "My title, optional"

[link2]: <http://google.com>

[link3]: http://fsf.org (The free software foundation)

[link4]: http://globo.com  'A title in single quotes'

The URL may optionally be surrounded by angle brackets: [link5].

[link5]: <http://foo.bar.baz>

The title may go on the next line: [link9]

[link9]: http://fsf.org

  "The free software foundation"

Note that link labels are not case sensitive. So, this will work:

Here is [my link][FOO]

[Foo]: /D:\Users\alms\Desktop\ts\new.htm **'Aqui, um link para um arquivo local**'

<!-- // Este é o jeito como se faz um link para arquivo local. Muita atenção: não pode por coisas que comecem com tag html, como por exemplo este parágrafo aqui, logo depois do link, senão o link para de funcionar## // -->

Para ver **como se fazem links internos**, depende; se for um link para um header, veja [acima](# formhead) (essa hashtag devia estar colada na palavra formhead mas estava endoidando o obsidian). Se for para qualquer parte do texto que não seja um header, veja [aqui](# mark1) (essa hashtag devia estar colada na palavra mark1 mas estava endoidando o obsidian) a respeito. Isso quer dizer o seguinte: no lugar-destino, coloque uma marca do tipo <a name="nomedomeuindicador"></a> e no lugar onde vai o link-chamada que deve saltar para o lugar-destino, coloque algo tipo [aqui](# nomedomeuindicador). (essa hashtag devia estar colada na palavra nomedomeuindicador mas estava endoidando o obsidian)

In an implicit reference link, the second pair of brackets is empty, or omitted entirely:

See [link1][], or [link1].

<!-- //  fcx links // -->  

>

<!-- //  icx img // -->  >

>

### Imagens

   

Para por imagens fazer assim: 

![chamada e caption](C:\Program Files\WriteMonkey\quack-2.jpg "caption optional")

Também pode fazer um mapa de lista de imagens ao final, assim:

![teste de imagem]

O texto acima aparecerá como caption/legenda. 

Aqui vai a lista-mapa das imagens (poderia estar no final da página):

[teste de imagem]: /E:\Dropbox\ESCRITOS\zettelplus\_0GL5UPCM0K802Z8ZX1QP.jpg

A sintaxe é muito simples e ele aceita os caminhos do jeito que o NexusFile copia, sem frescura. Mas **notar a barra antes do começo o caminho de arquivo!!**

<!-- // cuidado com o que usa para batizar a imagem (isto é, o nome que aparece entre colchetes e depois é referido no mapa de imagens. Isso aparece como caption na página exportada.  // -->

Agora vou por uma imagem da internet, funciona. Pode por o link de imagem da linha abaixo entre tags html de centralização.

![imgdanet]

E aqui vai o mapa da imagem da internet (que poderia estar no fim da página):

[imgdanet]: https://www.tjpr.jus.br/image/company_logo?img_id=10850&t=1432312083979

If you just want a regular inline image, just make sure it is not the only thing in the paragraph. One way to do this is to insert a nonbreaking space after the image:

![This image won't be a figure](/C:\Program Files\WriteMonkey\bullet.png) Vejamos como fica o texto com uma bullet no começo. **Não esqueça, quando for exportar, de mudar os caminhos de imagens para relativos à pasta onde ficará o html**.

 

<!-- //  fcx img // -->  >

<!-- //  icx table // -->  >

 

### Tabelas {#tabelas}

   

Este é o único assunto onde o formato textile é superior ao markdown pandoc. Aqui, todas as tabelas ficam _horríveis_. Se for usar tabelas, use textile.[^sobretabelas] Se mesmo assim quiser insistir com o pandoc-markdown, as tabelas simples são assim:

coluna1>coluna2>coluna3>coluna4

------->------->------->-------

hoje>amanhã>depois>hoje

18>> 19>> 20>>18

test>coisa>e tal>total

Table: Legenda da tabela.

Uma tabela com células que admitem mais de uma linha de texto é assim:

--------------------------------------------------------------------------------

prima>>segunda>>terceira>>quarta>>soma

coluna>>coluna>>coluna>>>coluna>>total

------->>--------->--------->>-------->----------------------------

célula 1>célula 2>aqui 3>>>aqui 4>>aqui vamos por texto que 

>>>>>>>>>>>>>supera a largura da célula

>>>>>>>>>>>>>e ver como fica

linha 2>>linha 2>>aqui é 3>>esta é>>vejamos como fica a linha

>>>>>>>>>>a linha>>2 da coluna quinta

>>>>>>>>>>4>>

--------------------------------------------------------------------------------

Table: Legenda: tem que começar e acabar com uma linha inteira de ->>>>>>>>>

Pipe tables look like this:

| Right | Left | Default | Center |

|------:|:-----|---------|:------:|

|   12  |  12  |    12   |    12  |

|  123  |  123 |   123   |   123  |

|    1  |    1 |     1   |     1  |

Demonstration of simple table syntax.

The syntax is the same as in PHP markdown extra. The beginning and ending pipe characters are optional, but pipes are required between all columns. The colons indicate column alignment as shown. The header can be omitted, but the horizontal line must still be included, as it defines column alignments.

Since the pipes indicate column boundaries, columns need not be vertically aligned, as they are in the above example. So, this is a perfectly legal (though ugly) pipe table:

fruit| price

-----|-----:

apple|2.05

pear|1.37

orange|3.09

The cells of pipe tables cannot contain block elements like paragraphs and lists, and cannot span multiple lines.

Table: Meu teste pessoal

pessoa | nome | idade | profissão

:-----------:|:----------------|:-----|---------------:

trubufu | josé carlos | 44 | lixeiro

pessoal | adoniran barbosa | 66 | compositor de sambas e modinhas

troço e tal | ernesto me convidou | 50 | ladrão e perdulário

<!-- //  fcx table // -->  >  

  

<!-- //  icx code // -->  >  

  

### Code blocks

   

A block of text indented four spaces (or one tab) is treated as verbatim text. Like:

>Este é um texto em formato code.

>

You can also make Fenced code blocks, like this one:

~~~~~~~~~

begin with a row of three (nine, na verdade) or more tildes or backticks (`) and end with a row of tildes or backticks that must be at least as long as the starting row. Everything between these lines is treated as code. No indentation is necessary

~~~~~~~~~

Muito cuidado ao tratar texto assim, veja se a quantidade de tils é suficiente para encerrar a marcação.

Optionally, you may attach attributes to the code block using this syntax:

~~~~~~~~~ {#identifier .class}

Onde identifier será o que o nome diz, e class idem (troque essas palavras pelos nomes que quer atribuir ao identifier e à class;

~~~~~~~~~

<!-- // por alguma razão que não entendo quando coloca nove tils em sequência o fenced block fica todo marcado como devia ser!  // -->

To make a short span of text verbatim, put it inside backticks `like this one`.

~~~~~~~~~~~

Interessante: quando abre o html no word, os codeblocks ficam com o mesmo formato do texto principal, mas com fonte dois pontos menor, o que é útil para comentários. Pena que essa bosta não aceita formatação, links, nada.

~~~~~~~~~~

<!-- O comentário acima só vale para quando abre no word um html criado pelo pandoc. Se pandoca direto de .md para .doc não funciona assim. -->

<!-- //  fcx code // -->  >  

   

   

<!-- //  icx html // -->  >  

   

### blocos e textos em html {#html}

   

A diferença entre PM e textile é que o 1º trata como sintaxe sua os sinais que houver dentro de um bloco html e que corresponderem aos seus marcadores.

<p class="bueno">Aqui vai **um teste** de __itálico__ dentro de um ~~bloco~~ html </p>

There is one exception to this rule: text between `<script>` and `<style>` tags is not interpreted as markdown.

Por enquanto ainda não achei um jeito de fazer links internos para qualquer coisa que não seja um header sem usar código html (procure mark1 para ver como é, se não se lembra). Para os headers funciona a tag PM ensinada [acima](# formhead). (essa hashtag devia estar colada na palavra formhead mas estava endoidando o obsidian)

<!-- //  fcx html // -->  >  

   

<!-- //  icx line blocks // -->  >   

   

### line blocks

   

A line block is a sequence of lines beginning with a vertical bar (|) followed by a space. The division into lines will be preserved in the output, as will any leading spaces; otherwise, the lines will be formatted as markdown. This is useful for verse and addresses:

| nome do destinatário

| endereço

| cidade 

| última linha do bloco

Voltamos ao normal aqui.

<!-- //  fcx line blocks // -->  >   

   

<!-- //  icx diclist // -->  >   

   

### listas de definições {#diclist}

   

Pandoc supports definition lists:

item 1

:>definition do item 1

item 2

: >aqui pode por vários parágrafos

>desde que as linhas interiores

  

>preservem a mesma distância da margem esquerda que a linha 1

If you leave space after the definition (as in the example above), the blocks of the definitions will be considered paragraphs. In some output formats, this will mean greater spacing between term/definition pairs. For a compact definition list, do not leave space between the definition and the next term:

Term 1

  ~ Definition 1 <!-- ~ -->

Term 2

  ~ Definition 2a <!-- ~ -->

  ~ Definition 2b <!-- ~ -->

Isso é ótimo, mas o problema são os tils. Tive que por um <!-- ~ --> no fim de cada linha de definição acima, para desenlouquecer a formatação. Mesmo estando dentro de um bloco de comentários html (que não aparecerá na edição), o til serve para fechar o marcador.

<!-- //  fcx diclist // -->  >   

   

<!-- //  icx lista de exemplos // -->  >   

   

### listas de exemplos {#exemplos}

   

The special list marker @ can be used for sequentially numbered examples. The first list item with a @ marker will be numbered ‘1’, the next ‘2’, and so on, throughout the document. The numbered examples need not occur in a single list; each new list using @ will take up where the last stopped. So, for example:

(@)  My first example will be numbered (1).

(@teste)  My second example will be numbered (2).

Explanation of examples.

(@)  My third example will be numbered (3).

Numbered examples can be labeled and referred to elsewhere in the document:

(@good)  This is a good example.

As (@good) illustrates, ...

The label can be any string of alphanumeric characters, underscores, or hyphens.

Esses marcadores não criam links. Apenas servem para batizar automaticamente os exemplos quando você faz referência a eles. Por exemplo, se eu escrever (@good) de novo ele vai por o número que o PM atribuiu a esse rótulo, e eu não preciso me preocupar com a numeração.

Vamos fazer (@teste) um teste aqui para ver o que acontece.

Será que vai chamar o (@teste)? Funciona. O defeito desse sistema, eu acho, é que não tem como reiniciar a numeração, que vai contínua até o fim do documento.

<!--   endsec 'formatação'  --> 

<!-- //  fcx lista de exemplos // -->  >   

## Exportando {#export}

<!-- //  icx como o PM funciona // -->  >   

### Como o PM funciona {#comofas}

 

Usar esta linha de código:

~~~~~~~~~

pandoc -f formatodeorigem -t formatodesaída arquivoaconverter -o arquivodesaída -s --toc

~~~~~~~~~

<!-- // No WordPress essas linhas enormes, conforme o CSS, aparecem com uma barra de rolagem horizontal! // --> 

Onde formato de origem é uma destas expressões: html, markdown, textile; e formato de saída é html, docx[^sobreword], plain (para texto puro), rtf, pdf[^sobrepdf],  etc..

As chaves `-s` e `--toc` são opcionais. Sem a primeira, o PM cria apenas um bloco de html, sem head nem fecho. Bom para colocar o cabeçalho personalizado, com css, etc.. Se usa o `-s` ele cria um HTML completo, pronto para ler. O `--toc` cria um índice no alto.

> Não precisa deixar a TOC no alto, pode depois abrir o html num editor, e mover a `div` que contém a TOC para qualquer lugar do texto (útil no caso de posts do WordPress).

> Pode copiar o CSS dos modelos do WriteMonkey (na pasta há um, magda.css, para exemplo); substitui tudo que aparecer entre as chaves `<style>` e `</style>` no head do html que o PM gerar, e pronto.

Se colocar a chave `-N` ele numera as seções. Se acrescentar `-S` ele converte aspas retas para aspas curvas **(era assim, em 20/06/2018 10:17 a opção -S não é mais aceita)**.

A linha a seguir, por exemplo, transforma o arquivo 'teste.txt', que foi feito em pandoc-markdown, num html, numerando seções (a chave `-N`), com índice no alto (a chave `--toc`), completo e pronto para ler (a chave `-s`) (tirei a opção de aspas curvas (a chave `-S`) porque não funciona mais):

~~~~~~~~~

pandoc -f markdown -t html teste.txt -o teste.html -s --toc -N

~~~~~~~~~

A linha a seguir vai como um caminho completo, para o **pc de casa**, **para exportar em html**, conferir antes de usar:

~~~~~~~~~

pandoc -f markdown -t html C:\Users\Master\Dropbox\ts\teste.txt -o C:\Users\Master\Dropbox\ts\teste.html -s --toc -N

~~~~~~~~~

No caso do PC do **fórum**, caminho completo é este (**para html**):

~~~~~~~~~

pandoc -f markdown -t html d:\Users\alms\Dropbox\ts\teste.txt -o d:\Users\alms\Dropbox\ts\teste.html -s --toc -N

~~~~~~~~~

As linhas a seguir têm o caminho completo para exportar **para formato docx**, conferir o caminho antes de usar; esta é o PC de **casa**:

~~~~~~~~~

pandoc -f markdown -t docx C:\Users\Master\Dropbox\ts\teste.txt -o C:\Users\Master\Dropbox\ts\teste.doc -s --toc -N

~~~~~~~~~

No caso do PC do **fórum**, o caminho completo é este (**Para docx**):

~~~~~~~~~

pandoc -f markdown -t docx d:\Users\alms\Dropbox\ts\teste.txt -o d:\Users\alms\Dropbox\ts\teste.doc -s --toc -N

~~~~~~~~~

Se pretende usar para escrever um despacho, ou um texto qualquer em html para colar num editor on-line (como o Projudi ou o do WordPress), retire as 4 extensões (-s --toc -N -S).

Gosto de deixar um arquivo aberto só com a linha de comando completa, outra com o texto que estou editando, e uma terceira com o arquivo texte.txt. Quando quiser ver como está ficando, copia todo o texto da janela principal para a teste.txt, salva e roda de novo a linha de comando. Daí é só dar F5 na janela do navegador onde abri pela primeira vez o `teste.html`. Ou então você vai em "Arquivo", "Abrir pasta atual em", "Cmd". Daí tem uma janela do DOS na pasta onde você está trabalhando. Cole ali a linha de comando. Quando quiser atualizar, alterne para o DOS, seta para cima, enter, e pronto.

<!-- //  fcx como o PM funciona // -->  >   

 

<!-- //  icx exportar // -->  >   

## Cautelas ao exportar

  

Quando for exportar, tem fazer primeiro as seguintes substituições e consertos:

1. Todas as marcas de comentários (barras duplas) tem que estar dentro de marcas de comentários html <!-- // como esta aqui // --> e não pode deixar nada com  classe 'mc' dentro de `span`, porque se tiver um desses antes de um header ele será ignorado. 

1. Consertar as marcas de xxx^sobrescrito^xxx tirando delas os 3 x (padronizei o marcador xxx^para^xxx sobrescrito porque se usar só o acento o texto enlouquece). De qualquer forma quando apagar o calço triplo isso deve ficar resolvido. 

1. Apagar todos os `yyy` e `zzz` que houver.

1. Apagar os kkk, às vezes fica algum esquecido.

1. **conferir se todos os headers têm uma linha em branco antes**

1. **Também não pode haver espaços em branco antes dos !**.

1. depois de exportar, tem que abrir no NPP e:

>a. mudar o encoding para UTF-8 puro, <!-- // talvez isso não seja necessário; antigamente eu precisava disso, mas agora parece que está funcionando perfeitamente a versão exportada no navegador e no WordPress sem precisar dessa etapa. Mistérios! // -->

>b. colocar o cabeçalho e o rodapé de html (neste ponto o uso de um CSS é bom).^[A menos que você tenha utilizado a opção -s na linha de comando do PM. Veja [a seção específica](#comofas).]

<!--   endsec como-funciona  --> 

>

<!-- //  fcx exportar // -->  >    

 

 

 

 

## Referências

<!-- //  icx sobreopandoc // -->  >   

### Sobre o pandoc

O arquivo de ajuda do Pandoc [está aqui][ajudapandoc].

[ajudapandoc]: /C:\Users\Master\AppData\Local\Pandoc\Pandoc User's Guide.html 'MERDA' 

<!-- // notar que este é um link para arquivo local, e pela primeira vez esta merda funciona; só consegui fazer criando uma tábua de referências em separado, na linha de baixo. Preste muita atenção na sintaxe! Muita atenção: não pode por coisas que comecem com tag html, como por exemplo este parágrafo aqui, logo depois do mapa de referências, senão o link para de funcionar## // -->

<!-- //  fcx sobreopandoc // -->  >   

<!-- //  icx sobreoMD // -->  >   

### Sobre o markdown puro

  

A ajuda do Markdown puro está [aqui](http://daringfireball.net/projects/markdown/).

 

<!-- //  fcx sobreoMD // -->  >   

 

 

<!-- //  icx outros links // -->  >   

 

### Correlatos

  

[S5](http://http://meyerweb.com/eric/tools/s5/primer.html) é um sistema incrivelmente simples para criar apresentações de slides que rodam em qualquer navegador. O PM gera apresentações desse tipo. Mas o Slideous (procure no dropbox ou no evernote) é mais simples e mais interessante, faz tudo num único arquivo html.

 

<!--   endsec reference  --> 

<!-- //  fcx outros links // -->  >   

<!-- //  icx notas de rodapé // --> 

<!-- // -----------NOTAS E ADENDOS COMEÇAM AQUI-------------  // --> 

## Notas e adendos {#notas}

[^sobretabelas]: Sobre esse assunto de tabelas, a questão é com o CSS. Se o CSS trata bem as tabelas elas ficam lindas. Testei no WordPress, e foi um sucesso. Então, não vale a pena ficar no Textile só por causa disso.

>Esta nota é ao mesmo tempo um teste sobre o assunto referido [acima](# mark1) (essa hashtag devia estar colada na palavra mark1 mas estava endoidando o obsidian) a respeito de como o PM coloca as notas de rodapé na ordem certa, desde que você dê a elas um identificador único. 

  

[^1]: Here is the footnote.

[^longnote]: Here's one with multiple blocks.

    Subsequent paragraphs are indented to show that they belong to the previous footnote.

        { some.code }

    The whole paragraph can be indented, or just the first line.  In this way, multi-paragraph footnotes work like multi-paragraph list items.

[^sobreword]: Não tenho usado exportação para docx ou rtf. Exporto para html, porque é mais rápido e versátil. Depois pode abrir o html no Word, salvar como arquivo do word, e formatar. Funciona médio. O que não funciona:

>a. As notas não podem ser convertidas em notas de rodapé. Ficam no fim do texto, à moda americana. Tem que converter manualmente se quiser.

>a. As listas "frouxas" não funcionam, ficam "apertadas".

>a. Notas de rodapé com mais de um parágrafo ficam com espaçamento estranho, requerem alguma formatação manual, nada difícil.

>a. Tem que apagar uma hr que o PM coloca entre o título da seção de notas e as notas propriamente ditas.

>a. Textos marcados como `code` como este não ficam com aparência code, ficam só com a fonte menor.

>a. **Pior de tudo**: os links internos não funcionam, nenhum, nem os para as notas de rodapé.

>

>O que fica ótimo:

>

>a. Se você utilizou codeblocks, no word eles ficam com a mesma formatação do texto normal, mas com a fonte 2 pontos menor, o que é útil para fazer comentários.

>a. As tabelas vão sem nenhuma formatação, mas é fácil usar os padrões pré-formatados do word e fica ótimo.

>

>Exportar para RTF é lixo completo.

>

>Exportar para docx (não pode ser doc, tem que ser docx) desformata tudo, e remove a numeração dos títulos (não achei um jeito fácil de corrigir isso). Mas em compensação você terá notas de rodapé no pé da página, mas os links internos não funcionam (só funcionam os links internos que remetem aos títulos de capítulo). Dá para fazer um sumário automaticamente, e os links dele funcionam. Quando exporta para PDF todos os links que funcionam no word também funcionarão. Se a intenção é gerar PDF, essa é a melhor opção.

[^sobrepdf]: O Pm exporta para pdf se você tiver o LaTeX instalado. Não tenho, mas não está fazendo falta, prefiro abrir no word, formatar lá e salvar como pdf por lá. Mais prático.

>Só que no PDF feito assim os links internos só funcionam se foram feitos em sintaxe html (braçalmente); os feitos usando MD não funcionam. Os links para notas de rodapé, portanto, não funcionam (no Word também não  funcionam).

>

<!-- // qualquer coisa que você escrever depois desta linha será reposicionada automaticamente antes das notas de rodapé. O PM sempre colocará as notas no final do documento, não interessa em que parte do documento rascunho elas estão  // -->

>

<!-- //  fcx notas de rodapé // --> 

<!--   endsec documento  -->

