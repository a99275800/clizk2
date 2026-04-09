---
{"dg-publish":true,"permalink":"/projeto-zkm-outra-lista-de-demandas/","dg-note-properties":{}}
---


## de volta à 2.18 e tentando de novo

INSTRUÇÕES RECORRENTES / PERMANENTES: use o arquivo enviado como base de trabalho, não é para reescrever o script todo; conserte APENAS O QUE PEDIREI NAS INTRUÇÕES NOVAS ABAIXO; não mude nada além do que eu pedi; não simplifique, reescreva, limpe nem "melhore" o código, não tente encurtar as instruções nem tornar o código mais elegante ou conciso sem eu pedir; não mexa em nada além do que eu pedi e não mude nada que não seja estritamente necessário para cumprir o que eu pedi; não tente melhorar o código sem eu pedir; se tiver de mexer em algo que seja fora da função que eu pedi, pare e me informe antes o que pretende fazer e me peça confirmação antes de prosseguir; faça comentários verbosos nas partes que criar ou mudar tornando o script explicativo para um aprendiz de Python; em cada linha ou seção do código que você alterar coloque um comentário "alterado (ou incluído) na versão x.xx". Não modifique a interface, estética, identidade visual dos menus e prompts exceto no que for estritamente necessário para atender às instruções adiante. Entregue o resultado final dividido em 3 partes. 

INSTRUÇÕES NOVAS: 

1. Os links externos (imagens, links de internet, pdfs, arquivos csv ou outros quaisquer que não sejam .md) que forem chamados a partir da lista de resultados da função extrair links não devem ser considerados LWF nem lançados na lista de LWFs

2. No submenu gestão de tasks, fazer estas melhorias / mudanças:

2.1) as pesquisas todas deverão sempre Ignorar files da subpasta templates

2.2) as demais pesquisas (que não sejam as novas criadas adiante) ignorarão tasks que constarem de files contendo as tag #contas #consertar e / ou #proj_zetteltex

2.2.1) Mas a opção "(1) : Listar TODAS as Tasks pendentes (Ordenadas)" deve incluir as tags #contas #consertar e / ou #proj_zetteltex e as tasks que estiverem em files que contêm essas tags, e ignorar apenas a pasta Templates;

2.3) adicionar uma pesquisa específica para "tasks internas", que buscará apenas as tasks que estiverem em files contendo as tags #consertar e / ou #proj_zetteltex; os resultados serão apresentados conforme já é feito para as pesquisas principais (itens 1 e 2 do submenu)

2.4) adicionar uma pesquisa específica para "tasks financeiras", que buscará apenas as tasks que estiverem em files contendo as tags #contas e/ ou #finanças; os resultados serão apresentados conforme já é feito para as pesquisas principais (itens 1 e 2 do submenu) mas as tasks serão ordenadas por data de vencimento; as que não tiverem vencimento agendado irão para o fim da lista de resultados; 

2.5) as funções de pesquisar por tags e de listar tags válidas considerarão como válidas as tags #contas #consertar e #proj_zetteltex

2.6) Criar uma função para abrir no editor externo associado todos os arquivos que contêm as Tasks constantes da lista de resultados da última pesquisa de tasks

2.7) excetuada as pesquisas por tasks internas e por tags válidas, as demais pesquisas ignorarão os arquivos "RQR rol index grandes temas ou questoes recorrentes fichas principais.md", "zzzz ultraindex megaindex uberindex de tags rqrs e indexes.md" e os que estiverem na pasta templates

3) Na gestão do Buffer, o histórico / backup de segurança parece estar sendo zerado a cada sessão, ou a cada vez que mando zerar o buffer. Não é assim que devia funcionar. Quando o user manda zerar o buffer, o conteúdo que ali estava deve ser colado no arquivo de histórico / backup e permanecer lá por 60 dias. É para ser um backup cumulativo, que acumula todos os conteúdos que passaram pelo arquivo-buffer nos últimos 60 dias. Não é para ser volátil.

4 - No menu / prompt principal (tela inicial) a opção de extrair links extrai os links, mas estão ocorrendo erros:

