---
{"dg-publish":true,"permalink":"/zkm-diretorio-de-funcoes/","dg-note-properties":{}}
---

**Versão 8.2.2**

Conforme o protocolo ZKM o diretório deve descrever detalhadamente quais são TODAS as funções contidas em TODOS os scripts dizendo o que elas fazem, como funcionam; deve indicar o nome de cada função tal como ele é batizado dentro do código, e descrever sua lógica. Deve dizer, para cada função, que scripts e/ou funções ela chama e por quais scripts / funções é chamada. Deve indicar que letra ou comando chama cada função. 

Este documento serve como a **Teia de Dependências** oficial, detalhando o fluxo de dados entre os vários módulos.

---

# 🕸️ Diretório de Funções Detalhado: Zettelkasten Manager v8.2.1

## 1. `zk.py` (Orquestrador Central)

- **`exibir_cabecalho()`**
    
    - **Lógica**: Limpa a tela e renderiza o visor (13 ou 34 linhas) com stats reais (versão, contagem de zettels, assets e tags).
        
    - **Chama**: `zk_goodies.calcular_estatisticas_reais`, `zk_nav.exibir_barra_nav`, `zk_view.gerar_conteudo_visor`.
        
    - **Chamada por**: `acao_ficheiro_lwf`, loop `__main__`.
        
- **`exibir_stats_lwf(nome_arquivo)`**
    
    - **Lógica**: Abre o LWF para ler tamanho físico e extrair tags via Regex para exibição no rodapé.
        
    - **Chamada por**: `acao_ficheiro_lwf`.
        
- **`menu_captura_lwf(nome_arquivo)`**
    
    - **Comando**: Tecla **(C)** na Home.
        
    - **Lógica**: Submenu para copiar metadados (Wikilink, Path, Contexto, etc) para o clipboard.
        
    - **Chama**: `zk_fileops.capturar_contexto_complexo`, `zk_pile.adicionar_a_pilha`, `zk_goodies.tocar_som`.
        
    - **Chamada por**: `acao_ficheiro_lwf`.
        
- **`acao_ficheiro_lwf(nome_arquivo)`**
    
    - **Lógica**: Loop principal de entrada de comandos. Gere o timeout para efeitos VHS e redireciona para todos os módulos.
        
    - **Chama**: `zk_nav.processar_nav`, `zk_nav.executar_redirecionamento`, `zk_search.realizar_busca_twin_souls`, `zk_core.navegar_resultados`, `zk_core.executar_externo_estrito`, `zk_system.menu_system`, `zk_pile.menu_gestao_pilha`, `zk_tags.menu_gestor_tags`, `zk_tasks.exibir_menu_tasks`, `zk_buffer.menu_buffer`, `zk_goodies.menu_goodies`.
        

## 2. `zk_core.py` (Alicerce e Persistência)

- **`obter_versao_oficial()`**: Lê `zk_version.md`. Chamada na inicialização de `VERSION`.
    
- **`salvar_config_fisica()`**: Grava `.zk_config`. Chamada por `zk_system.salvar_configuracoes`.
    
- **`calcular_estatisticas_reais()`**: Varre o diretório para inventário. Chamada por `zk.exibir_cabecalho`, `zk_goodies.exibir_intro_zkm`.
    
- **`limpar_tela()`**: Executa `clear`. Chamada por todos os módulos.
    
- **`ler_cache(caminho)`** / **`salvar_cache(caminho, lista)`**: I/O de listas `.zk_cache`. Chamada por todo o sistema.
    
- **`sortear_zettel_valido()`**: Motor de aleatoriedade (tecla **D**). Chamada por `get_lwf_single`, `zk_goodies.slideshow_zen`.
    
- **`get_lwf_single()`**: Recupera o LWF do cache. Chamada por `__main__` e `zk_nav.exibir_cabecalho_lwf_modulo`.
    
- **`executar_externo_estrito(app, arquivo)`**: Abre `micro` ou `less` em 80 colunas. Chamada por `zk.acao_ficheiro_lwf`.
    
- **`registrar_trabalho(nome)`**: Define LWF e atualiza histórico. Chamada por `zk.py`, `navegar_resultados`.
    
- **`trocar_lwf_sem_hist(nome)`**: Navegação sem poluir histórico. Chamada por `zk_nav.navegar_journal_direto`.
    
- **`navegar_resultados(lista, ...)`**: Interface de listas paginadas. Chamada por `zk_search`, `zk_tags`, `zk_tasks`, `zk_fileops`.
    
- **`centralizar_output(texto)`**: Calcula margens para centralização. Chamada por `zk_goodies.centralizar_output`.
    

## 3. `zk_search.py` (Busca Avançada)

- **`destacar_termos(texto, termos)`**: Injeta ANSI nos matches. Chamada por `extrair_contexto_v5`.
    
- **`extrair_contexto_v5(rel_path, termos)`**: Snippets de busca (tecla **C** em listas). Chamada por `zk_core.navegar_resultados`.
    
