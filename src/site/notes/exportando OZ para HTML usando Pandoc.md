---
{"dg-publish":true,"permalink":"/exportando-oz-para-html-usando-pandoc/","dg-note-properties":{}}
---

## exportando OZ inteiro para HTML usando Pandoc para tentar salvar o Obsidian

Usei o Batch abaixo, que peguei [aqui](). Rodei no `cmd.exe`.

Notar que o OZ tem de estar na pasta `c:\OZ`.


```batch
@ECHO ON
SETLOCAL
SET "sourcedir=C:\OZ"
PUSHD "%sourcedir%"
FOR /f "delims=" %%a IN (
 'dir /b /s /a-d *.md *.html '
 ) DO (
 IF /i "%%~xa"==".md" (
  IF NOT EXIST "%%~dpna.html" pandoc "%%a" -f markdown -t html -o "%%~dpna.html"
 ) ELSE (
  IF NOT EXIST "%%~dpna.MD" ECHO pandoc "%%a" -f html -t markdown -o "%%~dpna.MD"
 )
)
popd
GOTO :EOF
```

ele geram mesmo o conjunto de files, mas não entende o formato de link do Obsidian...