---
{"dg-publish":true,"permalink":"/57-y66g-como-fazer-as-listas-de-arquivos-para-usar-no-lintalist/","dg-note-properties":{}}
---

tags: #znok
parent: [[souorfaoporenquanto\|souorfaoporenquanto]]

## 20190402211321 como fazer as listas de arquivos para usar no lintalist

**precisa do lintalist**

### seleção de tags

o script para criar, no lintalist, o seletor das tags, é escrito assim:

```

![[Choice=#filter]]]]

```

claro q nid do file "listags_horizontal.txt"; ele foi feito manual e trabalhosa/, tem que abrir o tag_provider.ps1 e copiar dali a lista dos "ValidateSet", daí trocar "," por |

### seletor de files

nao precisamos mais do `listafiles.txt` o script do lintalist agora lista automaticamente;