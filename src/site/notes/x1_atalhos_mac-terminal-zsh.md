---
{"dg-publish":true,"permalink":"/x1-atalhos-mac-terminal-zsh/","dg-note-properties":{}}
---

o "salto de palavra" automaticamente, a menos que esteja configurado.

- **Saltar para o início da linha:** `Control + A`
    
- **Saltar para o fim da linha:** `Control + E`
    
- **Retroceder uma palavra:** `Option + ←` (Seta para a esquerda)
    
- **Avançar uma palavra:** `Option + →` (Seta para a direita)

No terminal, o "copiar e colar" tradicional (`Command + C / V`) funciona para interagir com o resto do macOS, mas para **manipular o texto que você está digitando no prompt**, usamos atalhos de "Kill and Yank":

- **Apagar (Cortar) do cursor até o início da linha:** `Control + U`
    
- **Apagar (Cortar) do cursor até o fim da linha:** `Control + K`
    
- **Apagar (Cortar) a palavra anterior ao cursor:** `Control + W`
    
- **Colar (Yank) o que você acabou de apagar/cortar:** `Control + Y`

Esses acima cortam mas só dá para colar no terminal, colar fora dele só selecionando com o mouse.

Se você digitou um comando gigante e precisa editá-lo com calma (como se fosse um bloco de notas), aperte: **`Control + X`seguido de `e`**

Isso abrirá o comando atual no editor de texto padrão (geralmente o `vi` ou `nano`). Quando você salvar e fechar o arquivo, o comando será executado automaticamente. Para salvar as alterações no vi e sair tecle Esc (para entrar no modo de comando) e digite `:wq` seguido de Enter.

para isso funcionar tem de executar isto aqui no terminal primeiro:

`echo -e "\n# Ativar edição de linha com Ctrl+X e\nautoload -U edit-command-line\nzle -N edit-command-line\nbindkey '^Xe' edit-command-line" >> ~/.zshrc && source ~/.zshrc`

#tech #mac 