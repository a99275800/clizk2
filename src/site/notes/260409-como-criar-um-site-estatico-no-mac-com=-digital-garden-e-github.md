---
{"dg-publish":true,"permalink":"/260409-como-criar-um-site-estatico-no-mac-com-digital-garden-e-github/","dg-note-properties":{}}
---

### 2. A pasta `dist` funciona como um site estático puro?

**Sim, exatamente.** Quando o motor Eleventy (usado pelo Digital Garden) termina o processamento, ele converte todos os seus zettels, links e imagens em arquivos HTML, CSS e JS padrão.

- **Independência:** Essa pasta é autossuficiente. Ela contém o "resultado final" do seu cérebro digital.
    
- **Hospedagem em qualquer lugar:** Você pode pegar o conteúdo dessa pasta `dist` e arrastá-lo para qualquer outro serviço de hospedagem estática (como **GitHub Pages, Netlify ou Cloudflare Pages**) e ele funcionará perfeitamente como um site.
    
- **Funcionamento Offline:** Se você abrir o arquivo `index.html` dessa pasta no seu navegador localmente, o site deve carregar (embora alguns links ou ícones possam exigir um servidor local simples para funcionar corretamente devido a políticas de segurança do navegador).
- ## 2. A Solução: Build Local (O Caminho ZKM)

Em vez de enviar o Markdown para a Vercel e pedir para ela "trabalhar", você fará o trabalho pesado no seu **MacBook M4** (que é muito mais potente que a máquina de build gratuita da Vercel) e enviará para ela apenas o resultado final (HTML/CSS/JS pronto).

### Como implementar:

1. **Instale o ambiente local:** Você precisará baixar o seu repositório do GitHub para uma pasta no seu Mac.
    
2. **Rode o Build no seu Mac:** No terminal, dentro da pasta do projeto, você executará:
    
    Bash
    
    ```
    npm install
    npm run build
    ```
    
    Isso gerará a pasta **`dist`** no seu computador em poucos minutos.
    
1. **Envie apenas a `dist`:** Você mudará a configuração da Vercel para que ela apenas "sirva" os arquivos prontos, sem tentar processar nada.

## completo
Esta é uma decisão estrategicamente superior sob o **Protocolo ZKM**. Ao processar o build localmente, você utiliza o poder do seu **MacBook Air M4** para realizar em segundos o que a Vercel falha em fazer em 45 minutos.

Aqui está o roteiro minucioso para transformar seu acervo de 3.000 notas em um site estático independente.

---

## 1. Preparação do Ambiente (macOS)

Como você já possui o projeto clonado do GitHub (que o Digital Garden criou), vamos trabalhar dentro dele.

1. **Abra o Terminal** (ou iTerm2) e navegue até a pasta do seu projeto:
    
    Bash
    
    ```
    cd "/Users/albertosantos/Library/Mobile Documents/iCloud~md~obsidian/Documents/Oz2"
    ```
    
2. **Verifique se o Node.js está instalado:**
    
    Bash
    
    ```
    node -v
    ```
    
    _(Se não estiver, instale via Homebrew: `brew install node`)_.
    

---

## 2. Instalação das Dependências

Dentro da pasta do projeto, você precisa instalar as ferramentas que o Digital Garden usa para "cozinhar" o Markdown:

1. **Execute a instalação:**
    
    Bash
    
    ```
    npm install
    ```
    
    _Este comando lerá o seu arquivo `package.json` e baixará o Eleventy e todos os plugins necessários (incluindo o MathJax que causou o erro anteriormente, mas agora no seu hardware local)_.
    

---

## 3. O Build Local (A Conversão)

Agora vamos realizar o "trabalho pesado" que travou a Vercel.

1. **Execute o comando de build:**
    
    Bash
    
    ```
    npm run build
    ```
    
2. **O que acontecerá:** * O Eleventy varrerá seus arquivos em `src/site/notes/`.
    
    - Ele processará todos os `[[wikilinks]]`, converterá o Markdown para HTML e aplicará os temas de CSS.
        
    - **O Resultado:** Será criada uma pasta chamada **`dist`** na raiz do seu projeto.
        

> **Nota Técnica:** Se o build travar por memória no seu Mac (improvável), você pode rodar:
> 
> `NODE_OPTIONS=--max-old-space-size=8192 npm run build`

---

