---
{"dg-publish":true,"permalink":"/zk-help/","dg-note-properties":{}}
---

Este documento apresenta o mapeamento completo e técnico de todos os comandos operacionais do ecossistema **CLIZK (v8.1)**, extraídos diretamente da lógica de processamento de entrada (`input`) e das funções de roteamento dos scripts mestres.

---

## 1. Módulos de Interface (Telas de Menu)

### 1.1. Tela Home (`zk.py`)

O centro nervoso do sistema, focado no LWF (_Last Watched File_) e navegação.

- **U**: **Ver LWF Ultra**: Invoca o módulo `zk_ultra.py` para visualização rica.
    
- **E**: **Abrir LWF Externo**: Abre o arquivo físico no editor padrão do macOS (`open`).
    
- **M**: **Ver LWF no Micro**: Abre o arquivo no editor de terminal `micro`.
    
- **V**: **Ver no Less**: Exibe o conteúdo formatado em 80 colunas via `less`.
    
- **C**: **Submenu Captura**: Abre interface para coleta de metadados para o clipboard.
    
    - **F**: Copia o Caminho Absoluto (_Fullpath_).
        
    - **N**: Copia o Nome do Arquivo com extensão.
        
    - **B**: Copia o _Basename_ (sem extensão).
        
    - **O**: Copia o Conteúdo Integral do texto.
        
    - **L**: Copia o [[Wikilink\|Wikilink]] formatado.
        
    - **X**: **Captura Contexto Complexo**: Copia tags e links para zettels com `#indexes`.
        
    - **P**: Adiciona o LWF atual à Pilha oficial.
        
    - **Fi**: Localiza e revela o arquivo no Finder do macOS.
        
- **X**: **Extrair Links LWF**: Varre o arquivo em busca de links e URLs.
    
- **F**: **Afiliados ao LWF**: Busca zettels que apontam para o LWF atual.
    
- **L**: **Histórico LWFs**: Exibe lista dos últimos arquivos acessados.
    
- **LSR**: **Última Pesquisa**: Reexibe o resultado da última busca.
    
- **R**: **Refinar Pesquisa**: Aplica novo filtro sobre os resultados da LSR.
    
- **D**: **Randômico**: Sorteia e define um novo Zettel como LWF.
    
- **N**: **Novo Zettel**: Inicia a criação de uma nova nota.
    
- **TSS**: **Twin Souls**: Busca zettels com tags similares ao LWF.
    
- **W**: **Toggle Original**: Alterna entre modo Monobloco e quebras originais.
    
- **=**: **Modo Alto / Avançar**: Ativa visor de 34 linhas ou avança página.
    
- **-**: **Voltar Página**: Retorna ao bloco anterior no modo de altura dinâmica.
    
- *****: **Reset Visor**: Retorna ao visor padrão de 13 linhas.
    
- **< / >**: **Navegação Histórica**: Alterna o LWF entre itens do histórico recente.
    
- **1 a 6**: **Troca de Visor**: Alterna entre LWF, Log, LSR, Buffer, Pilha e Histórico.
    
- **DOSS**: **Módulo Dossier**: Invoca o script `zk_dossier.sh` para visualização gráfica.
    
- **Q**: **Quit**: Encerra o CLIZK e silencia áudios ativos.
    

### 1.2. Módulo FileOps (`zk_fileops.py`)

Gestão física e filtros de organização do acervo.

- **1**: **Abrir todos LSR**: Envia resultados da pesquisa para o editor externo.
    
- **2**: **Copiar LWF p/ Clip**: Copia o texto puro do LWF para o clipboard.
    
- **3**: **Abrir todos da Pilha**: Abre itens empilhados no editor externo.
    
- **R**: **Buscar Referentes**: Localiza wikilinks apontando para o LWF.
    
- **5**: **LSR como Links**: Copia a LSR formatada como [[wikilinks\|wikilinks]].
    
- **M**: **Modificados Recentes**: Lista os 10 arquivos .md alterados recentemente.
    
- **SZ**: **Maiores Zettels**: Ranking dos 10 maiores arquivos por bytes.
    
- **SA**: **Maiores Assets**: Ranking dos 10 maiores arquivos não-texto (imagens/PDFs).
    
