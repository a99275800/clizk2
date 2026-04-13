---
{"dg-publish":true,"permalink":"/como-gravar-audio-direto-da-placa-de-som-no-mac/","dg-note-properties":{}}
---

## adendos
13 de janeiro de 2026 — Tudo abaixo deu certo. Mas o GarageBand é tenso. Para voltar a gravar alguma coisa usando o microfone do Mac, tem de teclar Cmd+vírgula e mudar o dispositivo de entrada para microfone. Se quiser voltar a gravar da placa de som, repete a operação e muda o dispositivo de entrada para BlackHole de novo.
## texto do Gemini
Para realizar o que chamamos de **"Loopback de Áudio"** (capturar o som interno do sistema sem usar microfones), o macOS exige uma ponte virtual, pois, por questões de segurança e direitos autorais, ele não permite essa rota nativamente.

Como você prefere soluções **open source** e de alta qualidade técnica, a melhor ferramenta para o seu MacBook Air M4 é o **BlackHole**.

---

### 1. O Conceito: BlackHole (Open Source)

O BlackHole cria um "cabo virtual". Você envia o som do vídeo para uma extremidade desse cabo e diz ao GarageBand para "ouvir" a outra extremidade.

- **Download:** [Existential Audio - BlackHole](https://github.com/ExistentialAudio/BlackHole) (Escolha a versão de 2 canais/2ch, que é suficiente para podcast).
    

### 2. Configuração: Para ouvir e gravar ao mesmo tempo

O maior desafio é que, se você selecionar o BlackHole como saída de áudio, você não ouvirá o som nas caixas do Mac. Para resolver isso, usaremos o **Ajuste de Áudio MIDI** (nativo do macOS):

1. Abra o **Ajuste de Áudio MIDI** (busque no Spotlight).
    
2. Clique no sinal de **+** no canto inferior esquerdo e selecione **Criar Dispositivo de Saída Múltipla**.
    
3. No painel à direita, marque duas caixas: **Falantes do MacBook Air** (ou sua saída padrão) e **BlackHole 2ch**.
    
    - _Isso fará o som do vídeo sair para você e para o "cabo virtual" simultaneamente._
        
4. Clique com o botão direito neste novo "Dispositivo de Saída Múltipla" e selecione **"Usar este dispositivo para saída de som"**.
    

### 3. Configuração no GarageBand

Agora que o som está "correndo" pelo cabo virtual, vamos capturá-lo:

1. No **GarageBand**, vá em **Ajustes** (Command + vírgula) > **Áudio/MIDI**.
    
2. Em **Dispositivo de Entrada**, selecione **BlackHole 2ch**.
    
3. No **Dispositivo de Saída**, mantenha seus fones ou os falantes do sistema.
    
4. Crie uma nova "Faixa de Áudio" (ícone do microfone).
    
5. **Importante:** Ative o botão de **Monitoramento** (ícone que parece uma onda/frequência na trilha) para ver o sinal entrando.
    

---

### Dicas para Alta Qualidade (M4/macOS 2026)

- **Taxa de Amostragem:** No Ajuste de Áudio MIDI, certifique-se de que tanto o BlackHole quanto sua saída física estejam na mesma taxa (ex: **48.0 kHz**). Isso evita estalos ou distorções no áudio gravado.
    
- **Isolamento de Voz:** Se o vídeo que você está gravando tiver muito ruído de fundo, o macOS 26 possui um excelente isolamento de voz via IA (no Centro de Controle > Modos de Microfone) que pode ser aplicado em tempo real.
    

### Alternativa Profissional (Paga)

Se você precisar fazer isso com frequência e quiser uma interface visual onde pode arrastar cabos virtuais entre apps (Safari para GarageBand, por exemplo), o app **Loopback** da Rogue Amoeba é o padrão da indústria, embora seja pago.

Deseja que eu detalhe como configurar o **Ajuste de Áudio MIDI** para garantir que o som não sofra atraso (latency) durante a gravação?

---
#tech #mac #projetos [[projeto podcast\|projeto podcast]]