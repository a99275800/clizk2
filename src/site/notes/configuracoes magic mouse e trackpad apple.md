---
{"dg-publish":true,"permalink":"/configuracoes-magic-mouse-e-trackpad-apple/","dg-note-properties":{}}
---

Parabéns pelo novo **MacBook Air M4**! É comum que, ao usar o Magic Mouse pela primeira vez, a sensibilidade padrão do macOS pareça "pesada" ou lenta, especialmente em telas de alta resolução.

Existem três níveis de ajuste para resolver isso: do mais simples ao mais avançado.

### 1. Ajuste Padrão (Interface do Sistema)

O primeiro passo é levar o controle deslizante ao máximo nas configurações oficiais:

1. Clique no **Menu Apple ()** > **Ajustes do Sistema**.
    
2. Na barra lateral, role até encontrar **Mouse**.
    
3. Em **Velocidade de rastreamento**, arraste o controle para a direita (em direção ao "Rápido").
    

### 2. Desativar a Aceleração do Ponteiro

Se mesmo rápido você sente que o mouse "prende" em movimentos curtos, o culpado pode ser a aceleração:

1. Ainda na tela de ajustes do **Mouse**, clique no botão **Avançado**.
    
2. Desative a chave **Aceleração do ponteiro**.
    
    - _Isso faz com que o ponteiro se mova de forma linear: a distância percorrida na tela será sempre proporcional ao movimento físico, sem depender da velocidade do seu pulso._
        

---

### 3. "Super Velocidade" via Terminal (Solução Pro)

Muitos usuários acham que o limite máximo do ajuste padrão ainda é insuficiente. Você pode forçar o macOS a ir além do limite da barra deslizante usando um comando no Terminal:

1. Abra o **Terminal** (via Spotlight, pressionando `Command + Espaço` e digitando "Terminal").
    
2. Copie e cole o seguinte comando e aperte Enter:
    
    defaults write -g com.apple.mouse.scaling 5.0
    
    (O padrão máximo da barra é geralmente 3.0. Você pode testar valores como 7.0 ou 9.0 se desejar ainda mais velocidade).
    
3. **Importante:** Você precisa **reiniciar o Mac** ou encerrar a sessão (Log out) para que essa alteração tenha efeito.
    

---

### Dicas Adicionais

- **Superfície:** O Magic Mouse é sensível à superfície. Ele funciona melhor em mousepads rígidos ou superfícies levemente foscas. Se a mesa for de vidro ou muito brilhante, o sensor laser pode falhar.
    
- **Limpeza:** Verifique se não há nenhum fio de cabelo ou poeira nas duas fendas pretas na parte inferior, onde fica o sensor.
    
- **Apps de Terceiros:** Se quiser um controle total sobre as curvas de aceleração e velocidade sem usar o Terminal, recomendo o app **LinearMouse** (gratuito) ou o **BetterTouchTool**.
    

---

Este vídeo mostra visualmente como encontrar os menus de ajuste no sistema: [Como mudar a velocidade de rastreamento do Magic Mouse](https://www.youtube.com/watch?v=11cDN3liV7M). Ele é útil para confirmar se você está navegando no caminho correto dos Ajustes do Sistema do macOS.

Gostaria que eu explicasse como configurar os **gestos multitoque** do Magic Mouse para facilitar sua navegação no MacBook Air?

#mac #tech [[macOS magic mouse apple como aumentar a velocidade resolucao mais videos para ver\|macOS magic mouse apple como aumentar a velocidade resolucao mais videos para ver]] [[apple\|apple]]