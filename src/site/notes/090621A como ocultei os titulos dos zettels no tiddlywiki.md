---
{"dg-publish":true,"permalink":"/090621-a-como-ocultei-os-titulos-dos-zettels-no-tiddlywiki/","dg-note-properties":{}}
---


criei um tiddler [[meu-estilinho\|meu-estilinho]], pus nele a tag `(cifrão):/tags/Stylesheet` e escrevi dentro:

```
h2.tc-title {display:none;)
h2.tc-title {display:none;)
```

Parece que assim dá para sobrepor ordens ao CSS padrão sem mexer nele!

tags: #tech #proj_zetteltex #ajuda #custom #tiddlywiki 

veja:

How to hide the author's and other fields with CSS
10th March 2018 at 8:12pm
Sometimes you might want to save some screen space by hiding away the author's name in all tiddlers. Here's a quick way to do it:

Create a new tiddler with any title you want.
Give the tiddler the tag (cifrão):/tags/Stylesheet
In the text field of the tiddler put:
.tc-subtitle .tc-tiddlylink {display:none;}
Save the tiddler. The author's name field should no longer appear.
Similarly, the entire subtitle field including author and date can be removed with:

.tc-subtitle {display:none;}
Unfortunately, you can't hide just the date without also hiding the author using CSS.

And finally, for a truly minimalist look, you can remove the title with:

h2.tc-title {display:none;)