4.1 - os wikilinks com aliases como por exemplo [[260305_J_5-de-marco-de-2026\|PREV]] estão sendo captados erradamente, foi desfeita a melhoria que funcionava anteriormente  e que reconhecia "|PREV" no exemplo acima como sendo um alias expurgando-o do resultado, que deveria, no exemplo, ser [[260305_J_5-de-marco-de-2026\|260305_J_5-de-marco-de-2026]]

4.2 - mesmo extraindo corretamente os nomes dos links de imagem como "exemplo.webp" quando teclo o número desse link e dou enter o link não é aberto no app registrado, e o script sai do submenu sem dar qualquer mensagem e abre o submenu de file-ops; pior, por alguma razão esse erro muda o LWF para algum outro arquivo aleatório e quando volto para a tela inicial não está mais como LWF aquele cujo link tinha sido extraído e eu estava tentando acessar

4.3 - embora seja um link válido e funcione, [Migalhas](https://www.migalhas.com.br/quentes/450875/juiza-que-reclamou-que-magistrado-nao-tem-cafe-agua-e-carro-vira-meme) não está sendo reconhecido pela função de extrair links

4.4 - pior, tentando executar essa função o script travou e quando reiniciei, embora estivesse executando o mesmo arquivo zk.py que antes funcionava, ele apareceu diferente, com o prompt da tela inicial encurtado e incompleto sem mostrar as estatísticas e o nome do LWF; depois que fiz uma pesquisa por string carregando um novo LWF, o defeito se auto consertou e a tela inicial voltou a aparecer completa

Depois de travar algumas vezes, o script simplesmente parou de rodar, o comando zk congela o terminal



## permanente
INSTRUÇÕES RECORRENTES / PERMANENTES: use o arquivo enviado como base de trabalho, não é para reescrever o script todo; conserte APENAS O QUE PEDIREI NAS INTRUÇÕES NOVAS ABAIXO; não mude nada além do que eu pedi; não simplifique, reescreva, limpe nem "melhore" o código, não tente encurtar as instruções nem tornar o código mais elegante ou conciso sem eu pedir; não mexa em nada além do que eu pedi e não mude nada que não seja estritamente necessário para cumprir o que eu pedi; não tente melhorar o código sem eu pedir; se tiver de mexer em algo que seja fora da função que eu pedi, pare e me informe antes o que pretende fazer e me peça confirmação antes de prosseguir; faça comentários verbosos nas partes que criar ou mudar tornando o script explicativo para um aprendiz de Python; em cada linha ou seção do código que você alterar coloque um comentário "alterado (ou incluído) na versão x.xx".
INSTRUÇÕES NOVAS:
A pesquisa por nome continua com o mesmo erro de antes. Fiz o teste várias vezes. Se entrou "zk n termo" no prompt do sistema, ele acha, por exemplo, 6 files com "termo" no nome; se digito "n termo" no prompt principal do "app" Zettelakasten Manager (isto é, depois de digitar "zk" Enter e acessar o prompt principal do script) o mesmo termo dá resultado vazio. Podíamos tentar um novo approach. Feita a pesquisa por string no conteúdo e nos nomes sempre que o user digitar uma string de 4 ou mais caracteres no prompt principal, é dada uma lista numerada de resultados seguida do prompt:

Digite Nº, (R)efine, (K) copy-all, ta(G)-mngr, (s)air ou (Q)uit:

Acrescente nesse prompt uma opção (N)omes, e se o user teclar N refaz a pesquisa procurando a string apenas nos nomes de files. Mais simples, não?

## novo 1

INSTRUÇÕES RECORRENTES / PERMANENTES: use o arquivo enviado como base de trabalho, não é para reescrever o script todo; conserte APENAS O QUE PEDIREI NAS INTRUÇÕES NOVAS ABAIXO; não mude nada além do que eu pedi; não simplifique, reescreva, limpe nem "melhore" o código, não tente encurtar as instruções nem tornar o código mais elegante ou conciso sem eu pedir; não mexa em nada além do que eu pedi e não mude nada que não seja estritamente necessário para cumprir o que eu pedi; não tente melhorar o código sem eu pedir; se tiver de mexer em algo que seja fora da função que eu pedi, pare e me informe antes o que pretende fazer e me peça confirmação antes de prosseguir; faça comentários verbosos nas partes que criar ou mudar tornando o script explicativo para um aprendiz de Python; em cada linha ou seção do código que você alterar coloque um comentário "alterado (ou incluído) na versão x.xx". Não modifique a interface, estética, identidade visual dos menus e prompts exceto no que for estritamente necessário para atender às instruções adiante.

INSTRUÇÕES NOVAS:

1 - No submenu gestão de tasks, fazer estas melhorias / mudanças:

1.1 -  a opção "(1) : Listar TODAS as Tasks pendentes (Ordenadas)" deve incluir as tags #contas #consertar e / ou #proj_zetteltex e as tasks que estiverem em files que contêm essas tags

1.2. a opção "(v) : Ver conteúdo atual da lista de tags gravadas" não está funcionando, volta para o mesmo prompt sem dar qualquer mensagem nem mostar o conteúdo (ainda que eu tenha acabado de gravar 3 tags)

1.3 - embora algumas pesquisas devam ignorar certas tags, conforme instruído, a opção "(8) : Listar Tags válidas em tarefas" deve incluir como tags válidas #contas #consertar e #proj_zetteltex e todas as outras tags que apareçam vinculadas a tasks, excetuando aqueles arquivos que mandei excluir, "RQR rol index grandes temas ou questoes recorrentes fichas principais.md", "zzzz ultraindex megaindex uberindex de tags rqrs e indexes.md" e os que estiverem na pasta templates

1.4. - Da mesma forma o prompt que surge da opção "(5) : Listar Tasks POR TAG específica" deve aceitar qualquer tag nas condições do item acima.

1.5 - A opção "(4) : Listar Tasks FINANCEIRAS (#contas/#finanças)" deve ordenar os resultados por ordem de data de vencimento, e depois das tags com data marcada colocar as que não tem vencimento agendado.

1.6 - A pesquisa por tags internas deve considerar (inclusive) os arquivos "RQR rol index grandes temas ou questoes recorrentes fichas principais.md", "zzzz ultraindex megaindex uberindex de tags rqrs e indexes.md", mas não os que estiverem na pasta templates.

2 - No menu / prompt principal (tela inicial) a opção de extrair links extrai os links, mas estão ocorrendo erros:

2.1 - os wikilinks com aliases como por exemplo [[260305_J_5-de-março-de-2026|PREV





## errado 1

~~Tudo errado. Você me entregou um file de 742 linhas para substituir um de 934 linhas. Não pode estar certo. Fazer de novo:~~

~~INSTRUÇÕES NOVAS:~~

~~adicionei manualmente o comando de importação da biblioteca readline, porque a versão que você me apresentou como sendo a 2.19 consolidada e completa tinha 200 linhas a menos que a versão 2.18, ou seja, estava estragada.~~

1) ~~Na versão que subi aqui, que é a consertada manualmente por mim, a readline funciona corretamente, mas falta anotar no changelog a alteração 2.19~~ 

2) ~~No submenu gestão de tasks, fazer estas melhorias / mudanças:~~

~~2.1) as pesquisas todas deverão sempre Ignorar files da subpasta templates~~