## 4. Testando o Site Localmente (Smoke Test)

Antes de subir para qualquer servidor, você deve ver se o site funciona no seu Mac.

1. **Inicie um servidor local simples:**
    
    Bash
    
    ```
    npx serve dist
    ```
    
2. **Acesse o endereço** fornecido (geralmente `http://localhost:3000`).
    
3. **Verifique:** Navegue pelos links e veja se as imagens aparecem. Se tudo estiver correto, sua pasta `dist` é um site completo.
    

---

## 5. Roteiro de Hospedagem (Escolha seu Servidor)

Agora que você tem a pasta **`dist`**, você pode hospedá-la em qualquer lugar. Aqui estão as três formas mais simples:

### Opção A: Vercel (Upload Direto / CLI)

Para evitar que a Vercel tente fazer o build, você envia os arquivos já "prontos":

1. Instale a ferramenta da Vercel: `npm install -g vercel`.
    
2. Entre na pasta `dist`: `cd dist`.
    
3. Execute: `vercel --prod`.
    
4. **Vantagem:** O site continua no seu domínio atual, mas o build foi feito por você.
    

### Opção B: GitHub Pages (Grátis e Estável)

Se você quer total independência da Vercel:

1. No seu repositório do GitHub, vá em **Settings > Pages**.
    
2. Em **Build and deployment**, mude a origem para **"GitHub Actions"**.
    
3. Configure o GitHub para apenas "servir" a pasta `dist`.
    

### Opção C: Servidor Web Tradicional (HostGator, Bluehost, etc.)

1. Conecte-se via **FTP** ao seu servidor.
    
2. Arraste todo o conteúdo de dentro da pasta `dist` para a pasta `public_html` (ou similar) do seu servidor.
    

---

## 6. Manutenção do Fluxo (Workflow ZKM)

Sempre que você criar novos zettels ou alterar os existentes:

1. **Edite** no Obsidian como de costume.
    
2. **Rode** o script de lote (`dg-publish-lote.py`) para marcar o que quer publicar.
    
3. **Execute** `npm run build` no terminal do Mac.
    
4. **Suba** a pasta `dist` atualizada para o servidor.
    

**Dica de Juiz:** Este processo elimina a incerteza da nuvem. Você tem o controle total do binário gerado antes da publicação.

Deseja que eu detalhe como automatizar esse "npm run build" para que ele aconteça sempre que você fechar o Obsidian?

## deu erro, e agora

### . Comando de Build com Memória Expandida

Em vez de apenas `npm run build`, execute este comando no terminal:

Bash

```
NODE_OPTIONS=--max-old-space-size=8192 npm run build
```

**O que isso faz:** Ele reserva **8 GB** de RAM especificamente para este processo. Como seu Mac M4 gerencia a memória de forma muito eficiente, isso deve ser o suficiente para o Eleventy completar a indexação sem "engasgar".

---

### 2. Se o erro persistir (Otimização de Conteúdo)

Se mesmo com 8 GB o erro continuar, o Eleventy está perdendo muito tempo processando elementos que você talvez não use no site. Você pode desativar os recursos mais pesados no arquivo de configuração do projeto (geralmente `eleventy.config.js` ou `.eleventy.js` na raiz):

- **Desative o Graph View:** A geração do mapa visual é o que mais consome memória.
    
- **Desative os Backlinks:** Se você não precisa ver "quais notas linkam para esta" no rodapé de cada página web, desativar isso economiza 40% de RAM.
    

---

### 3. Checklist de Sanidade ZKM

Antes de rodar o comando de 8 GB, faça uma limpeza rápida nos temporários para garantir um "campo de pouso" limpo:

1. **Limpe a pasta de saída:** `rm -rf dist`
    
2. **Limpe o cache do Eleventy:** `rm -rf .cache`
    
3. **Rode o build:** `NODE_OPTIONS=--max-old-space-size=8192 npm run build`
    

### Por que isso é melhor que na Vercel?

Na Vercel, você está limitado ao que eles oferecem no plano gratuito. No seu Mac, você é o "Juiz" dos recursos. Se precisar de 12 GB, você pode alocar. Uma vez que o comando completar, a pasta `dist` aparecerá e seu site estará pronto para ser movido para qualquer servidor como um arquivo estático puro.

Tente o comando com **8192** e me diga se ele conseguiu atravessar a barreira dos 3.000 arquivos.