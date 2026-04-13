---
{"dg-publish":true,"permalink":"/deleting-tiddlers-via-lists/","dg-note-properties":{}}
---


A solution inspired [[by posts\|by posts]] from [[Stephan Hradek\|Stephan Hradek]] and [[Metabele\|Metabele]] to delete tiddlers using a filtered list...

{{(cifrão):/.tb/templates/delete-filter}}

;all tiddlers
:`[is[tiddler]#is[system]]`
;tagged "Macros"
:`[tag[Macros]]`
;tagged "Macros" containing "sidebar"
:`[tag[Macros]search[sidebar]]`

The source code to drag and drop to your wiki <<source (cifrão):/.tb/templates/delete-filter>>