---
{"dg-publish":true,"permalink":"/projeto-zkm-outra-lista-de-demandas-obsoleta/","dg-note-properties":{}}
---

## obsoleto


INSTRUÇÕES RECORRENTES / PERMANENTES: use o arquivo enviado como base de trabalho, não é para reescrever o script todo; conserte APENAS O QUE PEDIREI NAS INTRUÇÕES NOVAS ABAIXO; não mude nada além do que eu pedi; não simplifique, reescreva, limpe nem "melhore" o código, não tente encurtar as instruções nem tornar o código mais elegante ou conciso sem eu pedir; não mexa em nada além do que eu pedi e não mude nada que não seja estritamente necessário para cumprir o que eu pedi; não tente melhorar o código sem eu pedir; se tiver de mexer em algo que seja fora da função que eu pedi, pare e me informe antes o que pretende fazer e me peça confirmação antes de prosseguir; faça comentários verbosos nas partes que criar ou mudar tornando o script explicativo para um aprendiz de Python; em cada linha ou seção do código que você alterar coloque um comentário "alterado (ou incluído) na versão x.xx".

INSTRUÇÕES NOVAS:
## copiado

```
1. Parece que só o prompt do menu principal está aceitando "q" como comando para sair do "programa"

2. O changelog está congelado na v.3.08 sem atualizações verbosas e detalhadas que eu pedi

3. Opções que havia no file-ops da v.2.18 e atualmente não aparecem mais (você tem como resgatar a lógica dessas funções da versão 2.18? Ou preciso explicar uma por uma?)

(2) : Copiar o conteúdo textual do arquivo LWF atual para o Clipboard
(4) : Acessar o menu de gestão detalhada da Lista de Cópia Temporária
(5) : Copiar todos os nomes da LSR formatados como [[links de wiki]]
(n) : Abrir o arquivo LWF atual no editor de texto MICRO (Terminal)
(r) : buscar Referentes (arquivos que remetem ao LWF atual)
(m) : Listar os 10 arquivos modificados mais recentemente no sistema
(sz): Listar os 10 maiores ZETTELS (arquivos .md) do cofre
(sa): Listar os 10 maiores ASSETS (outras extensões) do cofre
(st): Listar Zettels sem nenhuma etiqueta (#)
(ap): Listar Zettels marcados com #apagar (com contexto)
(in): Listar todos os arquivos que contenham a etiqueta #inbox
(ur): Listar todos os arquivos que contenham a etiqueta #urgente

4. Além disso a opção (c) do menu principal, que deveria inserir o LWF na "lista de cópia" não está funcionando, a "lista de cópia" segue vazia

5. Quando entro "r" no menu principal ele deveria me pedir uma string para refinar a pesquisa prévia, mas não faz nada e apenas repete a mesma tela e prompt

6. Se peço para refinar no prompt que se segue à lista de resultados, refina corretamente, aceita seleção de novo LWF, registra corretamente o novo LWF, etc. Mas se peço, no prompt principal, LSR, ele entrega a lista de LSR correta mas quando volta para a tela principal mudou o LWF selecionado para um aleatório, que não escolhi

=================

Carrega a interface

1) o d na tela inicial não faz nada (não carrega zettel escolhido randomicamente)

2) o LSR fornece a lista, mas escolho qualquer resultado para ser o novo LWF e não funciona, continua congelado sempre no mesmo LWF que estava lá quando carreguei o zk

3) nenhuma pesquisa por string funciona; só redesenha a mesma tela sem fazer nada

4) módulo de tags, interface reduzida a isto:

(T) : Total de tags  (M) : 20 MAIS usadas  (P) : 20 POUCO usadas

Incompleta de novo. Um lixo. Até lista as tags atendendo às pesquisas ofertadas, quando seleciono uma tag ele lista os arquivos que a contêm, como esperado. Mas quando seleciono um resultado da lista, em vez de abrir o file ele volta para a tela inicial do módulo, sem mensagem

Faltam várias opções que funcionavam antes, principalmente a pesquisa de tags por string

Vamos parar por aí, porque já são muitos erros para tanto trabalho já feito. Parece que a solução modular é ainda mais difícil de construir que a monolítica, a cada tentativa parece que voltamos à estaca zero.

Me esclareça: parece que a cada tentativa você reconstrói tudo do zero. Não tem como pegar a versão que funciona, manter o que funciona e só mudar o que não funciona?

===========

1) Na tela principal, a opção l não carrega a lista dos últimos LWFs

2) Pesquisas por string na tela principal não funcionam, nada acontece

3) Módulo de tags:

a) pesquisa as mais usadas e pouco usadas, abre a lista de files que contêm a tag que escolho na lista de resultados, mas quando seleciono um file na segunda lista de resultados ele não abre e nem se torna LWF

B) pesquisa tags por string mas diante da lista de resultados ocorrem os mesmos erros do item a; esses dois erros já foram acusados no prompt anterior e você me mandou versões novas sem corrigi-los

4) Da lista do prompt anterior, na verdade, você corrigiu apenas os itens 1, 2 e a busca de tag por string

==========

1) tela principal, a opção d escolhe um file aleatório e o registra como LWF (certo) mas o abre automaticamente no editor externo, não é o comportamento esperado, deve apenas por como LWF e abrir no terminal com o less

2) quando escolho um resultado em qualquer lista (LSR ou L, na verdade) o script aceita a escolha, registra como LWF mas abre no editor externo, o que não devia fazer, devia só registrar como LWF e esperar opção do user na tela principal

3) pesquisas por string: não funcionam, nada acontece. (Mas o refine na tela de resultados da busca de tags por string funciona...)

4) módulo tags, quando se escolhe um file na lista de resultados ele abre no editor externo, não devia, era só para registrar como LWF e voltar à tela inicial do submenu gestor de tags

5) na busca de tags por string falta a função de gravar tags selecionadas pelo user numa lista provisória para ser depois copiada para o clipboard, a lista-cópia ou o buffer

====

1) no submenu de tags o q não quita o programa, ao que parece executa uma pesquisa por tags que contêm a letra q; a pesquisa de tag por string deveria receber pedidos com strings de pelo menos 3 caracteres

2) como já disse várias vezes, pesquisa por string não funciona; podemos consertar isso antes de qualquer outra coisa? É a função mais essencial

3) módulo de tags, não tenho opção para ver o que consta da lista de tags gravadas pelo user e nem como zerar essa lista

4) idem, falta a opção para exportar a lista de tags gravada para clipboard ou lista-cópia ou buffer

================

1) a busca por strings funciona mas não aparece a opção refinar no prompt após a lista de resultados

2) o extrator de links da tela principal parece funcionar, ao menos para links para files .md, mas quando seleciono um resultado na lista ele abre no editor externo, não devia, devia só virar LWF e voltar à tela principal.

3) a identidade visual do gestor de tags está ruim, voltar para a versão 2.18 que era assim

                             --- GESTOR DE TAGS ---
--------------------------------------------------------------------------------
(t) : Exibir o número Total de tags únicas encontradas no cofre
(m) : Exibir as 20 etiquetas Mais usadas (Frequência Alta)
(p) : Exibir as 20 etiquetas Pouco usadas (Frequência Baixa)
(v) : Ver conteúdo atual da lista de tags gravadas
--------------------------------------------------------------------------------
Dica: Digite qualquer termo com mais de 3 letras para filtrar tags específicas.
--------------------------------------------------------------------------------
(s)air : Retorna ao menu anterior       (q)uit : Encerra o programa
--------------------------------------------------------------------------------
Gestor >

4) o gestor de tags está "pegando" como tags #termo no meio de palavra / string; errado; só é tag #string precedido de espaço em branco ou começo de linha

5) por alguma razão o buscador de tags pouco usadas acusa "[13] #lITERATURA (1)"; mas se pesquiso por string na tela principal "#literatura" aparecem dezenas de files com essa tag; e quando, na lista de respostas do buscador de tags pouco usadas o user seleciona "13", ele lista dezenas de files, e não apenas um; parece estar se confundindo com a questão da cAIXA; o mesmo acontece com "#fRASES"; essa pesquisa deveria ser indiferente à caixa

=============

1) nova versão do zk_fileops encolheu para menos da metade; está certo isso?

2) o mesmo aconteceu com o zk.py; está certo?

O script não roda mais, nada acontece ao chamar zk

=========

1) precisa importar de novo aquela biblioteca que permite voltar no histórico de comandos do prompt e usar o CMd+R para pesquisar nesse histórico

2) o extrator de links da tela principal parece funcionar, ao menos para links para files .md e links de internet, mas quando seleciono um resultado na lista ele não o converte em LWF e volta à tela principal mantendo como LWF o que estava antes (aquele cujos links foram extraídos).

3) a busca por strings funciona mas não aparece a opção refinar no prompt após a lista de resultados

=============

1) a busca por strings funciona mas não aparece a opção refinar no prompt após a lista de resultados; o comando R na tela principal realmente oferece a função de refinar, pesquisando por string nova apenas nos files da LSR, como devia ser; mas a opção de refinar tem de aparecer no prompt que se segue à lista de resultados de toda pesquisa por string

2) a identidade visual do módulo system deve ser restaurada para a aparência que tinha na versão 2.18 que era

                          --- SYSTEM / MANUTENÇÃO ---
--------------------------------------------------------------------------------
(1) : Gerar Backup Completo (Zettels + Assets + Subpastas)
(2) : Gerar Backup apenas de arquivos Markdown (.md) da raiz
(3) : Gerar Backup apenas de arquivos de script Python (.py)
(4) : Backup dos Zettels (.md) para pasta TZ-2 (OneDrive)
(e) : Abrir os scripts do Zettelkasten Manager para edição (com backup prévio)
(f) : Abrir a pasta de Backups no Finder do macOS
(h) : Exibir o Histórico de Versões / Changelog
--------------------------------------------------------------------------------
(s)air : Retorna ao menu anterior       (q)uit : Encerra o programa
--------------------------------------------------------------------------------
System >

Note que modernizei o item (e) para a versão modular


============

A) no menu inicial aparece v. 3.26 embora estivéssemos na 3.27

B) Vamos melhorar o módulo file-ops

1) a opção "(3) : Abrir todos da Lista Cópia" não faz nada

2) as opções de pesquisar maiores zettels e maiores assets funciona mas não está informando o tamanho dos files

3) para preservar a identidade visual do conjunto o menu do file-ops deve terminar com

--------------------------------------------------------------------------------
(s)air : Retorna ao menu anterior       (q)uit : Encerra o programa
--------------------------------------------------------------------------------
File-Ops >

==================

1) O changelog não contém as atualizações da v.3.28; é para atualizar o changelog toda vez que fizermos alguma alteração, não espere eu pedir

2) no módulo file-ops a opção "(3) : Abrir todos da Lista Cópia" não faz nada

=====

Ótimo, adiante

A) um problema: o extrator de links do LWF funciona, permite escolher um resultado na lista de links extraídos, registra corretamente o link escolhido como novo LWF mas abre-o no editor externo imediatamente, o que é indesejado.

B) passemos à gestão de buffer:

1) A opção "(A) : Add Clipboard" funciona, mas poderia dar uma mensagem no prompt confirmando que executou, só dá para saber abrindo o buffer; o mesmo se aplica à opção "(D) : Add Data/Hora atual"

2) a opção "(D) : Add Data/Hora atual" devia escrever no buffer "Zettel criado/alterado dd-mm-yyyy"

3) a opção "(+) : Add LWF ao buffer" não faz nada

4) a versão 2.18 da interface era muito melhor, restaure:

                   --- ZETTELKASTEN MANAGER (MacOS 2026) ---
                            --- GESTÃO DE BUFFER ---
--------------------------------------------------------------------------------
(V) : ver conteúdo do buffer            (A) : ADICIONAR CLIPBOARD ao buffer
(E) : abrir em editor externo           (C) : copiar buffer p/ clipboard
(M) : abrir no editor Micro             (+) : add LWF ao buffer
(F) : mostrar buffer no Finder          (!) : add buffer ao LWF (com backup)
(Z) : ZERAR / Limpar buffer             (T) : add tags do LWF ao buffer
(H) : ver histórico (log de seg)        (D) : add Data/Hora atual ao buffer
(L) : add lista LSR (wikilinks)         (K) : add lista Cópia (wikilinks)
--------------------------------------------------------------------------------
Dica: Digite um texto longo (>3 carac) para salvá-lo direto no buffer.
--------------------------------------------------------------------------------
(S)air : Retorna ao menu anterior       (Q)uit : Encerra o programa
--------------------------------------------------------------------------------
Buffer >

5) falta implementar a função " (T) : add tags do LWF ao buffer"

6) idem para "(K) : add lista Cópia (wikilinks)"

======

A) tela inicial

1) continua informando v.3.28; essa informação devia ser automatizada e pegar o n da versão em algum ponto do script que mantivesse o nº atualizado, não ?

B) gestão de buffer

1) mude " (A) : ADICIONAR CLIPBOARD ao buffer" para " (A) : Adicionar clipboard ao buffer"

2) mude "(Z) : ZERAR / Limpar buffer" para "(Z) : Zerar / limpar buffer"

3) a opção "(H) : ver histórico (log de seg)" não faz nada

4) explique: quando digito uma string longa no prompt para ser add ao buffer, como faço para incluir quebras de linha?

================

Melhorias a fazer:

A) Menu file-ops: 

1) todos os itens de menu que estão EM CAIXA ALTA reescreva para estarem em caixa baixa, só a letra que o user deve digitar para selecionar a opção deve estar em caixa alta

2) na função "(AP): Zettels #APAGAR (contexto)" era melhor quando na lista de respostas o contexto vinha numa linha abaixo da linha com o nome do file, restaure

B) começando a aprimorar o módulo de tasks:

1) a identidade visual deve voltar a ser a da versão 2.18 com as mudanças que fiz abaixo:


                       --- GESTÃO DE TASKS (TAREFAS) ---
--------------------------------------------------------------------------------
(T) : Listar TODAS as Tasks pendentes (Ordenadas)
(A) : Listar Tasks ATUAIS (Hoje + 5 dias + Sem prazo)
(G) : Listar Tasks por TAG específica
(F) : Listar Tasks FINANCEIRAS (#contas)
(I) : Listar Tasks INTERNAS (#consertar #proj_zettletex)
(D) : Listar Tasks DISTANTES (> 60 dias)
(C) : Listar Tasks CONCLUÍDAS (Done)
(V) : Listar Tags VÁLIDAS em tarefas
(E) : Abrir editor externo com arquivos de Tasks pendentes
--------------------------------------------------------------------------------
(S)air : Retorna ao menu anterior       (Q)uit : Encerra o programa
--------------------------------------------------------------------------------
Tasks >

2) todas as pesquisas (atuais, distantes, financeiras, internas etc) devem incluir no prompt que segue a lista de resultados a opção de abrir todos os files que contêm as tasks constantes da lista de resultados no editor externo

3) as pesquisas de tasks por tag (#contas #finanças #internas #consertar #proj_zetteltex) devem considerar como resultados válidos apenas aqueles que contiverem a task procurada na task, não no file, ou seja, a tag buscada tem de estar na mesma linha onde está a task, não em outra linha ou parte do file, por exemplo em um file que contenha estas duas tasks:

- [ ] task1 #contas
- [ ] task2 #consertar

A task1 deve ser capturada pela pesquisa de tasks financeiras, mas não na de tasks internas; a task2 tem de aparecer nos resultados da pesquisa de tasks internas e não na pesquisa de tasks financeiras

4) Esta é uma linha da lista de resultados de uma pesquisa de tasks, mostrando uma task com prazo marcado:

[2] fazer a inspeção @due(2026-02-28) (@due: 28/02/2026)

Está errado, deveria ser assim:

[2] fazer a inspeção - v.: 28/02/2026

Quer dizer, suprime a parte do texto que contém a string que agenda a data e formata a data agendada do jeito que defini acima

5) Numa lista de resultados de uma pesquisa por tasks aparece

[9] reservar hotel em SP?? (@due: S/D)

Isso corresponde a uma task que consta assim no file original

- [ ] reservar hotel em SP?? #viagens #projetos

Está visto que essa task não tem prazo definido, a linha de resultado não deveria conter o "@due: S/D)", deveria só dizer:

[9] reservar hotel em SP??

C) Instrução permanente / persistente aplicável a todos os módulos e arquivos do projeto: não faça alterações na identidade visual / menus / telas / nomes e códigos das opções / funções sem eu pedir ou se não for necessário para atender alguma demanda de criação ou mudança de função; é para manter como está aquilo que aprovei e não pedi para mexer. Não quero ter de conferir a cada versão se você inventou alguma mudança nos menus e telas que eu não tenha encomendado, isso é muito trabalhoso.

 ========

A) módulo system

1) Embora o comando (e) faça corretamente os backups de todos os scripts do projeto (zk_tasks.py zk_fileops.py zk.py zk_buffer.py zk_core.py zk_system.py zk_tags.py zk_search.py) ele só abre no editor externo o zk.py

B) módulo de tasks

1) Os resultados de pesquisas que buscam as tasks com base nas tags como

(G) : Listar Tasks por TAG específica
(F) : Listar Tasks FINANCEIRAS (#contas)
(I) : Listar Tasks INTERNAS (#consertar #proj_zettletex)
E mais a função que busca as tasks com base na tag que o user digita no prompt

não precisam (não devem) incluir as tags na linha de resultados como aparece aqui:

[7] cancelar Disney  #finanças #contas #task - v.: 25/01/2027

Deveria ser apenas:

[7] cancelar Disney - v.: 25/01/2027

As tags devem aparecer nas linhas das listas de resultados apenas nas pesquisas que são tag-independentes (Todas, Atuais, Distantes, Concluídas) onde pode ser útil para o user saber qual tags pertencem a cada task 

2) aliás, a tag #task não devia aparecer em nenhuma linha de lista de resultado de pesquisa de tasks, já que toda task tem essa tag, a informação é inútil na lista de resultados

3) a opção "(V) : Listar Tags VÁLIDAS em tarefas" está entregando uma lista de 29 tasks, que parece ser a lista de todas as tags pendentes, em vez de entregar uma listas de tags que aparecem nas tasks existentes

4) digitando qualquer string no prompt do Tasks-manager, em vez de buscar tasks pela string (se ela corresponde a uma tag válida) ou informar que a string não é uma tag válida e mostrar a Lista das válidas, o script entrega a mesma lista de todas as tags pendentes mencionada acima

==============

A) geral

1) Já faz um tempo que você congelou o número da versão em 3.29, apesar de várias modificações terem sido feitas desde lá e elas não foram lançadas no changelogq

B) módulo system

1) a opção H voltou a estar quebrada, não faz nada; por que coisas que tinham sido consertadas voltam a quebrar? Você está mexendo em coisas que não pedi para mexer? Já pedi para não alterar nada que não corresponda aos pedidos que eu fizer

C) módulo tasks

1) tasks com tag #contas #finanças #internas #proj_zetteltex #consertar ou constantes de files que contenham essas mesmas tags ainda que fora da linha de task devem ser ignoradas na pesquisa do item A (tasks atuais)

D) tela principal / menu inicial

1) mudar o item "(C): Clip-list LWF" para "(P): emPilhar o lwf"

2) mudar "(P): copia lwf Path" para "(C): copia lwf Path"

3) atualizar os scripts para que essas funções sejam chamadas pelas letras novas estabelecidas acima

E) módulo file-ops

1) mudar de "(4) : gestão da lista de cópia" para "(4) : gestão da Pilha"

2) mudar "(3) : abrir todos da lista cópia" para "(3) : abrir todos da Pilha"

F) Módulo gestão de buffer

1) mudar "(K) : add lista Cópia (wikilinks)" para "(K) : Kopia pilha para buffer"

2) Mude "Dica: Use '\n' para incluir quebras de linha no texto direto." para "Dica: 'string' para bufferar texto, '\n' para quebrar linha no texto."

G) Geral: exceto onde informado especificamente, a mudança dos itens de menu não muda nada na lógica / funcionamento das funções

======

Com isso acabamos a restauração da versão 2.28 agora modular. Parece que temos de volta todas as funções e sem erros. Agradeço, excelente trabalho. Agora vamos expandir o projeto.

Quero sua opinião sobre a viabilidade de criar uma "área de visualização" na tela principal, situada logo abaixo da linha horizontal ------ que se segue às stats e antes de uma segunda linha horizontal de 80 colunas de largura que ficará antes do nome do Arquivo Atual. Essa "área de visualização" terá 13 linhas de altura (lembre-se que nossa "interface" tem sempre 80 colunas.

A área de visualização (vou chamar doravante de visor) exibirá por default uma parte do texto do LWF (o texto será simplificado eliminando as quebras de parágrafo, convertido num bloco / parágrafo só, e o visor mostrará a parte do conteúdo que couber na área de 13 linhas, terminando com ... se não couber tudo. Se o texto for pequeno e não preencher as 13 linhas, o script manterá em branco as linhas não usadas: o visor deve ter um tamanho consistente permanente para dar a impressão de que é uma "telinha"

Se isso for possível, te explico as demais ideias que tenho para o visor (ele deverá permitir que o user opte por exibir a parte que couber no espaço da LSR, do buffer, da Pilha, do histórico de LWFs ou do changelog). Se parecer que isso vai ser tão complexo que merece um arquivo .py separado, sugira isso.

Se parecer viável, já forneça uma versão de teste e coloque no menu da tela inicial uma linha nova assim: (cuide da formatação / distribuição das colunas)

(H): gestão da pilHa  (1/2/3) LWF / Help / LSR  (4/5/6) Buffer / Pilha / Hist.


===============

Está ótimo o visor. Vamos melhorá-lo.

1) O menu principal está acabando assim:


(M): ver lwf no Micro     (C): copia lwf Path        (F): ver lwf no Finder
--------------------------------------------------------------------------------
(H): gestão da pilHa      (1/2/3) LWF / Help / LSR   (4/5/6) Buffer / Pilha / Hist.
--------------------------------------------------------------------------------
Escolha ação:


Mude para isto aqui:


(M): ver lwf no Micro     (C): copia lwf Path        (F): ver lwf no Finder
(H): gestão da pilHa      (1/2/3) LWF / Log / LSR    (4/5/6) Buffer/Pilha/Hist.
--------------------------------------------------------------------------------
Escolha ação:


2) Lembrar, então, que o zk_view precisa ser incluído nas rotinas de backup (por encomenda do user e os que precedem a abertura para edição em lote) e abrir os scripts no editor externo que constam do módulo system, confirme se está ok essa parte

3) Na tela principal, adicionar as opções para o user alternar o modo do visor: 1 para mostrar o LWF, que é o default e a lógica está boa. 2 para mostrar o changelog, consolidado em bloco como fizemos como LWF, as linhas que couberem no visor, etc. 3 para mostrar a LSR, um item por linha, os itens que couberem no espaço, linhas em branco preenchendo o espaço vazio se a lista for curta. Não precisa por os números dos itens, só os nomes, um por linha. 4 para mostrar o conteúdo do buffer, no formato que estiver no arquivo buffer, sem reformatar, mesmas regras sobre aproveitamento do espaço quanto ao mais, mensagem avisando se o buffer estiver vazio. 5 para mostrar a Pìlha, mesmas regra do item 3, mensagem se a pilha estiver vazia. 6 para mostrar a lista dos últimos LWFs, um item por linha até encher o espaço, não precisa numerar a lista. 

4) Gostaria que a linha da tela inicial que informa o nome do LWF fosse alterada, em vez de 

📍 ARQUIVO ATUAL (LWF): nomecompleto

Exibir

📍 LWF: parte do nome que couber na linha (que tem 80 caracteres no total) com ... no final se o nome não couber inteiro. As reticências também têm de caber nos 80 caracteres

5) Na linha imediatamente abaixo dessa, criar uma linha de stats que informará (em relação ao LWF):

Size: xx Kb | LastUp: dd-mm-yy | Tags: #tag2 #tag2

LastUp é a data da última atualização do file. Tags são as contidas no texto do LWF, na ordem em que aparecem no seu texto, mas limitadas à largura da linha (80 caras.), se não couber tudo reservar espaço para ...


===============

1) Não sei por que, mas o changelog foi praticamente esvaziado na última alteração. Não quero que isso aconteça, quero que seja cumulativo. Tem como recuperar as informações que foram suprimidas e restaurar o changelog bem completo?

1.b) Aliás, o linha de stats no alto da tela inicial continha não atualizando o nº de versão

2) Vamos mexer no cabeçalho da tela principal, que está assim:

                   --- ZETTELKASTEN MANAGER (MacOS 2026) ---
--------------------------------------------------------------------------------
             v. 3.30 | 3159 Zettels (9 Mb) | 840 Assets | 483 Tags

Para que essa linha de stats tenha mais um item, no final, informando o modo atual do visor, tipo

| View: LWF

Ou

| View: Changelog
| View: LSR
| View: Buffer
| View: Pilha
| View: past-LWFs

Mantenha a centralização / formatação

3) Na mesma tela inicial mude "(C): copia lwf Path" para "(C): Captura lwf". Refazer a função, que atualmente só copia o path para o clipboard. Agora o "C" abrirá um prompt perguntando "Capturar (F)ullpath, (N)come, (B)asename ou (L)link, em(P)ilhar ou mostrar no (F)inter?"

F será o que já era, copia o fullpath para o clipboard
N copia o nome do file no formato Basename.md para o clipboard
B copia para o clipboard só o basename
L copia o [[basename]] no formato wikilink, entre colchetes duplos, para o clipboard
P colocará o LWF na pilha como já era feito com a função chamada na tela principal pela letra P
F mostrará no Finder o LWF como fazia a letra F na tela principal

Em todo caso o prompt exibirá mensagem "Copiado 'tal-coisa' para o clipboard" indicando o que foi que copiou, ou "empilhado o LWF" ou "Aberto o Finder no LWF" e voltará para a tela inicial

4) Com isso, apagar do menu da tela principal o item "(P): emPilhar o lwf" por "(R): Referentes do lwf" e transferir para essa opção o que faz / fazia a opção de buscar referentes que atualmente está no módulo file-ops; por mim não precisa mover a parte lógica de um .py para outro, tanto faz, pode optar pelo que for mais eficiente do ponto de vista da administração futura do pacote. Não mude o menu do módulo file-ops por ora, ainda vou pensar sobre ele. 

5) Remover do menu principal o item "(F): ver lwf no Finder" mas sem mexer na lógica, imagino, porque a função continuará sendo executada a partir do menu principal, só que como sub-item do item C, ver item 3 da lista acima. 

Substitua esse item por 

(</>) voltar / avançar

Estou supondo que é permitido usar < e > no prompt para disparar comandos. Se não for, sugira letra ou número para figurar no lugar desses sinais. A ideia é criar uma navegação tipo voltar e avançar no histórico de LWFs. Temos uma lista de LWFs recentes, acessíveis no menu inicial com a letra L. E nessa lista que os botões < e > vão avançar e retroceder, de forma circular. Voltar deve carregar o LWF anterior ao atualmente exibido, avançar o que for mais recente na lista de últimos LWFs usados. Se o user pedir > e o LWF atual for o mais recente da lista (o que deve ser comum), a navegação avançará para o último (o mais antigo) da lista de LWFs anteriores. Se a instrução estiver confusa não crie a função e me peça explicações.

==================

1) quando entro "lsr" no prompt da tela inicial, em vez de entregar a lista LSR o script trata "lsr" como uma string para pesquisar nos files e dispara a rotina de busca por string

2) quando entro "l" enter no prompt principal, em vez de exibir a lista de histórico de LWFs ele não faz nada e redesenha a tela

3) por isso não tenho como conferir exatamente mas parece que a função < e > não está seguindo a lista de últimos LWFs usados, às vezes aparecem uns files aleatórios que não pareciam estar na lista

4) a opção "d" não funciona mais, não faz nada, redesenha a tela

5) a opção "x" idem, não extrai links e redesenha a tela

6) não sei se expliquei bem como queria que a navegação funcionasse. Imagine que a lista dos últimos LWF tenha só 5 itens:

Item1
Item2
Item3
Item4
Item5

O item1 é o LWF mais recente e está selecionado (é o LWF atual). A lista é em ordem decrescente de uso, o que foi usado antes do item1 é o item2, e o que foi usado antes do item2 é o item3

Se estou no item1 e peço > ele deve ir para o item2. Se estou no item2 > deve levar para Item3 e < levar para Item1.

Se estiver no item1 e pedir < ele tem de ir para Item5, porque não há nada "em cima" do item1 e o navegador deve rodar para o fim da lista e subir desde lá.

Se a explicação estiver confusa ou minha ideia colidir com a lógica do script, ou criar dificuldades para ser executada exigindo alterações profundas, sugira outra solução. 

======

1) Temos um problema e não sei resolver, na rotina de navegação no histórico de LWFs. Imagine a lista:

Item1
Item2
Item3

Se estou no item1 e peço > ele corretamente vai para Item2. Só que Item1, em vez de ir para o fim da fila, passa a ser o segundo da lista, que fica assim:

Item2
Item1
Item3

Se eu estiver no item2 e pedir > ele volta para o item1 e cria-se um lopping entre esses dois itens. Não devia ser assim. Se estou no item1 e avanço para item2 o item1 devia se tornar o último da fila, não o segundo. Dá para fazer isso?

2) A tela do módulo buffer está corretamente mostrando o título do "sistema" seguido do subtítulo (nome do módulo):

                       --- ZETTELKASTEN MANAGER v3.34 ---
                            --- GESTÃO DE BUFFER ---
--------------------------------------------------------------------------------

Quero que os outros módulos (system, file-ops, buffer, tasks, tags e Pilha) sigam esse mesmo padrão de identidade visual. 

3) qual a possibilidade (e o grau de complicação dos scripts resultante) de partes dos itens da tela aparecerem em negativo, isto é,  fundo escuro e texto claro? Se isso fosse possível, gostaria que a linha de título e a linha do nome do LWF atual ficassem em negativo. Poderia, se for possível, gerar uma versão da tela principal assim, para eu ver?

===================

1) adaptar todas as telas de módulos (submenus) para o padrão de título e subtítulo, e implementar o "visual negativo" no título em todos os submenus

2) Em todos os prompts a linha que apresenta as opções do user, (por exemplo "(Nº) Selecionar LWF   (R)efinar busca   (S)air") devem estar no "visual negativo"

3) o changelog continua defasado e pouco minucioso

4) na tela principal temos duas opções com chamada pelo R. Mude "(R): Referentes do lwf" para "(F): aFiliados ao lwf" e coloque a função de buscar referentes acionada pela letra F, deixando a letra R para Refine; 


===================

1) No módulo gestão de pilha, identidade visual, depois de 

 --- GESTÃO DA PILHA (4 itens) ---

deve haver a linha horizontal como 80 colunas de largura

2) em todas as listas de resultados que aparecem depois de limpar a tela o título da lista de resultados deve ser considerado subtítulo, e acima dele deve aparecer em negativo o título do sistema seguindo a identidade visual do conjunto

3) a string "[[:toc:]]" e qualquer outra que comece com "[[:" não é um wikilink válido e deve ser ignorada em todas as funções que trabalham com wikilinks

====================

1) o módulo / menu " --- GESTÃO DE BUFFER ---" não está seguindo a padronização de identidade visual, o título e a linha de opções não estão "em negativo"

2) Se for possível gostaria de criar um visor para o gestor de buffer, seguindo em tudo a ideia do visor da tela principal, mas este mostrará apenas o conteúdo do buffer. Se o conteúdo não couber nas 13 linhas do espaço, o visor mostrará o final do buffer. Pode conectar o texto todo do buffer num bloco / parágrafo só para caber mais texto no espaço. 

3) esse submenu Gestão de Buffer foi alterado sem ordem, desfazendo alterações que eu havia comandado antes. Ele está assim:

--------------------------------------------------------------------------------
Dica: Use '\n' para incluir quebras de linha no texto direto.
--------------------------------------------------------------------------------

Não devia haver a linha horizontal antes da linha da Dica, e o texto deveria ser "Entre 'string' para bufferizar texto e use '\n' para quebrar linha no texto"

=======

O visor do gestor de buffer está ótimo, mas não era para apagar o menu de opções do gestor de buffer e substituí-lo pelo visor. Restaure o menu de opções, fazendo nele apenas a correção que pedi no prompt anterior (a respeito do texto da dica e a linha horizontal) e acima da lista de opções deixe o visor recém criado.

Esse tipo de menu simplificado que você pôs lá:

(V) Ver no Less  (E) Editar  (T) Tags do LWF  (K) Pilha  (L) LSR  (D) Data  (X) Zerar

é péssimo e não combina com a identidade visual do conjunto, não fala mais assim. Aliás, não mude o que eu não pedir para mudar. 


=====================


Próxima etapa: a Pilha. Diferenciando: o Buffer é um arquivo provisório para anotações temporárias em geral. A Pilha é uma pilha de nomes de zettels, para serem depois manejados em lote (deletados, renomeados, terem tags adicionadas ou excluídas, etc). Uma lista de arquivos que serão o
bjeto de ações em lote.

Portanto na pilha devem constar apenas nomes de arquivos com extensão .md - se o user tentar inserir lá algo que não seja isso, o script deve rejeitar e informar o erro

Como a pilha servirá para ações em lote, que dependerão de funções várias a serem desenvolvidas, peço que sugira a estratégia mais eficiente: criar um novo módulo .py para gerir a Pilha, ou tratá-la dentro de um dos .py já existente.

No menu do módulo file-ops exclua os comandos "(N) : abrir LWF no micro" e "(4) : gestão da Pilha". O primeiro já funciona no menu principal, e o segundo será movido para lá, e a função correspondente (a parte lógica) veja onde é melhor ser colocada

Inclua no módulo file-ops uma opção para deletar o LWF, e crie a função correspondente, que moverá o LWF para a lixeira do sistema mas manterá um arquivo oculto permanente que registrará todos os zettels deletados pela função, com data e hora da operação.

Crie no mesmo menu a função / opção para abrir esse histórico de deletados no editor externo

Quanto ao que sobre no menu do módulo file-ops, redistribua em duas colunas mantendo o estilo / identidade visual, e sem mudar mais nada

O desenho do submenu Gestão da Pilha está bom, dentro do padrão visual. Apenas decida se é caso de movê-lo do lugar onde está para um script próprio do módulo da pilha. Vamos deixar aquele visualizador da pilha que já está no alto, fixar a altura dele em 13 linhas, seguindo os padrões já definidos para os outros visores. Abaixo do visor, linha horizontal e abaixo dela o menu de opções, cujos itens irão sendo definidos, deverá ser em duas colunas com as (L)etras definidoras de opções alinhadas. Deixar para a linha "em negativo" as opções de sair e quitar. Para o menu de opções do gestor de pilha crie por ora itens para 

(Z)erar a pilha             (C): basenames para clipboard
(F)ullnames para clipboard  (L): wikilinks para clipboard
(R)emover item da pilha     (DEL): apagar zettels empilhados
(G): taGuear empilhados     (U): Untaguear empilhados
(EZ): empilhados no editor  (K): clip links em linha única
(P): paths para clipboard   (V)er a pilha no less
(EP): texto pilha no editor (H) abrir logs no editor

Zerar pilha é a mesma rotina que já existe com esse nome, escolha onde ela deve residir. Mensagens no prompt para avisar do sucesso das operações antes de voltar para o menu, neste caso e em todos os demais.

As cópias para clipboard só mudam o formato, F copia fullname (com extensão), C só os basenames e L copia os basenames no formato [[wikilink]], em todos os casos um nome em cada linha. P põe os paths no clipboard, um por linha. Mensagens no prompt para avisar do sucesso das operações antes de voltar para o menu.

K copia para clipboard os basenames no formato [[wikilink]] mas todos os nomes na mesma linha separados por ", "

R abre um prompt que pede um número da lista, o script apagará da pilha o zettel que corresponder ao número escolhido.

V mostra o conteúdo da pilha na tela (less); EP abre o texto da pilha no editor; EZ abre no editor associado os zettels listados na pilha; 

DEL: apaga (move para a lixeira do sistema) todos os zettels com as cautelas de backup que pedi para a opção de deletar um só zettel no menu file-ops. Mas aqui na deleção em lote o script pedirá confirmação do user antes de executar "Tem certeza? S/N"

T e U lidam com tags válidas; se o user pede T o prompt pede a string; se a string não for uma tag válida, recusa; se for, insere essa tag no final de todos os zettels empilhados (precedida de um espaço em branco); a opção Untag remove uma tag de todos os empilhados, o prompt lista as tags que constam em comum em todos os zettels da pilha (mensagem de erro se não houver nenhuma assim) numa lista numerada para o user escolher; será conservado um arquivo oculto com o histórico das atribuições e remoções de tags com data e hora e lista dos files afetados. Essa lista será acessível pela opção H abaixo.

H abrirá no editor externo os arquivos de histórico de segurança do módulo (o de deletados e o de tags mudadas)

========

1) o nº da versão não foi atualizado, por que? Atualizar, fazer o changelog; o changelog minucioso e verboso deve ser atualizado em cada versão nova, e o número da versão atualizado sempre, essa instrução é permanente / persistente.

2) uma regressão indevida: na tela principal a pesquisa por strings pesquisa diretamente pelo conteúdo sem perguntar se o user quer pesquisar por nome.

3) reorganizar o menu do módulo da pilha só com estes itens

(Z)erar a pilha               (C): operações de Clipboard
(P): por itens na Pilha       (A): Abrir a pilha
(R)emover item da pilha       (DEL): apagar empilhados
(G): taGuear lote             (U): Untaguear lote

Outras funções já criadas serão movidas para itens de prompt; os comandos C P e A abrem prompts que oferecem estas opções:

(C): operações de Clipboard
(C) Basenames, (L) wikilinks, (F)ullnames, (K) links numa linha, (P)aths

- C copia os basenames para o clipboard, D os full names, L os empinhados no formato [[wikilink]] um em cada linha, K os wikilinks numa linha só separados por vírgula espaço, P os caminhos completos

(P): por itens na Pilha
(L) LWF, (S) LSR, (H) histórico LWFS, (A)filiados LWF, (K) linkados LWF

- funções para incluir itens na Pilha: L inclui o LWF, LSR a lista dos resultados da última pesquisa, H a lista dos últimos LWFs, A os zettels que linkam para o LWF, K os zettels (apenas os zettels, isto é,  arquivos com extensão .md) que constam do texto do LWF (esse comando é novo, desenvolver a função correspondente)	

(A): Abrir a pilha
(E) texto no editor ou (L) na tela, (Z)ettels ou (H) logs no editor

- E abre o texto do arquivo pilha no editor externo, L abre esse texto no less, Z abre os setters empilhados no editor externo, H abre os logs de deletados e de taqueados/untagueados no editor externo.

4) função estragada: no módulo de tags o prompt não aceita mais que digite uma string de 4 ou mais caracteres para procurar automaticamente tags que contenham essa string; Se seleciono o P ele abre um menu para digita um prefixo, e pesquisa tags que COMEÇAM com a string, o que é útil e deve permanecer, mas a pesquisa por digitação livre tem de voltar: o user deve poder digitar uma string de 4 ou mais caracteres direto no prompt e o script procurará tags válidas que contenham a string em qualquer parte do seu texto, não apenas no início. Ficam as duas opções, o comando que o P aciona pesquisa pelo prefixo e aceita qualquer comprimento de string, o comando de digitar string direto no prompt exige 4 ou mais e procura a string em qualquer parte do nome da tag;  #nomedetag por exemplo deve aparecer nos resultados da busca por "nomed" e também na busca por "datag"

=============

Vamos voltar ao aperfeiçoamento do Zettelkasten Manager. Vou subir as versões mais recentes dos .py para você usar como base do trabalho. Repito as instruções permanentes / persistentes: (a) não altere nada que eu não tenha pedido ou que não seja estritamente necessário para atender ao que eu pedi; (b) não mexa na interface / identidade visual do sistema sem eu pedir ou autorizar; (c) entregue sempre os .py novos em versão integral, todo o texto do começo ao fim, para eu poder copiar e colar inteiro substituindo integralmente o texto da versão anterior; (d) se isso aumentar a eficiência, entregue os novos .py um de cada vez aguardando o "prossiga" antes de gerar o seguinte.

==============

Problemas:

1) Tela principal, comando X extrai corretamente os links, mas quando escolho um resultado da lista nada acontece, apenas volta para a tela inicial.

Aliás não abre os arquivos de imagem, nem PDFs, nem links de internet, nada

2) links de internet, links para arquivos de imagem ou pdf, enfim, qualquer arquivo que não tenha extensão .md não deve aparecer nunca nem na LSR nem da lista de últimos LWFs usados. 

3) Módulo de pilha, a função Untaguear não faz nada, só mostra rapidamente a mensagem "Função untag em implementação estrutural". Não está pronta ainda?

4) Quando não há um LWF selecionado (porque foi apagado, por exemplo), a tela inicial bagunça. Sugiro esta solução: se não existir um LWF ativo, sortear aleatoriamente um zettel, por como LWF ativo e dar uma mensagem avisando "Não havia LWF ativo, um foi sorteado", algo assim. Menos quando o user seleciona numa lista um arquivo inválido (deletado/inexistente), aí o script devia avisar isso "Zettel inexistente / inválido" e manter o LWF previamente ativo.

5) o subitem H do item A (abrir pilha / logs) está abrindo corretamente os logs, mas no console, eu prefiro que os abra no editor externo associado

============

1) Infelizmente o comando X na tela principal não funciona mais, dá tela de resultados vazio (0 links) por mais que o LWF tenha vários links dentro

2) o comando de untaguear está dando positivo para tags que não existem nos files da pilha e para tags inválidas (que nem existem no acervo todo).

3) no módulo da pilha o comando Del não funciona mais, só redesenha a tela

 4) o subitem H do item A (abrir pilha / logs) está abrindo corretamente os logs, mas no console, eu prefiro que os abra no editor externo associado


========

Foi 

1) o subitem H do item A (abrir pilha / logs) está abrindo corretamente os logs, mas no console, eu prefiro que os abra no editor externo associado; terceira vez que peço isso, se não for possível fazer isso me avise e sugira alternativas.

2) extrator de links está captando apenas files .md. Parou de captar links de internet como "https://www1.folha.uol.com.br/cotidiano/2026/03/1-em-cada-5-adolescentes-brasileiros-relata-ter-sofrido-exploracao-ou-abuso-sexual-online-aponta-unicef.shtml", links de imagem e para PDFs. Talvez tenha havido uma confusão com uma instrução minha anterior: arquivos não-.md não devem aparecer na LSR nem na lista "histórico de LWFs" quando essas listas são pedidas pelo user na tela inicial ou no gestor de buffer ou gestor de pilha. Mas é indispensável que links para PDFs, imagens, sites de internet, documentos .docx ou similares, csv, xls etc apareçam nos resultados do extrator de links, que tem de abrir esses links no app associado à extensão quando o user o pedir

3) o comando F na tela inicial não funciona, não busca mais os aFiliados do LWF, apenas redesenha a tela

==========

Foi 260309143322

1) o extrator de links voltou a extrair e abrir links de internet mas ainda não acha os links para pdfs e imagens no LWF, não os menciona na lista de resultados

2) o subitem H do item A (abrir pilha / logs) está abrindo corretamente os logs, mas no console, eu prefiro que os abra no editor externo associado; QUARTA vez que peço isso, se não for possível fazer isso me avise e sugira alternativas.


=============

Foi 260309144445

Questão dos logs resolvidos, mas:

1) o extrator de links ainda não acha os links para pdfs e imagens no LWF, não os menciona na lista de resultados - repete o mesmo erro já acusado

=============

Foi 260309145750

4) o comando C da tela inicial (capturar LWF) deve incluir mais duas funções: 

a) capturar para o clipboard todo o conteúdo do file; 

b) capturar para o clipboard o conteXto do LWF, ou seja, copiar para o clipboard, numa linha só, precedida de "Zettel criado / alterado em dd-mm-yyyy — " estas informações: (a) os links citados no texto do LWF e que contenham, em seus respectivos conteúdos, a tag #indexes, no formato [[wikilink]], itens separados por ", "; (b) as tags contidas no LWF, lista precedida de " — " e tags separadas umas das outras por um espaço em branco.

c) o prompt ficaria com "Capturar (F)ullpath, (N)ome, (B)asename, c(O)nteúdo, conte(X)to ou (L)ink, em(P)ilhar ou ver no (Fi)nder" e  pode ser dividido em duas colunas como você fez nos subitens do módulo de Pilha como o Abrir Pilha


=====================

Foi

5) no módulo gestor de tags, uma função para capturar as tags do LWF, a serem jogadas no clipboard todas numa linha só separadas por espaço em branco, lista precedida de um espaço em branco.

==============

Foi v4.0 260309151715

em todos os módulos e também na tela principal incluir uma linha formatada "em negativo" contendo links de navegação para as telas

--- HOME | FILEOPS | SYSTEM | PILE | TAGS | TASKS | BUFFER --- 

Quero que isso fique disponível para permitir navegação entre os módulos a partir do prompt principal de cada módulo, de modo que o user possa trocar de módulo sem ter de voltar à tela inicial para isso

A linha "menu de navegação" ficaria, na tela inicial, logo depois da linha horizontal ---- que se segue à linha de stats, e nos módulos logo abaixo da linha horizontal ---- que se segue ao subtítulo / título do módulo.

Não sei como criar os comandos / strings que o user teria de digitar no prompt sem criar conflito com as já usadas para as opções dos menus. Tem como implementar alguma coisa usando combinações de teclas tipo Ctrl+1 Ctr+2 ou algo assim, ainda que importando alguma biblioteca do Python ou criando mais um módulo para gerir a navegação? Se for preciso digitar um comando no prompt, tente fazê-lo o mais curto possível sem causar conflitos


======

Ficou ótimo e tem um defeito só: em qualquer tela/módulo, a opção sair não sai para Home, volta para a tela anterior no histórico de navegação (aparentemente). E teclar "/h" em qualquer tela faz o mesmo, não retorna para Home fica voltando no histórico de navegação.

============

Infelizmente aconteceu aquilo que tantas vezes pedi para evitar: mexeu em coisas que eu não pedi, coisas que funcionavam antes pararam de funcionar e tenho de reconferir todas as funções. Por favor corrija apenas o que eu pedir não mexa no que está aprovado.

Menu Home, o comando l fornece a lista dos LWFs recentes mas quando seleciono um nº da lista o LWF não é mudado, está congelado no mesmo (curiosamente o zettel que escolhi da lista aparece no visor, mas para todas as outras funções o LWF continua congelado no anterior

O mesmo acontece com a lista de resultados LSR, seleciono um resultado e o LWF permanece o mesmo, não aceita o comando para chamar o resultado

Como não consigo escolher o LWF não consigo testar as demais funções. 


============

Foi

A nova versão resolveu o defeito acusado no meu último pedido e estragou várias coisas que antes funcionavam:

1) módulo file-ops, a opção sz dá uma lista de 10 itens com os tamanhos mas sem os nomes, em vez de nomes em cada linha tem um .

2) idem, opção sa só mostra 1 item na linha de resultados o que obviamente está errado, deviam ser os 10 maiores files não-.md na pasta e subpastas

3) idem, opção in não faz nada

4) idem, opção ap não faz nada

5) idem, opção ur não faz nada

6) opção h abre o log no console, mude para abrir no TextEdit

7) nos módulos system, buffer, tags e pile aparentemente tudo funciona perfeitamente, por favor tente não mexer lá a não ser que seja estritamente necessário

8) módulo tasks, opção g está aceitando qualquer string sem filtrar para recusar strings que não correspondam a uma tag válida

==========

Feito

1) modulo file-ops, a pesquisa por zettels com tag #apagar devia dar o contexto conforme ocorria nas versões mais antigas; explico: apenas a pesquisa por zettels com a tag #apagar no módulo file-ops (e nenhuma outra pesquisa do conjunto) deve captar um contexto e exibi-lo na lista de resultados. Consiste no restante da linha que contiver a tag #apagar, começando depois do espaço em branco que se segue ao termo #apagar e indo até o fim da linha.

================

v5.0

Vamos dar por definitiva a versão 4 como está, parece funcional. Vamos começar a projetar uma versão 5, que incluirá novas funcionalidades, especialmente mecanismos de pesquisa mais avançados.

1) Atualize a versão para 5.0 em todos os módulos; preencha o changelog

2) Precisa arranjar um jeito de mover o changelog e a numeração de versão para algum arquivo externo único para automatizar e tornar melhor o fluxo de sua atualização: esses dados têm de poder ser atualizados num lugar só e das as funções têm de ir buscar lá as informaçções sobre. Você preparou várias revisões desde o começo da versão 4 e todas elas constam como 4.0, isso não devia acontecer, cada vez que muda qualquer coisa nem que seja num único módulo tem de atualizar o número da versão e anotar no changelog. Por isso nem número de versão nem changelog pode ser hardcoded nos módulos e não pode ser necessário mexer em mais de um documento para atualizar changelog ou número de versão.

2.a) Aproveite para mexer no módulo de system, nas opções que fazem backup dos scripts .py, o nome do file zip deve conter além da informação de data e hora o número da versão;

3) Vamos - para evitar mexer nos menus incluindo itens - sofisticar o prompt que aparece depois da lista de resultados na pesquisa básica (pesquisa por string de texto que o user entra  no prompt da tela Home). 

hoje ele diz

(Nº) Abrir/Selecionar   (R)efinar   (S)air

e mudará para

(Nº) definir LWF, (R)efinar, (C)ontexto, pró(X)imas,(S)air

3.a) Vamos incluir primeiro a opção (C)ontexto, e criar a função; consiste em republicar a lista de resultados, numerada como de costume, para que o user possa abrir um resultado digitando o nº no prompt, mas desta vez a lista conterá para cada resultado uma linha com o nome do file que contém a string (as strings, se já for uma pesquisa refinada) seguido de uma ou mais linhas que conterão as 30 palavras que aparecem antes e as 30 que aparecem depois da string no file; se o file contém a string mais de uma vez, haverá uma linha de contexto para cada ocorrência.

3.b) A segunda opção a incluir é pró(X)imas, e a função refinará a pesquisa (ou seja, pesquisará apenas nos files que constam da LSR) mas a segunda string (a string que refina a busca) será considerada presente apenas se estiver no máximo 120 caracteres distante da string usada na primeira busca, podendo aparecer antes ou depois da outra string, a ordem não importa; a lista de resultados refinados também os apresentará em duas linhas, a primeira com o nome numerado do file-resultado e a segunda com o contexto igual ao do item acuma; se houver mais de uma ocorrência dos dois termos próximos um do outro no mesmo file, acrescenta-se uma linha de contexto para cada ocorrência

3.c) Nas novidades acima a segunda listsa de resultados sempre será seguida do mesmo prompt da pesquisa "normal", isto é, 

(Nº) Abrir/Selecionar, (R)efinar, (C)ontexto, pró(X)imas,(S)air

4) Agora o módulo tags

4.a) tag com contexto: a lista de resultados da pesquisa de tag por string digitada livremente pelo usar no prompt principal do módulo será seguida por um prompt precedido desta mensagem:

(Nº): buscar tag | (G): gravar tag p/ lista | (C): contexto | (S)air

A função contexto pedirá ao user que selecione uma tag da lista de resultados, e selecionado um resultado válido apresentará uma segunda lista, contendo os files que usam aquela tag selecionada, mas a lista conterá, abaixo da linha numerada com o nome do zettel, a linha (ou linhas) de contexto.

O contexto aqui consiste nas 25 palavras que precedem a tag objeto da busca. Mas é preciso filtrar esse resultado: essas 25 palavras não devem conter #tags nem [[wikilinks]], deve-se contar as 25 palavras que precedem a tag-alvo e mencioná-las excluindo #tags e [[links]] de qualquer espécie (links para outros zettels ou para anexos, pdfs imagens sites de internet)

4.b) aproveitando para melhorar o módulo tags, a opção para gerir tags gravadas (opção G do menu principal do módulo) deve incluir as opções de copiar para clipboard e remover item da lista

(A)dd ao buffer | (Z)erar lista | (C)lipboard | (R)emover item | (S)air

4.b.1) a opção de copiar para clipboard copiará a lista de tags gravadas mas numa linha só, precedida de espaço em branco e tags separadas por ", "

4.b.2) a função de remover será similar à que consta do módulo pile, oferece um prompt para o user escolher um item da lista, remove-o, redesenha a lista e oferece de novo a lista de resultado e o mesmo prompt

4.c) ainda sobre a opção de gravar tags no modulo de tags, quando abre o prompt para selecionar uma tag da lista devia mostrar no prompt quais as que já estão gravadas, para o user não escolher algo que já consta

5) Buffer: 

5.a) criar uma função para consolidar todo o texto do buffer num parágrafo só, joining as linhas mas deixando um sinal de "(...) " no lugar onde ficava a quebra de linha, antes de copiá-lo para o clipboard; o item de menu que hoje diz:

(C) : copiar buffer p/ clipboard

mudar para:

(S/C): clipboard Simples/Compacto

A opção S corresponde à função que já existia, copia o conteúdo do buffer para o clipboard com a formatação que está atualmente, sem mudar. A opção C chama a função nova que compacta o texto num parágrafo só antes de copiar para o clipboard.

Em ambos os casos, copiado o buffer para o clipboard ele será zerado.

5.b) aproveitando: no modulo buffer a opção t devia filtrar e impedir o adicionamento de #tag repetida (que já consta do texto do buffer)

6) na tela Home, a opção de sortear zettel randomicamente deve filtrar (excluir do sorteio) zettels que contenham (a) menos de 200 caracteres de conteúdo; (b) zettels que contenham alternativamente uma destas tags: #ONO #contas #admin #powershell #ajuda #docs #work #bc3 ; 



============

v6.0 goodies

7) Em todas as telas principais de módulo só tenho dois jeitos de voltar para Home, teclando "/h" ou "s" seguidos de Enter. Gostaria que todas as telas aceitassem um Enter vazio (sem nada no prompt) como comando para voltar para Home. Note que estou falando só dos prompts das telas principais de cada módulo (os que hoje aceitam os comandos de navegação tipo /b /g /k) e não dos prompts que vêm depois das listas de resultados e prompts derivados/subordinados etc

8) é possível por em negrito o texto de todas linhas que aparecem "em negativo"?

9) Favor remover as linhas horizontais ----- que vêm imediatamente antes ou imediatamente depois das linhas "em negativo, deixando as que não se enquadram nessa condição

10) NEXT / PREV

11) remover do menu da tela Home estes itens

(Y): sYstem stuff         (I) : menu fIle-ops        (B): gerir Buffer     (K): gerir tasKs  (G)estor : Menu de Tags      (Q)uit : Encerrar script     (P): gestão da Pilha

Crie um novo item de menu, (+): mais opções, deixe sem função por ora, depois vemos

Atente: não é para eliminar as funcionalidades, não quero perder a possibilidade de teclar q enter para quitar ou b enter para ir para a tela buffer, etc. As funcionalidades ficarão omitidas no menu, mas continuarão funcionando tal como na versão anterior.

O menu da tela home ficará assim:

(V): Ver LWF no terminal  (E): abrir LWF externo     (M): ver LWF no Micro
(</>) voltar / avançar    (1/2/3) LWF / Log / LSR    (4/5/6) Buffer/Pilha/Hist.
(X): eXtrair links LWF    (F): aFiliados ao LWF      (L): histórico de LWFs    
(LSR): última pesquisa    (R): Refinar pesquisa      (C): Coleta dados LWF           
(D): zettel ranDômico.    (N): Novo zettel           (+): mais comandos

Apesar de eu haver reescrito as descrições as letras acionadoras das funções continuam as mesmas e as funções não devem ser modificadas a menos que eu tenha pedido expressamente
```


#projeto-ZKM #mac #proj_zetteltex [[projeto-ZKM-OZ-em-python-index\|projeto-ZKM-OZ-em-python-index]]