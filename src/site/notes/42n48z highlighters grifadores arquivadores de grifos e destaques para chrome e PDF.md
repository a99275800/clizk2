---
{"dg-publish":true,"permalink":"/42n48z-highlighters-grifadores-arquivadores-de-grifos-e-destaques-para-chrome-e-pdf/","dg-note-properties":{}}
---



tags: #tech #custom #links #zettelkasten #proj_zetteltex
akin: [[Projeto-Zetteltex-AKA-OZ-index\|Projeto-Zetteltex-AKA-OZ-index]]
parent: [[tech stuff programas customizacao index\|tech stuff programas customizacao index]]

## 42n48z highlighters grifadores arquivadores de grifos e destaques para chrome e PDF

### Glasp

> meu acervo no Glasp está [[aqui\|aqui]]

Funciona ótimo, mas claro que cedo ou tarde vão começar a cobrar e daí podemos perder tudo. Por ora, não usar para nada importante de verdade, ou só usar se for exportar imediatamente para NSZ (é o que estou fazendo até hoje, 11/9/23). Defeito: como o Diigo, não funciona no Ipad.

A vantagem dele em relação ao Diigo, além da aparência, é que tem um bom resumidor baseado em IA.

### Diigo

> minha biblioteca / acervo Diigo está [[aqui\|aqui]]

Só funciona se pagar, porque o limite para contas grátis é de 500 highlights. Mas, tirando isso, ótimo. Faz tudo que o Weava faz, e tem umas vantagens. Os aplicativos para IPad e Android funcionam (do mesmo jeito que tudo funciona no IPad: tem de compartilhar o site com o Diigo, e ali fazer os grifos). Outras vantagens: exporta o PDF grifado em "formato texto" (O Weava exporta uma foto dele, não dá para copiar texto, exportar os grifos, continuar grifando em outro app; o PDF do Diigo permite tudo isso). A pesquisa por palavra na coleção de grifos funciona perfeita e rapidamente. Não trava, e abre rápido os arquivos grifados (ao contrário do Weava). 

Diferenças: abre e grifa sem problema os PDFs depositados no OneDrive (o Weava é inconsistente nisso), mas se você grifa um PDF que achou online num saite "normal", como a encyclopaedia, ele só grifa se upar o PDF para a nuvem dele. Não achei informe sobre limitação de espaço de armazenamento mas pode ser um problema. De todo modo arquivar os PDFs no OneDrive não é nada demais.

O mais genial é que tem um outliner embutido: você pode arrastar as citações do banco de grifos para dentro do outliner, enquanto faz ali o esqueleto do seu texto!

Não tem pastas, usa tags no lugar, mas aparentemente isso é mais versátil.

O mais genial: se você grifa um site usando ele, quando você abre a página grifada a partir dele, e exporta para o JustRead, este pega os grifos e os mantém! Ele também grifa/captura emails do Gmail, e consegue abrir os emails quando clica no link, mesmo que eles já tenham sido jogados no lixo do Gmail (o Weava também grifa emails, mas não consegue reabri-los clicando no link, abre a tela principal do Gmail).

### Weava

