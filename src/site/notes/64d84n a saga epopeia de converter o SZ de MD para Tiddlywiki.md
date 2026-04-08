---
{"dg-publish":true,"permalink":"/64d84n-a-saga-epopeia-de-converter-o-sz-de-md-para-tiddlywiki/","dg-note-properties":{}}
---


tags: #ajuda #proj_zetteltex #zettelkasten #tech #tiddlywiki
parent: [[Projeto-Zetteltex-AKA-OZ-index\|Projeto-Zetteltex-AKA-OZ-index]]

## 64d84n a saga epopeia de converter o SZ de MD para Tiddlywiki

1. dá para somente atualizar, isto é, basta incluir os vb. de data recente, não tem de regerar o set todo...

2. coleta os vb. que precisa incluir, copia para a pasta teste no desktop

3. usa o ReplaceText para fazer as mudanças

4. basicamente as replaces são:

   1. troca {}e por {}e{}e{}e

   2. troca ! por !

   3. troca ' por '

   4. troca outro por outro

5. notar que depois de convertido as tags serão marcadas por ! e não!, por exemplo #zettelkasten vira #zettelkasten

6. suponho que deva replace \t por >

7. acho que daí é só importar para dentro do sz.html

8. pensando melhor, como o ReplaceText parece corromper alguns arquivos, e como só vai atualizar com os verbetes novos, pode usar o Replace In Files do npp, e daí trocar:

   1. troca # por !

   2. troca ' por '

   3. troca \n\r por \n\r\n\r

   4. troca \l por \n\r\n\r

   5. troca \n por \n\r\n\r

   6. troca outro por outro

9. deu certo isso no teste de hoje 2705202122hoje

10. pode largar os verbetes novos no SZ que ele substitui os velhos

11. novas descobertas: se apagar as marcas <!-- e --> do cabeço, e trocar a extensão do arquivo .md para .tid antes de importar, ele reconhece as tags; mas apaga o parent, coisa a resolver;

12. mas é possível trocar no cabeço a palavra parent por source, e daí o campo aparece na área de campos do tiddler;

13. da mesma forma pode-se trocar title por caption, e ficaria aproveitável;

14. mas tem de fazer essas coisas antes da primeira importação...