- **`realizar_busca(t1, t2, logica)`**: Motor AND/OR/Nome. Chamada por `processar_busca_centralizada`, `menu_refinar`.
    
- **`realizar_busca_proximidade(lista, t1, t2)`**: Filtro de distância (tecla **X** em listas). Chamada por `zk_core.navegar_resultados`.
    
- **`formatar_item_tss(caminho, tags)`**: Formata linha da TSS. Chamada por `realizar_busca_twin_souls`.
    
- **`realizar_busca_twin_souls(lwf)`**: Interseção de tags (comando **tss**). Chamada por `zk.acao_ficheiro_lwf`.
    
- **`menu_refinar(lista)`**: Refino de resultados (tecla **R** em listas). Chamada por `zk_core.navegar_resultados`.
    
- **`processar_busca_centralizada(input)`**: Analisador de busca na Home. Chamada por `zk.py`.
    
- **`buscar_por_tag_estrito(tag)`**: Busca por hashtag. Chamada por `zk_tags.buscar_por_tag`.
    
- **`listar_zettels_recentes()`**: Ordena por data. Chamada por `zk_fileops.menu_file_ops`.
    
- **`listar_zettels_por_tamanho()`**: Ordena por KB. Chamada por `zk_fileops.menu_file_ops`.
    

## 4. `zk_system.py` (Manutenção e Governança)

- **`gerir_dependencias()`**: Instala `Pillow`. Chamada por `menu_system`.
    
- **`carregar_configuracoes()`** / **`salvar_configuracoes()`**: Sincronia de estado. Chamada por `menu_system`.
    
- **`alternar_para_stable()`**: Swap para pasta `ZK-stable`. Chamada por `menu_system` (tecla **G**).
    
- **`editar_scripts_seguro()`**: Backup + Edição. Chamada por `menu_system` (tecla **E**).
    
- **`criar_zip(nome_base, ...)`**: Backup com injeção de docs de governança. Chamada por `menu_system`, `editar_scripts_seguro`.
    
- **`exibir_changelog_manual()`**: Abre `zk_changelog.md` via `less`. Chamada por `menu_system` (tecla **H**).
    
- **`menu_system()`**: Interface principal **(Y)**. Chama `zk_nav`, `criar_zip`, `editar_scripts_seguro`.
    
- **`exibir_changelog()`**: Função mestre original para visualização de log via dicionário (obsoleta v8.2.1).
    

## 5. `zk_goodies.py` (Estética)

- **`tocar_som(nome)`** / **`tocar_som_absoluto(path)`** / **`parar_todos_sons()`**: Gestão de áudio. Chamada por todo o sistema.
    
- **`centralizar_output(texto)`**: Injeta tremor VHS e Scanlines. Chamada por `zk_core.centralizar_output`.
    
- **`aplicar_glitch_vhs()`**: Efeito visual de ruído. Chamada por `menu_goodies`.
    
- **`barra_progresso_fake(duracao, label)`**: Animação ASCII. Chamada por `tela_loading_zkm`.
    
- **`tela_loading_zkm()`**: Boot imersivo. Chamada por `zk.py`.
    
- **`exibir_intro_zkm()`**: Manifesto ZKM. Chamada por `tela_loading_zkm`.
    
- **`rodar_screensaver_visor()`**: Efeito Matrix. Chamada por `menu_goodies`.
    
- **`exibir_fichamento_metadata(path)`**: Stats em CAIXA ALTA. Chamada por `slideshow_zen`.
    
- **`slideshow_zen()`**: Leitura automática. Chamada por `menu_goodies`.
    
- **`menu_goodies()`**: Interface de extras **(Z)**. Chama `slideshow_zen`, `tela_loading_zkm`.
    

## 6. `zk_pile.py` (Gestão em Lote)

- **`registrar_log_tag(acao, arqs, tag)`**: Auditoria de tags. Chamada por `taguear_em_lote`.
    
- **`registrar_log_delete(arqs)`**: Auditoria de exclusão. Chamada por `deletar_em_lote`.
    
- **`taguear_em_lote()`** / **`untaguear_em_lote()`**: Adição/Remoção de tags. Chamada por `menu_gestao_pilha`.
    
- **`deletar_em_lote()`**: Exclusão em massa. Chamada por `menu_gestao_pilha`.
    
- **`menu_gestao_pilha()`**: Interface principal **(P)**. Chama `zk_nav`, `ler_cache`.
    

## 7. `zk_tags.py` (Etiquetas)

- **`remover_acentos(texto)`**: Normalização Unicode. Chamada por `gerar_nuvem_tags`.
    
- **`extrair_contexto_tag(path, tag)`**: Snippet de tag. Chamada por `buscar_por_tag`.
    
- **`buscar_por_tag(tag)`**: Motor de busca de tags. Chamada por `menu_gestor_tags`.
    
- **`gerar_nuvem_tags()`**: Contagem de tags. Chamada por `menu_gestor_tags`.
    