- **ST**: **Zettels sem Tags**: Filtra notas sem nenhuma etiqueta (#).
    
- **AP**: **Filtro #apagar**: Lista zettels marcados para deleção.
    
- **IN / UR**: **Inbox / Urgente**: Atalhos para as tags `#inbox` e `#urgente`.
    
- **DEL**: **Deletar LWF**: Move o arquivo para a Lixeira do macOS via Finder.
    
- **H**: **Log de Deletados**: Abre o histórico de arquivos removidos.
    

### 1.3. Módulo System (`zk_system.py`)

Manutenção e integridade do sistema.

- **1**: **Backup Integral**: Zip de notas, scripts e assets.
    
- **2**: **Backup Zettels**: Zip apenas das notas markdown.
    
- **3**: **Backup Scripts**: Zip de arquivos `.py`, `.sh` e governança.
    
- **4**: **Backup OneDrive**: Espelha backup de zettels no CloudStorage.
    
- **G**: **Alternar p/ Gold**: Carrega a versão estável (ZK-stable).
    
- **E**: **Editar Scripts**: Backup de segurança e abertura de scripts no editor.
    
- **H**: **Changelog Oficial**: Abre `zk_changelog.md` no `less`.
    
- **F**: **Abrir Backups**: Abre a pasta de destino dos zips no Finder.
    
- **T**: **Toggle Goodies**: Ativa/Desativa efeitos sonoros e animações.
    
- **R**: **Toggle Retro**: Ativa/Desativa o visualizador de anexos Lo-Fi.
    

### 1.4. Módulo Pile (Pilha) (`zk_pile.py`)

Operações em lote e processamento sequencial.

- **P**: **Menu Adicionar**: Inclui LWF, LSR ou Histórico na pilha.
    
- **C**: **Operações Clipboard**: Copia Basenames, Wikilinks ou Paths da pilha.
    
- **A**: **Abrir Pilha**: Abre pilha como texto único, lista ou múltiplos arquivos.
    
- **Z**: **Zerar Pilha**: Limpa o cache de arquivos empilhados.
    
- **R**: **Remover Item**: Exclui arquivo específico da pilha pelo índice.
    
- **DEL**: **Apagar Empilhados**: Deleção em massa via Lixeira.
    
- **G**: **Taguear Lote**: Adiciona tag específica ao final de todos os arquivos da pilha.
    
- **U**: **Untaguear Lote**: Remove tags comuns de todos os arquivos da pilha.
    
- **T**: **Comando Secreto**: Cria arquivos de teste interlinkados.
    

### 1.5. Módulo Tags (`zk_tags.py`)

Navegação taxonômica.

- **T**: **Total Únicas**: Contagem de tags distintas no acervo.
    
- **M**: **20 Mais Usadas**: Ranking de popularidade das etiquetas.
    
- **L**: **20 Menos Usadas**: Lista de tags raras ou órfãs.
    
- **P**: **Tags por Prefixo**: Filtra tags que iniciam com string específica.
    
- **C**: **Capturar Tags LWF**: Copia tags do LWF como linha formatada.
    
- **G**: **Gerir Gravadas**: Manipula tags salvas em cache temporário.
    
- **String**: **Busca de Tag**: Filtra tags contendo a sequência digitada (3+ letras).
    

### 1.6. Módulo Tasks (`zk_tasks.py`)

Gestão de tarefas e pendências.

- **T**: **Todas Pendentes**: Lista todas as checkboxes `[ ]` do cofre.
    
- **A**: **Tasks Atuais**: Filtra pendências próximas (5 dias) ou sem data.
    
- **G**: **Por Tag**: Filtra tarefas com tag específica.
    
- **F**: **Financeiras**: Atalho para `#contas` ou `#finanças`.
    
- **I**: **Internas**: Atalho para `#consertar` ou `#proj_zetteltex`.
    
- **D**: **Distantes**: Tarefas com vencimento superior a 60 dias.
    
- **C**: **Concluídas**: Lista histórico de itens marcados com `[x]`.
    
- **V**: **Tags Válidas**: Mostra etiquetas exclusivas de blocos de tarefas.
    
- **E**: **Abrir Editor**: Abre todos os arquivos com tarefas pendentes.
    

### 1.7. Módulo Buffer (`zk_buffer.py`)

Bloco de notas volátil e injeção de dados.

- **V**: **Ver Buffer**: Exibe conteúdo de `zk_buffer.md` no `less`.
    
- **A**: **Add Clipboard**: Adiciona área de transferência ao fim do buffer.
    
- **E / M**: **Editor**: Abre buffer no editor externo ou `micro`.
    
- **S / C**: **Copia Buffer**: Copia texto para clipboard e limpa o arquivo.
    
- **+**: **LWF p/ Buffer**: Injeta conteúdo do LWF no buffer.
    
- **!**: **Injetar no LWF**: Move conteúdo do buffer para o fim do LWF.
    
- **Z**: **Zerar**: Limpa o buffer com registro no log de segurança.
    
- **H**: **Ver Histórico**: Abre log histórico de textos do buffer.
    
- **T**: **Tags do LWF**: Extrai tags do LWF para o buffer.
    
- **D**: **Data/Hora**: Insere carimbo de tempo atual.
    
- **L / K**: **Listas**: Injeta links da LSR ou Pilha no buffer.
    

### 1.8. Módulo Extra / Goodies (`zk_goodies.py`)

Funções estéticas e imersão.

- **S**: **Slideshow Zen**: Exibição automática de Zettels com trilha.
    
- **U**: **Ultra Zen VHS**: Invoca protetor de tela `zk_ssvhs.py`.
    
- **G**: **Screensaver Visor**: Animação "Cyberpunk" no visor central.
    
- **T**: **Testar Glitch**: Efeito visual de interferência e som de erro.
    
- **V**: **Modo VHS**: Toggle de tremor lateral e corrupção de caracteres.
    
- **F**: **Scanline**: Toggle de linhas de varredura de TV antiga.
    
- **L**: **Tela Loading**: Repete animação de inicialização.
    

---

## 2. Módulos Operacionais (Visualizadores)

### 2.1. Dossier (`zk_dossier.sh`)

Interface gráfica de visualização de documentos (comando `doss` na Home).

- **N / P**: **Navegação**: Avança ou retorna uma página.
    
- **V**: **Ciclo de Visor**: Alterna filtros (Xerox, Negative, Blueprint, Mimeo, Halftone).
    
- **C**: **Copy**: Copia imagem processada da página para o clipboard.
    
- **E**: **Edit**: Abre arquivo .md e encerra o Dossier.
    
- **D**: **Debug**: Abre pasta temporária de frames PNG.
    
- **Q**: **Quit**: Retorna ao CLIZK.
    

### 2.2. Ultra Viewer (`zk_ultra.py`)

Navegador de hipertexto com busca integrada.

- **A / V**: **Avançar/Voltar**: Rola conteúdo (23 ou 29 linhas).
    
- **< / >**: **Navegação**: Histórico de arquivos vistos no Ultra.
    
- **M**: **Menu**: Toggle do painel de opções técnicas.
    
- **U**: **Aumentar Tela**: Expande visão em +7 linhas.
    
- **Z**: **Histórico**: Lista numerada para salto rápido.
    
- **Números**: **Salto de Link**: Abre o wikilink ou URL correspondente ao índice.
    
- **LSR**: **Última Busca**: Recupera resultado da última pesquisa AND/OR.
    
- **S**: **Sair**: Salva arquivo como novo LWF e volta à Home.
    

---

## 3. Modos de Pesquisa

- **Home: Entrada (3+ chars)**: Pesquisa de conteúdo (padrão).
    
- **Home: `n [termo]`**: Pesquisa exclusiva por nome de arquivo.
    
- **Home: `a [t1] [t2]`**: Pesquisa **AND** (ambos os termos).
    
- **Home: `o [t1] [t2]`**: Pesquisa **OR** (ao menos um termo).
    
- **Home: `r`**: **Refinar** busca sobre resultados anteriores.
    
- **Home: `c`**: **Contexto** (exibe trechos encontrados).
    
- **Home: `x`**: **Próximas** (termos a até 120 caracteres de distância).
    
- **Tags: Entrada (3+ chars)**: Filtra etiquetas pela string.
    
- **Tags: `p [prefixo]`**: Filtra etiquetas que iniciam com o prefixo.
    
- **Ultra: `and [t1] [t2...]`**: Busca arquivos com todos os termos.
    
- **Ultra: `or [t1] [t2...]`**: Busca arquivos com qualquer termo.
    
- **Ultra: `lsr`**: Recupera lista persistente da última pesquisa no Ultra.
    

---

## 4. Módulos Independentes

### 4.1. Slides / Slideshow (`zk_slides.py`)

Galeria imersiva via `imgcat` (iTerm2).

- **Espaço**: **Menu**: Abre opções técnicas.
    
- **Enter**: **Avançar**: Próxima imagem da tag atual.
    
- **Menu Interno**:
    
    - **N / P**: Navegação manual.
        
    - **X**: Xerox Toggle (Alto contraste P&B).
        
    - **D**: Deteriorar (Ruído e manchas de "toner").
        
    - **L**: Scanlines (Linhas de varredura).
        
    - **O**: Abrir Externo no visualizador do macOS.
        
    - **#**: Mudar Tag de busca.
        
    - **S**: Sair.
        

### 4.2. zk_oneliner.py (Eye-Candy)

Terminal de pílulas de conhecimento com efeito de decodificação.

- **Q**: Encerra o módulo.
    
- **P**: Pausa a animação ou fixação da frase.
    
- **C**: Copia frase atual para o clipboard.
    
- **E**: Abre o Zettel de origem no editor externo.

---
29/03/2026