[Weava](https://www.evernote.com/shard/s672/nl/124106736/3aced116-6293-4118-a9fa-d49030e0995a?title=weava%20highligther%20para%20sites%20saites%20e%20pdfs) para Chrome, é o melhor grifador e a conta grátis armazena até 100 Mb. Permite grifar artigos online e PDFs. Para estes, você pode grifar online ou subir um do seu PC. Exporta os grifos em formato docx ou texto (exporta por pasta, ou você pode marcar/selecionar um ou alguns grifos para copiar para o clipboard). Permite notas e também as exporta. Pode deletar grifos no painel de controle, e editar as notas lá (ou incluí­-las por lá). Tem campos para referência bibliográfica. Parece sólido e bem confiável. Cinco cores de grifos, até 3 pastas no modo grátis. 

Mais legal é que tem app que funciona para IPad! E você não precisa upar os PDFs para o app, pode colocar no OneDrive e usar o Weava para grifar (ao menos no PC funciona) e ele aceita. (Quando abre no OneDrive o PDF grifado, demora um pouco para aparecerem os grifos, é só esperar). O link que de dentro do Weava deveria abrir o PDF no OneDrive não funciona. Tem de achar e abrir o PDF no OneDrive manualmente. No Dropbox não funciona! E definitivamente não dá para ver os PDFs no app do Weava no IPad, só dá acesso aos grifos.

Fora da experiência OneDrive, para grifar um PDF que está em outra parte da internet, num saite "normal", como o nsvg4 ou a encyclopaedia por exemplo, tem de começar clicando no botão da extensão do Weava no alto à direita. Ele parece abrir no seu próprio app uma cópia do PDF, mas pelo que vi ele não salva na sua nuvem, não usa o espaço da conta grátis. Testei hospedando na encyclopaedia, e apenas colando o nome do PDF e a extensão depois do endereço `http://encyclopaedia.site44.com/`, e deu certinho.

Nos testes, parece que hospedando PDFs no OneDrive dá muito problema e frequentemente não carrega mais no Weava o texto integral. Com a opção encyclopaedia deu certo sempre.

Ao que parece não dá para abrir os PDFs grifados no IPad, a partir do Weava. Mas dá para ler os grifos.

Mesmo que não seja uma opção confiável paara escrever uma tese, por exemplo, para ler um PDF casual e apenas extrair os grifos com simplicidade é ótimo app. Melhor que usar a opção Dropbox+Foxit, porque extrai automaticamente e ainda coleciona os grifos.

Só que o sistema de busca por frase ou palavra é muito lento. Preferido.

### WebScrapBok

Uma extensão open source para Chrome (EV IUI 210521a). Complicada de configurar, e é uma ideia diferente: salva as páginas saites offline no seu disco. Daí dá para (na verdade tem de) rebatizá-las IMEDIATAMENTE com um nome inteligível (porque a extensão põe nomes malucos numerados), e mover para a encyclopaedia ou o OneDrive (preferencialmente a encyclopaedia, para poder depois grifar usando o Weava ou o Diigo ou mandar para o JustRead).

Tem de lembrar que (a) precisa renomear imediatamente o arquivo, (b) antes de usar tem de configurar as opções para não salvar imagens, vídeos e áudios, trocando por links, e (c) configurar para salvar em uma única página html, senão para cada captura é uma festa de CSSs e outros files auxiliares.

O "editor" que permite por grifos e notas nas páginas antes de salvar é bom, e também apaga elementos que você não queira salvar. O defeito é que não exporta o texto dos grifos, como fazer Diigo e Weava.

Vantagens: salvou, é seu para sempre.

Desvantagens: tem um grifador, mas só funciona se usa antes de capturar. Para grifar depois de capturar precisa ter outro app, como o Diigo, ou instalar um troço em Python que parece complexo e não funcionará no Fórum.

Acho, enfim, que não vence o JustRead no quesito substituto do evernote para arquivar artigos.

### Hypothesis

[Hypothesis](https://hypothes.is/users/a99275800) [^g7wf9] para Chrome, era o preferido antes do weava e há grifos salvos lá. Muito eficiente e completo, e totalmente grátis. Mas tem defeitos. Não há uma exportação exatamente, você tem de copiar os grifos e colar num texto, mas vai uma porção de informação interna deles junto. E não permite formatar o texto do painel, as letras são muito pequenas. O resto é bom. 

### Super Simple

Esse [grifador](https://chrome.google.com/webstore/detail/super-simple-highlighter/hhlhjgianpocpoppaiihmlpgcoehlhio) é muito prático, e funciona. único defeito: não tem exportador, tem de copiar e colar os grifos. Mas cola todos os parágrafos emendados! não fosse isso, seria perfeito.

### Zotero

v. [[25j73q\|25j73q]] como usar zotero e dropbox para armazenar e grifar pdfs grátis

### notas

[^g7wf9]: [zinia aqui](https://www.evernote.com/shard/s672/nl/124106736/8e78edef-8431-4866-928f-b375278243d3?title=hypothesis%20conta%20anotador%20online%20para%20saites%20pdf%20e%20epub%20ziniaz)