- **`menu_gestor_tags()`**: Interface principal **(G)**. Chama `buscar_por_tag`, `gerar_nuvem_tags`.
    
- **`gerir_tags_gravadas()`**: Submenu de favoritas. Chamada por `menu_gestor_tags`.
    
- **`capturar_tags_lwf()`**: Copia tags do LWF. Chamada por `menu_gestor_tags`.
    

## 8. `zk_tasks.py` (Tarefas)

- **`coletar_tarefas()`**: Scanner de `- [ ]`. Chamada por `exibir_menu_tasks`.
    
- **`exibir_menu_tasks()`**: Filtros RQR. Interface principal **(K)**.
    
- **`processar_rqr()`**: Lógica de filtragem específica. Chamada por `exibir_menu_tasks`.
    
- **`navegar_resultados_tasks(lista, titulo, labels)`**: Interface de seleção de notas com pendências.
    

## 9. `zk_buffer.py` (Notas)

- **`limpar_log_60_dias()`**: Manutenção de log. Chamada por `menu_buffer`.
    
- **`registrar_log_buffer(cont)`**: Persiste notas. Chamada por `menu_buffer`.
    
- **`processar_copia_buffer(modo)`**: Envia ao clipboard. Chamada por `menu_buffer`.
    
- **`visualizar_historico_buffer()`**: Abre log. Chamada por `menu_buffer`.
    
- **`menu_buffer()`**: Interface principal **(B)**. Gatilhos: `+`, `!`, `T`.
    

## 10. `zk_fileops.py` (Operações)

- **`exibir_lista_estatistica(lista, labs, tit)`**: Interface de seleção rápida. Chamada por `menu_file_ops`.
    
- **`buscar_referentes_logica(termo)`**: Busca citações ao LWF (tecla **F** na Home). Chamada por `zk.py`.
    
- **`extrair_links_do_arquivo(nome)`**: Lista wikilinks (tecla **X** na Home). Chamada por `zk.py`.
    
- **`capturar_contexto_complexo(nome)`**: Extrai blocos `#index`. Chamada por `zk.menu_captura_lwf`.
    
- **`menu_file_ops()`**: Interface principal **(I)**. Chama `criar_novo_zettel`, `renomear_zettel_estrito`.
    
- **`renomear_zettel_estrito()`**: Renomeia arquivo. Chamada por `menu_file_ops`.
    
- **`deletar_zettel_estrito()`**: Apaga arquivo. Chamada por `menu_file_ops`.
    
- **`criar_novo_zettel()`**: Cria novo MD. Chamada por `menu_file_ops`.
    

## 11. `zk_view.py` (Visor)

- **`formatar_em_bloco(texto, ...)`**: Quebra parágrafo. Chamada por `gerar_conteudo_visor`.
    
- **`formatar_lista(lista, ...)`**: Renderiza arrays. Chamada por `gerar_conteudo_visor`.
    
- **`gerar_conteudo_visor(modo, ...)`**: Switch case Modos 1-6. Chamada por `zk.exibir_cabecalho`.
    

## 12. `zk_visor_logic.py` (Render)

- **`aplicar_formatacao_zkm(texto, styles)`**: Tradutor ANSI. Chamada por `calcular_paginacao_fisica`.
    
- **`calcular_paginacao_fisica(...)`**: Enquadramento 80x20. Chamada por `zk_core.navegar_resultados`.
    

## 13. `zk_nav.py` (Navegação Global)

- **`exibir_cabecalho_lwf_modulo()`**: Nome do LWF no topo. Chamada por `exibir_barra_nav`.
    
- **`exibir_barra_nav(suprimir)`**: Linha de atalhos. Chamada por `zk.exibir_cabecalho`, `menu_system`, etc.
    
- **`processar_nav(entrada)`**: Tradutor de `/H` a `/Z`. Chamada por loops de input.
    
- **`executar_redirecionamento(destino)`**: Executa o menu alvo. Chamada por `zk.acao_ficheiro_lwf`.
    
- **`navegar_journal_direto(direcao, lwf)`**: Salto entre datas. Chamada por `zk.acao_ficheiro_lwf`.
    

## 14. `zk_attachments.py` (Anexos)

- **`exibir_imagem_ascii(path)`**: Imagem ASCII. Chamada por `renderizar_anexo_visor`.
    
- **`renderizar_anexo_visor(path)`**: Abre anexos. Chamada por `gerir_anexo_externo`.
    
- **`gerir_anexo_externo(path)`**: Interface de comandos para não-MD. Chamada por `zk.acao_ficheiro_lwf`.
    

## 15. `zk_vhs.py` (Efeitos)

- **`obter_caractere_corrompido(char)`**: Letras gregas/japas. Chamada por `zk_goodies.centralizar_output`.
    
- **`calcular_proximo_pulso()`**: Ciclos de instabilidade. Chamada por `zk.acao_ficheiro_lwf`, `slideshow_zen`.
    

