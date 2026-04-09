---
{"dg-publish":true,"permalink":"/obsidian-testes-demo-exemplos-formatacao-de-markdown-no/","dg-note-properties":{}}
---


tags: #obsidian #internas #ajuda #proj_zetteltex 
parent: [[231011a Obsidian - ajuda caput\|231011a Obsidian - ajuda caput]]
q.v. [[dummy4 demonstracao de query campo de busca nos zettels\|dummy4 demonstracao de query campo de busca nos zettels]]

## Content Index

- [Obsidian testes](#Obsidian testes)
	- [cap1](##cap1)
	- [como inserir uma imagem](##como%20inserir%20uma%20imagem)
	- [como faz transclusão](##como%20faz%20transclusão)
	- [callout (citação fofinha)](##callout%20(citação%20fofinha))
	- [comentário dentro do texto](##comentário%20dentro%20do%20texto)
	- [Resizing images](##Resizing%20images)
		- [cap1a](###cap1a)
		- [cap1b](###cap1b)
	- [cap2](##cap2)
		- [cap2a](###cap2a)
		- [cap2b](###cap2b)
	- [cap3](##cap3)
	- [cap4](##cap4)
		- [cap4.1 ksdjkfhjksadhgfa](###cap4.1%20ksdjkfhjksadhgfa)
	- [cap5](##cap5)
		- [cap5.1 ksdjkfhjksadhgfa](###cap5.1%20ksdjkfhjksadhgfa)
	- [coleção de memes para reutilizar](##coleção%20de%20memes%20para%20reutilizar)


## cap1

Este é o tipo 1 de nota de rodapé[^1], que também pode ser assim, com espaço antes do colchete [^243] é *objeto* desta lide; (c) aqui tentamos o outro tipo de nota^[escrevendo o texto longo dentro dos colchetes, desde que não tenha mais de um parágrafo] para ver se dá. 

E funciona, ao menos com o acento circunflexo colado no texto antes, vamos ver se deixa por um espaço entre texto e acento ^[aqui está o resultado]. Parece versátil e simples. Note que os textos dos rodapés estão logo abaixo do parágrafo, e não no final do textão, o que é prático!

[^1]: hjsgdjfkhagsdkjhfgk jashdgfkjhgfkjhasd

[^243]: esta é a nota 2

## como inserir uma imagem

Este é o jeito simples, imagem tamanho 100%

![Obsidian|700x24](https://obsidian.md/images/banner.png)

Este permite escolher o tamanho (largura?) da imagem:

![Obsidian|200|700x24](https://obsidian.md/images/banner.png)

Como não achei extensão para VSCode para tanto, criei snippet no Beef para por um link para a imagem cujo link estiver no clipboard, `img/`.

![exemplo](https://i.imgur.com/JkrmL4f.jpg) 

**Notar esta bosta**: o Obsidian *não sabe ler espaços* em branco nos caminhos web, tem de trocar tudo por %20 como fizemos em [13V66n jim unger humor charge pague ou entao ponto de vista relatividade armadilhas da linguagem.jpg](/img/user/13V66n%20jim%20unger%20humor%20charge%20pague%20ou%20entao%20ponto%20de%20vista%20relatividade%20armadilhas%20da%20linguagem.jpg.md)

## como faz transclusão

coloca um link para o file a transcluir (eles chamam de "embed") com um ! antes, assim:


<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





tags: #ética 
parent: [[Etica\|Etica]]

 

disse Ortega y Gasset, "as virtudes que não possuímos são as que mais contam para nós" (3M8 pos. 3376)

( #virtudes  #inveja-vícios)


</div></div>


## callout (citação fofinha)

>[!INFO]
> bota o texto aqui
> fica assim

pode ser assim também 

>[!example] Saiba mais...
>este é o texto

Additionally, you can create a folding callout by adding `+` (default expanded) or `-` (default collapsed) after the block.

> [!NOTE]- Are callouts foldable?
> Yes! In a foldable callout, the contents are hidden until it is expanded. Aqui pode por um textão, serve para substituir os vários tipos de texto oculto expansível do tiddly

## comentário dentro do texto

This is an  comment.



## Resizing images

Example of this above image resized to 200 pixels wide:

```md
![Obsidian|200|700x24](https://obsidian.md/images/banner.png)
```

### cap1a
  
As etiquetas suspensas **não funcionam** (acronym). O grifado é ==feito assim==. Ôs dois jeitos de **nota de rodapé** funcionam aqui: pode deixar sem número e meter o texto dentro dos colchetes ^[Teste de nota de rodapé] no *meio do texto* principal, como aqui. E atenção para a ==nota de rodapé com vários parágrafos ^[8s7fd9a8s76dfa9], que, aliás, não funciona!==

Ou pode numerar o troço e [^2] escrever o texto da nota ==no fim do parágrafo onde ele entra==, como aqui, em vez de escrever lá embaixo. Fica mais fácil de editar e manter o texto coerente, e de revisar as notas sem ter de subir e descer a tela. Você [^7864589324] não precisa seguir ou controlar a numeração, pode usar chaves aleatórias. 

[^2]: teste escrevendo o texto da nota de rodapé logo abaixo do parágrafo onde ela é chamada.

[^7864589324]: Usar um texto aleatório como chamada de nota também funciona

### cap1b
 
ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos **efeitos daquele** MS coletivo, impetrad se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos **efeitos daquele** MS coletivo, impetrado pelo SINPOSC, porque não é associado daquele ente; (d) não quer a suspensão deste processo para aguardar a solução do MS.
   
## cap2
   
se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos **efeitos daquele** MS coletivo, impetrado pelo SINPOSC, porque não é associado daquele ente; (d) não quer a suspensão deste processo para aguardar a solução do MS.

### cap2a

hjhgasd se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos **efeitos daquele** MS coletivo, impetrado pelo SINPOSC, porque não é associado daquele ente; (d) não quer a suspensão deste processo para aguardar a solução do MS. se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não 

### cap2b

jkhkasjdhlk se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos **efeitos daquele** MS coletivo, impetrado pelo SINPOSC, porque não é associado daquele ente; (d) não quer a suspensão deste processo para aguardar a solução do MS. se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não 

## cap3

hkjhasdkljhfalksdf se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos **efeitos daquele** MS coletivo, impetrado pelo SINPOSC, porque não é associado daquele ente; (d) não quer a suspensão deste processo para aguardar a solução do MS. se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos **efeitos daquele** MS coletivo, impetrado pelo SINPOSC, porque não é associado daquele ente; (d) não quer a suspensão deste processo para aguardar a solução do MS. se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não

## cap4

### cap4.1 ksdjkfhjksadhgfa

se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos^[nota de rodapé do cap2] **efeitos daquele** MS coletivo, impetrado pelo SINPOSC, porque não é associado daquele ente; (d) não quer a suspensão deste processo para aguardar a solução do MS. se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos **efeitos daquele** MS coletivo, impetrado pelo SINPOSC, porque não é associado daquele ente; (d) não quer a suspensão deste processo para aguardar a solução do MS. se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não

## cap5

### cap5.1 ksdjkfhjksadhgfa

se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos^[nota de rodapé do cap3] **efeitos daquele** MS coletivo, impetrado pelo SINPOSC, porque não é associado daquele ente; (d) não quer a suspensão deste processo para aguardar a solução do MS. se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não se sujeita aos **efeitos daquele** MS coletivo, impetrado pelo SINPOSC, porque não é associado daquele ente; (d) não quer a suspensão deste processo para aguardar a solução do MS. se aplica ao caso a decisão do STJ no REsp nº 1110549, porque o MS de que fala a contestação não demanda o pagamento dos atrasados, que é *objeto* desta lide; (c) o autor não

[^8s7fd9a8s76dfa9]: Here's one with multiple paragraphs and code.
	Indent paragraphs to include them in the footnote.
	`{ my code }`
	Add as many paragraphs as you like.

## coleção de memes para reutilizar

q.v. [[memes-collection-para-reusar-no-Oz2-index\|memes-collection-para-reusar-no-Oz2-index]]