~~2.2) as demais pesquisas (que não sejam as novas criadas adiante) ignorarão tasks que constarem de files contendo as tag #contas #consertar e / ou #proj_zetteltex~~

~~2.3) adicionar uma pesquisa específica para "tasks internas", que buscará apenas as tasks que estiverem em files contendo as tags #consertar e / ou #proj_zetteltex; os resultados serão apresentados conforme já é feito para as pesquisas principais (itens 1 e 2 do submenu)~~

~~2.4) adicionar uma pesquisa específica para "tasks financeiras", que buscará apenas as tasks que estiverem em files contendo as tags #contas e/ ou #finanças; os resultados serão apresentados conforme já é feito para as pesquisas principais (itens 1 e 2 do submenu)~~

~~2.5) Criar uma função para abrir no editor externo associado todos os arquivos que contêm as Tasks constantes da lista de resultados da última pesquisa de tasks~~

3) ~~Na gestão do Buffer, o histórico / backup de segurança parece estar sendo zerado a cada sessão, ou a cada vez que mando zerar o buffer. Não é assim que devia funcionar. Quando o user manda zerar o buffer, o conteúdo que ali estava deve ser colado no arquivo de histórico / backup e permanecer lá por 60 dias. É para ser um backup cumulativo, que acumula todos os conteúdos que passaram pelo arquivo-buffer nos últimos 60 dias. Não é para ser volátil.~~ 
## errado 2

