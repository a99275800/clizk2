---
{"dg-publish":true,"permalink":"/projeto-zkm-oz-em-python-mapa-de-calor/","dg-note-properties":{}}
---

## mapa de calor

| **Comando Home**   | **Função Alvo**                     | **Módulo**      | **Ficheiro/Dependência**              | **Status Atual**          |
| ------------------ | ----------------------------------- | --------------- | ------------------------------------- | ------------------------- |
| **L**              | `navegar_resultados`                | `zk_core.py`    | `LWF_HIST`                            | Ativo                     |
| **V**              | `subprocess.run(['less'])`          | `zk.py`         | `FOLDER` / `nome_arquivo`             | Ativo                     |
| **M**              | `subprocess.run(['micro'])`         | `zk.py`         | `FOLDER` / `nome_arquivo`             | Ativo                     |
| **X**              | `extrair_links_do_arquivo`          | `zk_fileops.py` | `extrair_links_regex`(`zk_search.py`) | **Crítico (Ponto 10/11)** |
| **C**              | `menu_captura_lwf`                  | `zk.py`         | `capturar_contexto_complexo`          | **Crítico (Ponto 1)**     |
| **R/C/X** (Listas) | `menu_refinar` / `extrair_contexto` | `zk_search.py`  | `navegar_resultados`                  | **Crítico (Ponto 12)**    |

## Manifesto de Dependências (O Contrato)

|**Módulo**|**Entrega (Exports)**|**Necessita (Imports)**|
|---|---|---|
|**zk_core.py**|`LARGURA_MENU`, `calcular_estatisticas_reais`, `registrar_trabalho`|_Nenhum (Base)_|
|**zk_goodies.py**|`tela_loading_zkm`, `centralizar_output`, `tocar_som`|`zk_core` (stats e config)|
|**zk_nav.py**|`exibir_barra_nav`, `exibir_cabecalho_lwf_modulo`|`zk_goodies` (centralização)|
|**zk_view.py**|`gerar_conteudo_visor`|`zk_core` (caches)|
|**zk_search.py**|`processar_busca_centralizada`, `extrair_links_regex`|`zk_core`, `zk_goodies`|
|**zk.py**|_Loop Principal_|**Todos os outros 12 módulos**|
