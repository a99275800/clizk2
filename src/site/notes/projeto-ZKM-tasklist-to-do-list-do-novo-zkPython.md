---
{"dg-publish":true,"permalink":"/projeto-zkm-tasklist-to-do-list-do-novo-zk-python/","dg-note-properties":{}}
---

## ambições e inovações planejadas

1. o emendador de frases aleatõrias de zettels com duas ou mais tags em comum
2. UMA PESQUISA contextual do tipo AND mas que pega termos dentro do mesmo parágrafo
3. o screensaver derretedor da tela home
4. search for siblings
5. módulo novo zettel
6. preenchimento de tags com fuzzy
7. preenchimento de [[wikilinks\|wikilinks]] com fuzzy
8. ultra com índice de subtítulos
9. seria legal um slideshow que fosse sorteando um zettel (journals, de preferência) e exibindo um parágrafo de cada vez, interrompendo para mostrar as imagens vinculadas
## imgcat, o comando que funciona

imgcat -W auto -H 100% -r


---
## revisão para v8.2.2:
1. por uma linha em branco no alto do visor no modo lwf
2. o alternador para versão gold na tela system alterna para 8.0.1 que está bugada
3. o ultra precisa fechar com enter vazio
4. o módulo tasks idem
5. as barras de progresso só se ativam se a opção goodies ON é aplicada no prompt do terminal ao chamar o CLIZK. Ativar os goodies dentro do CLIZK ativa os sons mas não as barras.
6. a opção Retro ON não faz nada
7. eliminar i g k p b da tela home
8. aumentar a variedade de sons (som de fundo ruído branco?)
9. a tela tasks não está aceitando `enter vazio` como equivalente a `/h enter`
10. perfeccionismo, mas se a Pile inclui um item já apagado o comando taguear funciona mas o untaguear dá erro / será que o untaguear não buga se a lista é fiel?

```
T Traceback (most recent call last):

  File "/Users/albertosantos/Library/Mobile Documents/iCloud~md~obsidian/Documents/Oz2/zk.py", line 271, in <module>

    if lwf and os.path.exists(os.path.join(FOLDER, lwf)): acao_ficheiro_lwf(lwf)

  File "/Users/albertosantos/Library/Mobile Documents/iCloud~md~obsidian/Documents/Oz2/zk.py", line 217, in acao_ficheiro_lwf

    if zk_nav.executar_redirecionamento(nav_dest): return

  File "/Users/albertosantos/Library/Mobile Documents/iCloud~md~obsidian/Documents/Oz2/zk_nav.py", line 78, in executar_redirecionamento

    modulos[destino]()

  File "/Users/albertosantos/Library/Mobile Documents/iCloud~md~obsidian/Documents/Oz2/zk_pile.py", line 255, in menu_gestao_pilha

    with open(path, "r", encoding="utf-8") as f: cont = f.read()

FileNotFoundError: [Errno 2] No such file or directory: '/Users/albertosantos/Library/Mobile Documents/iCloud~md~obsidian/Documents/Oz2/meleca1.md' 
```
9.
 11. Adicionar a segunda página de menu na home


```
   (última linha de texto do visor)           
  --------------------------------------------------------------------------------
  📍 LWF: NOME-DO-LWF                              
   Size: 19.5 Kb | LastUp: 15-03-26 | Tags: #from_encyclo                         
  --------------------------------------------------------------------------------
  (lines xx): altura MA   (V): Ver na tela            (=): Modo Alto (ON / rola)       
  (Z): anima visor        (W): formata visor          (TSS): Twin-Souls-Search    
  ( ): work in progress   ( ): work in progress       ( ): work in progress            
  ( ): work in progress   ( ): work in progress       ( ): work in progress       
  ( ): work in progress   ( ): work in progress       ((cifrão)): menos comandos          
  --------------------------------------------------------------------------------
  Escolha ação:

```



## anexos
[[projeto-ZKM-OZ-em-python-index\|projeto-ZKM-OZ-em-python-index]]
[[projeto-ZKM-menu-certo\|projeto-ZKM-menu-certo]]





#projeto-ZKM #projetos #mac #proj_zetteltex [[projeto-ZKM-OZ-em-python-index\|projeto-ZKM-OZ-em-python-index]] #inbox #internas #consertar 