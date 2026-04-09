---
{"dg-publish":true,"permalink":"/zk-help-old-version/","dg-note-properties":{}}
---

Este documento apresenta o mapeamento completo e técnico de todos os comandos operacionais do ecossistema **CLIZK (v8.1)**, extraídos diretamente da lógica de processamento de entrada (`input`) e das funções de roteamento dos scripts mestres.

---

## Content Index

- [1. Módulos de Interface (Telas de Menu)](##1.%20Módulos%20de%20Interface%20(Telas%20de%20Menu))
	- [1.1. Tela Home (`zk.py`)](##1.1.%20Tela%20Home%20(`zk.py`))
	- [1.2. Módulo FileOps (`zk_fileops.py`)](##1.2.%20Módulo%20FileOps%20(`zk_fileops.py`))
	- [1.3. Módulo System (`zk_system.py`)](##1.3.%20Módulo%20System%20(`zk_system.py`))
	- [1.4. Módulo Pile (Pilha) (`zk_pile.py`)](##1.4.%20Módulo%20Pile%20(Pilha)%20(`zk_pile.py`))
	- [1.5. Módulo Tags (`zk_tags.py`)](##1.5.%20Módulo%20Tags%20(`zk_tags.py`))
	- [1.6. Módulo Tasks (`zk_tasks.py`)](##1.6.%20Módulo%20Tasks%20(`zk_tasks.py`))
	- [1.7. Módulo Buffer (`zk_buffer.py`)](##1.7.%20Módulo%20Buffer%20(`zk_buffer.py`))
	- [1.8. Módulo Extra / Goodies (`zk_goodies.py`)](##1.8.%20Módulo%20Extra%20/%20Goodies%20(`zk_goodies.py`))
	- [2. Módulos Operacionais (Sem Tela / Visualizadores)](##2.%20Módulos%20Operacionais%20(Sem%20Tela%20/%20Visualizadores))
	- [2.1. Dossier (`zk_dossier.sh`)](##2.1.%20Dossier%20(`zk_dossier.sh`))
	- [2.2. Ultra Viewer (`zk_ultra.py`)](##2.2.%20Ultra%20Viewer%20(`zk_ultra.py`))
	- [2.3. Screensaver Ultra Zen (`zk_ssvhs.py`)](##2.3.%20Screensaver%20Ultra%20Zen%20(`zk_ssvhs.py`))
	- [3. Tabela de Modos de Pesquisa](##3.%20Tabela%20de%20Modos%20de%20Pesquisa)
- [4. módulos independentes / autônomos](#4.%20módulos%20independentes%20/%20autônomos)
	- [4.1. Murmurs (`zk_murmurs.py`)](##4.1.%20Murmurs%20(`zk_murmurs.py`))
	- [4.2. Slides / Slideshow (`zk_slides.py`)](##4.2.%20Slides%20/%20Slideshow%20(`zk_slides.py`))
	- [4.3. Cinema (`zk_cinema.py`)](##4.3.%20Cinema%20(`zk_cinema.py`))
	- [4.4. Ultra Zen VHS (`zk_ssvhs.py`)](##4.4.%20Ultra%20Zen%20VHS%20(`zk_ssvhs.py`))
	- [4.5. Pixel Art Renderer (`zk_pix8.py`)](##4.5.%20Pixel%20Art%20Renderer%20(`zk_pix8.py`))
	- [4.6. Hacker Mode / Hacker Eyes (`zk_hacker.py`)](##4.6.%20Hacker%20Mode%20/%20Hacker%20Eyes%20(`zk_hacker.py`))

---

## 1. Módulos de Interface (Telas de Menu)

## 1.1. Tela Home (`zk.py`)

O centro nervoso do sistema, focado no LWF (_Last Watched File_) e navegação.

|**Comando**|**Descrição**|
|---|---|
|**U**|**Ver LWF Ultra**: Invoca o módulo `zk_ultra.py` para visualização rica do arquivo atual.|
|**E**|**Abrir LWF Externo**: Abre o arquivo físico no editor padrão do macOS (`open`).|
|**M**|**Ver LWF no Micro**: Abre o arquivo no editor de terminal `micro` (config. de fábrica).|
|**V**|**Ver no Less**: Exibe o conteúdo formatado em 80 colunas via comando `less`.|
|**C**|**Submenu Captura**: Abre interface para coleta de metadados do LWF para o clipboard.|
||_--- Submenus de Captura ---_|
||**F**: Copia o Caminho Absoluto (_Fullpath_) do arquivo.|
||**N**: Copia o Nome do Arquivo (com extensão).|
||**B**: Copia o _Basename_ (nome sem extensão).|
||**O**: Copia o Conteúdo Integral do texto.|
||**L**: Copia o [[Wikilink\|Wikilink]] formatado com o nome do arquivo.|
||**X**: **Captura Contexto Complexo**: Copia tags do LWF e links para zettels com `#indexes`.|
||**P**: Adiciona o LWF atual à Pilha oficial.|
||**Fi**: Localiza e revela o arquivo no Finder do macOS.|
|**X**|**Extrair Links LWF**: Varre o arquivo em busca de links e URLs para navegação direta.|
|**F**|**Afiliados ao LWF**: Busca todos os outros zettels que possuem links apontando para o LWF.|
|**L**|**Histórico LWFs**: Exibe lista dos últimos arquivos acessados para reabertura.|
|**LSR**|**Última Pesquisa**: Reexibe o resultado da última busca realizada.|
|**R**|**Refinar Pesquisa**: Aplica um novo filtro sobre os resultados atuais da LSR.|
|**D**|**Randômico**: Sorteia e define um novo Zettel válido como LWF.|
|**N**|**Novo Zettel**: Inicia a criação de uma nova nota (lógica de busca por nome inexistente).|
|**TSS**|**Twin Souls**: Busca zettels com tags similares ao LWF (mote de afinidade).|
|**W**|**Toggle Original**: Alterna o visor entre modo Monobloco e preservação de quebras originais.|
|**=**|**Modo Alto / Avançar**: Ativa visor de 34 linhas ou avança para a próxima página.|
|**-**|**Voltar Página**: Retorna ao bloco anterior no modo de altura dinâmica.|
|*****|**Reset Visor**: Desativa o Modo Alto e retorna ao visor padrão de 13 linhas.|
|**< / >**|**Navegação Histórica**: Alterna o LWF entre os itens do cache de histórico recente.|
|**1 a 6**|**Troca de Visor**: Alterna o conteúdo entre LWF, Log, LSR, Buffer, Pilha e Histórico.|
|**DOSS**|**Módulo Dossier**: Invoca o shell script `zk_dossier.sh` para visualização gráfica.|
|**Q**|**Quit**: Encerra o processo CLIZK e silencia áudios ativos.|

## 1.2. Módulo FileOps (`zk_fileops.py`)

Gestão física e filtros de organização do acervo.

|**Comando**|**Descrição**|
|---|---|
|**1**|**Abrir todos LSR**: Envia todos os arquivos da última pesquisa para o editor externo.|
|**2**|**Copiar LWF p/ Clip**: Copia o conteúdo textual puro do LWF para a área de transferência.|
|**3**|**Abrir todos da Pilha**: Envia todos os itens empilhados para abertura no editor externo.|
|**R**|**Buscar Referentes**: Localiza wikilinks apontando para o nome do LWF atual.|
|**5**|**LSR como Links**: Copia a lista da última pesquisa formatada como [[wikilinks\|wikilinks]].|
|**M**|**Modificados Recentes**: Lista os 10 arquivos .md alterados mais recentemente.|
|**SZ**|**Maiores Zettels**: Ranking dos 10 maiores arquivos de texto por tamanho em bytes.|
|**SA**|**Maiores Assets**: Ranking dos 10 maiores arquivos não-texto (imagens/pdfs).|
|**ST**|**Zettels sem Tags**: Filtra notas que não possuem nenhuma etiqueta (#).|
|**AP**|**Filtro #apagar**: Lista zettels marcados para deleção com seu contexto.|
|**IN / UR**|**Inbox / Urgente**: Atalhos rápidos para as tags `#inbox` e `#urgente`.|
|**DEL**|**Deletar LWF**: Move o arquivo atual para a Lixeira do macOS via Finder (seguro).|
|**H**|**Log de Deletados**: Abre o histórico de arquivos removidos via sistema.|

## 1.3. Módulo System (`zk_system.py`)

Manutenção, integridade e alternância de versões.

|**Comando**|**Descrição**|
|---|---|
|**1**|**Backup Integral**: Gera arquivo .zip contendo .md, .py, .sh e a pasta assets.|
|**2**|**Backup Zettels**: Gera arquivo .zip contendo apenas as notas markdown.|
|**3**|**Backup Scripts**: Gera .zip com arquivos `.py`, `.sh` e documentos de governança.|
|**4**|**Backup OneDrive**: Espelha o backup de zettels na pasta TZ-2 do CloudStorage.|
|**G**|**Alternar p/ Gold**: Encerra o sistema atual e carrega a versão estável (ZK-stable).|
|**E**|**Editar Scripts**: Realiza backup de segurança e abre todos os scripts `.py/.sh` no editor.|
|**H**|**Changelog Oficial**: Abre o arquivo `zk_changelog.md` diretamente no `less`.|
|**F**|**Abrir Backups**: Abre a pasta de destino dos arquivos zip no Finder.|
|**T**|**Toggle Goodies**: Ativa/Desativa efeitos sonoros e animações de interface.|
|**R**|**Toggle Retro**: Ativa/Desativa o visualizador de anexos Lo-Fi.|

## 1.4. Módulo Pile (Pilha) (`zk_pile.py`)

Operações em lote e processamento sequencial.

|**Comando**|**Descrição**|
|---|---|
|**P**|**Menu Adicionar**: Abre submenu para incluir LWF, LSR ou Histórico na pilha.|
|**C**|**Operações Clipboard**: Submenu para copiar Basenames, Wikilinks ou Paths da pilha.|
|**A**|**Abrir Pilha**: Submenu para abrir a pilha como texto único, lista ou múltiplos zettels.|
|**Z**|**Zerar Pilha**: Limpa o cache de arquivos empilhados.|
|**R**|**Remover Item**: Exclui um arquivo específico da pilha através do seu índice numérico.|
|**DEL**|**Apagar Empilhados**: Deleção em massa (via Lixeira) de todos os itens na pilha.|
|**G**|**Taguear Lote**: Adiciona uma tag específica ao final de todos os arquivos da pilha.|
|**U**|**Untaguear Lote**: Identifica tags em comum e as remove de todos os arquivos da pilha.|
|**T**|**Comando Secreto**: Cria arquivos de teste interlinkados ("meleca1, 2, 3").|

## 1.5. Módulo Tags (`zk_tags.py`)

Navegação taxonômica e extração de metadados.

|**Comando**|**Descrição**|
|---|---|
|**T**|**Total Únicas**: Exibe a contagem de tags distintas em todo o acervo.|
|**M**|**20 Mais Usadas**: Ranking de frequência das etiquetas mais populares.|
|**L**|**20 Menos Usadas**: Lista de tags raras ou órfãs.|
|**P**|**Tags por Prefixo**: Filtra tags que iniciam com uma determinada string.|
|**C**|**Capturar Tags LWF**: Copia todas as tags do LWF atual como uma linha formatada.|
|**G**|**Gerir Gravadas**: Abre interface para manipular tags salvas em cache temporário.|
|**String**|**Busca de Tag**: Digitar 3+ letras filtra tags que contenham a sequência digitada.|

## 1.6. Módulo Tasks (`zk_tasks.py`)

Interface de gestão de tarefas e pendências.

|**Comando**|**Descrição**|
|---|---|
|**T**|**Todas Pendentes**: Lista todas as checkboxes `[ ]` encontradas no cofre.|
|**A**|**Tasks Atuais**: Filtra tarefas pendentes com vencimento próximo (5 dias) ou sem data.|
|**G**|**Por Tag**: Filtra tarefas que contenham uma tag específica.|
|**F**|**Financeiras**: Atalho para listar tasks com `#contas` ou `#finanças`.|
|**I**|**Internas**: Atalho para listar tasks com `#consertar` ou `#proj_zetteltex`.|
|**D**|**Distantes**: Lista tarefas com vencimento superior a 60 dias.|
|**C**|**Concluídas**: Lista histórico de itens marcados com `[x]`.|
|**V**|**Tags Válidas**: Mostra as etiquetas utilizadas exclusivamente em blocos de tarefas.|
|**E**|**Abrir Editor**: Abre todos os arquivos que contenham tarefas pendentes.|

## 1.7. Módulo Buffer (`zk_buffer.py`)

Bloco de notas volátil e injeção de dados.

|**Comando**|**Descrição**|
|---|---|
|**V**|**Ver Buffer**: Exibe o conteúdo completo do arquivo `zk_buffer.md` no `less`.|
|**A**|**Add Clipboard**: Adiciona o conteúdo atual da área de transferência ao fim do buffer.|
|**E / M**|**Editor**: Abre o arquivo de buffer no editor externo ou no `micro`.|
|**S / C**|**Copia Buffer**: Copia o texto para o clipboard (Simples ou Compacto) e limpa o arquivo.|
|**+**|**LWF p/ Buffer**: Injeta o conteúdo integral do LWF dentro do buffer.|
|**!**|**Injetar no LWF**: Move o conteúdo do buffer para o final do LWF ativo.|
|**Z**|**Zerar**: Limpa o buffer e registra o conteúdo apagado no log de segurança.|
|**H**|**Ver Histórico**: Abre o log histórico de textos que passaram pelo buffer.|
|**T**|**Tags do LWF**: Extrai tags do LWF e as anexa ao buffer.|
|**D**|**Data/Hora**: Insere carimbo de tempo atual no arquivo.|
|**L / K**|**Listas**: Injeta links da LSR ou da Pilha como wikilinks no buffer.|

## 1.8. Módulo Extra / Goodies (`zk_goodies.py`)

Funções estéticas e de imersão.

|**Comando**|**Descrição**|
|---|---|
|**S**|**Slideshow Zen**: Inicia exibição automática de Zettels com trilha sonora.|
|**U**|**Ultra Zen VHS**: Invoca o protetor de tela `zk_ssvhs.py`.|
|**G**|**Screensaver Visor**: Animação estilo Matrix "Cyberpunk" no visor central.|
|**T**|**Testar Glitch**: Dispara efeito visual de interferência e som de erro.|
|**V**|**Modo VHS**: Ativa/Desativa o tremor lateral e corrupção de caracteres.|
|**F**|**Scanline**: Ativa/Desativa o efeito de linhas de varredura de TV antiga.|
|**L**|**Tela Loading**: Repete a animação de inicialização do sistema.|

---

## 2. Módulos Operacionais (Sem Tela / Visualizadores)

## 2.1. Dossier (`zk_dossier.sh`)

Interface gráfica de visualização de documentos. Usa fundos que têm de estar na pasta assets e começarem com `_dossier_background` seguido de um número. Fiz os fundos no Canva. Para usar esse módulo, estando na tela Home e com o zettel previamente definido como LWF, digite no prompt `doss` enter.

|**Comando**|**Descrição**|
|---|---|
|**N / P**|**Navegação**: Avança ou retorna uma página do documento renderizado.|
|**V**|**Ciclo de Visor**: Alterna filtros (Xerox, Negative, Blueprint, Mimeo, Halftone).|
|**C**|**Copy**: Copia a imagem processada da página atual para o clipboard.|
|**E**|**Edit**: Abre o arquivo fonte (.md) e encerra o Dossier.|
|**D**|**Debug**: Abre a pasta temporária onde os _frames_ PNG foram gerados.|
|**Q**|**Quit**: Encerra o visualizador e retorna ao CLIZK.|

## 2.2. Ultra Viewer (`zk_ultra.py`)

Navegador de hipertexto com motor de busca integrado.

|**Comando**|**Descrição**|
|---|---|
|**A / V**|**Avançar/Voltar**: Rola o conteúdo do zettel (23 ou 29 linhas por vez).|
|**< / >**|**Navegação**: Volta ou avança no histórico de arquivos visualizados no Ultra.|
|**M**|**Menu**: Alterna a visibilidade do painel de 15 opções técnicas.|
|**U**|**Aumentar Tela**: Expande a área de visão em +7 linhas.|
|**Z**|**Histórico**: Exibe lista numerada dos últimos zettels vistos para salto rápido.|
|**Números**|**Salto de Link**: Digitar o índice `[n]` abre o wikilink ou URL correspondente.|
|**LSR**|**Última Busca**: Recupera o resultado da última pesquisa AND/OR realizada.|
|**S**|**Sair**: Salva o arquivo atual como o novo LWF e retorna à Home.|

## 2.3. Screensaver Ultra Zen (`zk_ssvhs.py`)

Protetor de tela contemplativo com estética VHS. Os recursos visuais interessantes só funcionam se os goodies estiverem ON (escolhe na tela System)

|**Comando**|**Descrição**|
|---|---|
|**Espaço**|**Pausa**: Congela a sucessão de páginas e a animação de flicker.|
|**D**|**Ruído Toggle**: Ativa/Desativa a sujeira visual de fundo (pixels aleatórios).|
|**V**|**Voltar**: Retorna ao Zettel exibido anteriormente na sessão.|
|**A**|**Abrir**: Define o Zettel atual como LWF e retorna ao Home (registra trabalho).|
|**S**|**Sair**: Finaliza a sessão de screensaver e silencia o áudio.|

---

## 3. Tabela de Modos de Pesquisa

O CLIZK possui motores de busca distintos dependendo do contexto de entrada.

| **Contexto** | **Comando/Lógica**   | **Descrição da Operação**                                                              |
| ------------ | -------------------- | -------------------------------------------------------------------------------------- |
| **Home**     | `Entrada (3+ chars)` | Pesquisa **Conteúdo** por padrão (ignora case).                                        |
| **Home**     | `n [termo]`          | Pesquisa **Nome de Arquivo** exclusivamente.                                           |
| **Home**     | `a [t1] [t2]`        | Pesquisa **AND**: Arquivos que contenham ambos os termos.                              |
| **Home**     | `o [t1] [t2]`        | Pesquisa **OR**: Arquivos que contenham ao menos um dos termos.                        |
| **Home**     | `r`                  | **Refinar**: Aplica nova busca sobre a lista de resultados anterior.                   |
| **Home**     | `c`                  | **Contexto**: Exibe trechos do arquivo onde os termos foram achados.                   |
| **Home**     | `x`                  | **Próximas**: Busca arquivos onde dois termos estão a até 120 caracteres de distância. |
| **Tags**     | `Entrada (3+ chars)` | Filtra etiquetas que contenham a **String** pesquisada.                                |
| **Tags**     | `p [prefixo]`        | Filtra etiquetas que iniciam com a string digitada.                                    |
| **Ultra**    | `and [t1] [t2...]`   | Motor `zk_ultrasearch`: Busca arquivos com **todos** os termos.                        |
| **Ultra**    | `or [t1] [t2...]`    | Motor `zk_ultrasearch`: Busca arquivos com **qualquer** dos termos.                    |
| **Ultra**    | `lsr`                | Recupera a lista persistente da última pesquisa efetuada no Ultra.                     |

# 4. módulos independentes / autônomos

Rodam digitando, no iTerm (a maioria só roda no iTerm), desde que com o path definido para a pasta raiz do projeto:

```
python3 ./nomedomodulo.py
```

## 4.1. Murmurs (`zk_murmurs.py`)

Visor de vigilância ascendente (_Base-In_) que extrai frases aleatórias do acervo.

|**Comando**|**Descrição**|
|---|---|
|**P**|**Pausar**: Congela o fluxo de subida das frases e o preenchimento da barra de progresso.|
|**S**|**Sair**: Encerra o script e limpa a tela do terminal.|

## 4.2. Slides / Slideshow (`zk_slides.py`)

Galeria imersiva via protocolo `imgcat` (iTerm2) com suporte a tags e filtros em tempo real. Escolhe as coleções por tags. As imagens estão na pasta assets e todas começam com `decor-nomedotema` e um número depois. E cada tema está num zettel, por exemplo [[decor-machinery\|decor-machinery]], e cada zettel com essa função tem uma tag, por exemplo `#decor03` e é essa string que se digita para trocar de coleção durante a execuçâo do script.

|**Comando**|**Descrição**|
|---|---|
|**Espaço**|**Menu**: Sai do modo imersivo e abre o menu de opções técnicas.|
|**Enter**|**Avançar**: Pula manualmente para a próxima imagem da tag atual.|
||_--- Opções no Menu Interno ---_|
|**N / P**|**Próximo / Anterior**: Navega manualmente pela lista de imagens carregadas.|
|**X**|**Xerox Toggle**: Ativa/Desativa o filtro de alto contraste P&B.|
|**D**|**Deteriorar**: Ativa/Desativa a injeção de ruído e manchas de "toner" na imagem.|
|**L**|**Scanlines**: Ativa/Desativa as linhas de varredura (cor varia conforme a versão do script).|
|**O**|**Abrir Externo**: Abre o arquivo original da imagem no visualizador do macOS.|
|**#**|**Mudar Tag**: Permite digitar uma nova hashtag para buscar outro conjunto de imagens.|
|**S**|**Sair**: Finaliza o módulo e restaura a tela do terminal.|

## 4.3. Cinema (`zk_cinema.py`)

Projeção estável de clipes curtos e GIFs com temporizador de 15 segundos. Para isso aqui funcionar, importante todos os vídeos terem o mesmo formato (quadrado, de preferência. Os vídeos estão na pasta assets e têm todos nomes começando com `_decor0x`; esse x é um número; é com essa string que se escolhe qual coleção de vídeos rodar).

|**Comando**|**Descrição**|
|---|---|
|**M**|**Menu**: Abre a interface de configuração de filtros e busca de clipes.|
|**N**|**Avançar**: Pula o clipe atual e carrega o próximo da playlist.|
|**S**|**Sair**: Encerra a sessão de cinema imediatamente.|
||_--- Opções no Modo Menu ---_|
|**Enter**|**Voltar**: Retoma a projeção com as configurações atuais.|
|**String**|**Filtro**: Digitar 3+ letras redefine o critério de busca (ex: `_decor01`).|

## 4.4. Ultra Zen VHS (`zk_ssvhs.py`)

Protetor de tela contemplativo com renderização instável e foco em Zettels aleatórios.

|**Comando**|**Descrição**|
|---|---|
|**Espaço**|**Pausa**: Congela o texto na tela e interrompe o ciclo de sincronismo (Sync).|
|**D**|**Ruído Toggle**: Liga/Desliga a camada de grão visual (quase preto/cinza profundo).|
|**V**|**Voltar**: Reexibe o Zettel anterior visualizado na mesma sessão.|
|**A**|**Abrir / Registrar**: Define o arquivo atual como LWF e fecha o screensaver.|
|**S**|**Sair**: Encerra o módulo e interrompe a trilha sonora.|

## 4.5. Pixel Art Renderer (`zk_pix8.py`)

Conversor de imagens para arte ANSI 8-bit usando técnica de resolução dupla (meio-bloco).

|**Comando**|**Descrição**|
|---|---|
|**Automático**|**Renderização**: Este módulo não possui menu interativo; ao receber um _path_, ele cospe a arte ANSI diretamente no buffer do terminal e encerra a execução.|

## 4.6. Hacker Mode / Hacker Eyes (`zk_hacker.py`)

Simulador de atividade de sistema "Hollywood style" com logs e animação de dutos (_Pipes_).

|**Comando**|**Descrição**|
|---|---|
|**Espaço**|**Reset**: Limpa o visor central (matriz de canos) e reinicia a animação.|
|**S**|**Sair**: Encerra a simulação e silencia os sons de efeitos.|
|**Automático**|**Lentidão**: O script opera com um delay fixo de **0.4s** por frame para garantir legibilidade técnica.|

## 4.7. Projector (`zk_projector.py`)

Simulador de projetor idealizado para mostrar zettels do tipo journal, mostrando um parágrafo de cada vez e mais as imagens que estiverem implicadas. Só mostra imagens locais, não abre links do GPHO. Tem de ser chamado fornecendo o nome / caminho do zettel. Aceita navagação de avançar e recuar entre journals.

## 4.8. Módulo: zk_oneliner.py (Eye-Candy)

O **Oneliner** é um módulo de exibição estética e contemplativa projetado para extrair "pílulas de conhecimento" e fragmentos literários do seu acervo Zettelkasten. Ele opera como um terminal de dados de alta velocidade, processando frases aleatórias com um efeito visual de decodificação.
### Comandos (Não Documentados)

Embora a interface seja limpa (_Stealth Mode_), os seguintes comandos permanecem ativos:

- **Q**: Encerra o módulo e retorna ao terminal.
    
- **P**: Pausa a animação ou o tempo de fixação da frase.
    
- **C**: Copia a frase atual (já limpa) para o Clipboard do sistema.
    
- **E**: Abre o Zettel de origem da frase no editor externo configurado.


---
29/03/2026