~~não pode estar certo, a versão 2.20 que você entregou tem 737 linhas, ainda menos que as 742 do erro anterior, a versão de trabalho que te enviei tinha 934 linhas e pedi para aumentar funções. As instruções foram desrespeitadas. Vou subir o arquivo original novamente e por favor recomece, seguindo desta vez as instruções~~

~~INSTRUÇÕES NOVAS:~~

~~adicionei manualmente o comando de importação da biblioteca readline, porque a versão que você me apresentou como sendo a 2.19 consolidada e completa tinha 200 linhas a menos que a versão 2.18, ou seja, estava estragada.~~

1) ~~Na versão que subi aqui, que é a consertada manualmente por mim, a readline funciona corretamente, mas falta anotar no changelog a alteração 2.19~~ 

2) ~~No submenu gestão de tasks, fazer estas melhorias / mudanças:~~

~~2.1) as pesquisas todas deverão sempre Ignorar files da subpasta templates~~

~~2.2) as demais pesquisas (que não sejam as novas criadas adiante) ignorarão tasks que constarem de files contendo as tag #contas #consertar e / ou #proj_zetteltex~~

~~2.3) adicionar uma pesquisa específica para "tasks internas", que buscará apenas as tasks que estiverem em files contendo as tags #consertar e / ou #proj_zetteltex; os resultados serão apresentados conforme já é feito para as pesquisas principais (itens 1 e 2 do submenu)~~

~~2.4) adicionar uma pesquisa específica para "tasks financeiras", que buscará apenas as tasks que estiverem em files contendo as tags #contas e/ ou #finanças; os resultados serão apresentados conforme já é feito para as pesquisas principais (itens 1 e 2 do submenu)~~

~~2.5) Criar uma função para abrir no editor externo associado todos os arquivos que contêm as Tasks constantes da lista de resultados da última pesquisa de tasks~~

3) ~~Na gestão do Buffer, o histórico / backup de segurança parece estar sendo zerado a cada sessão, ou a cada vez que mando zerar o buffer. Não é assim que devia funcionar. Quando o user manda zerar o buffer, o conteúdo que ali estava deve ser colado no arquivo de histórico / backup e permanecer lá por 60 dias. É para ser um backup cumulativo, que acumula todos os conteúdos que passaram pelo arquivo-buffer nos últimos 60 dias. Não é para ser volátil.~~ 

## errado 3


~~INSTRUÇÕES NOVAS:~~ 

~~Parece que as novas funções estão corretas mas:~~

1) ~~todos os submenus e seus respectivos prompts, menos o novo, de gestão de tasks, foram completamente estragados pelas alterações indevidas que você fez na versão 2.20; devem todos (menos a tela principal e o submenu gestão de tasks) ser restaurados para a condição em que estavam na versão 2.18~~

2) ~~no submenu de gestão de tasks todas as pesquisas devem ignorar o file "RQR rol index grandes temas ou questoes recorrentes fichas principais.md" e o file "zzzz ultraindex megaindex uberindex de tags rqrs e indexes.md"~~

3) ~~tasks que constarem de files contendo as tags #consertar #proj_zetteltex não devem aparecer na pesquisa de tags financeiras~~ 


#projeto-ZKM #projetos #mac #proj_zetteltex [[projeto-ZKM-OZ-em-python-index\|projeto-ZKM-OZ-em-python-index]]
