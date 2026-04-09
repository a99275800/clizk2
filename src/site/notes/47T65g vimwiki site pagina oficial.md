---
{"dg-publish":true,"permalink":"/47-t65g-vimwiki-site-pagina-oficial/","dg-note-properties":{}}
---

tags: #tech #linux #custom #links 
parent: [[26H97v linux principais comandos tutorial\|26H97v linux principais comandos tutorial]]

## 47T65g vimwiki site página oficial 

http://vimwiki.github.io/

Quickstart
Press <Leader>ww (this is usually \ww) to go to your index page. By default it is located in ~/vimwiki/index.wiki.

Feed it with the following example:

```
= My knowledge base =
    * Tasks -- things to be done _yesterday_!!!
    * Project Gutenberg -- good books are power.
    * Scratchpad -- various temporary stuff.
Place your cursor on Tasks and press Enter to create a link. Press Enter again to open it. Edit the new page, save it, and press Backspace to jump back to your index.

A Vimwiki link can be constructed from more than one word. Just visually select the words to be linked and press Enter. Try it with Project Gutenberg. The result should look something like:

= My knowledge base =
    * [[Tasks]] -- things to be done _yesterday_!!!
    * [[Project Gutenberg]] -- good books are power.
    * Scratchpad -- various temporary stuff.
See :h vimwiki for the full documentation.

Basic markup (default syntax)
= Header1 =
== Header2 ==
=== Header3 ===

*bold text*
_italic text_

[[wiki link]]
[[wiki link]]

* bullet list item 1
* bullet list item 2
    a) numbered list item 1
    b) numbered list item 2

{{{python
def greet(s):
    print("Hello, " + s)
}}}

| a table |  |
|---------|--|
|         |  |
For other syntax elements, see :h vimwiki-syntax

Key bindings
<Leader>ww – Open the default wiki index file
<Leader>ws – Select and open wiki index file
<Enter> – Follow/Create wiki link
<Backspace> – Go back to parent(previous) wiki link
<Tab> – Find next wiki link
<Shift-Tab> – Find previous wiki link
For more keys, see :h vimwiki-mappings

Commands
:Vimwiki2HTML – Convert current wiki page to HTML
:VimwikiAll2HTML – Convert all your wiki pages to HTML
For more, see :h vimwiki-commands
```