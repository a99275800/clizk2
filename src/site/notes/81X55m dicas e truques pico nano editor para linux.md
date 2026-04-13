---
{"dg-publish":true,"permalink":"/81-x55m-dicas-e-truques-pico-nano-editor-para-linux/","dg-note-properties":{}}
---

tags: #tech #linux #custom
parent: [[26H97v\|26H97v]]

## 81X55m dicas e truques pico nano editor para linux

Alt S para ver as linhas inteiras (não sangrando para fora da tela);

Alt J para justificar o texto todo. (NUNCA use isto, estraga os arquivos)

endereço do executável:

E:\prog\cmder\vendor\git-for-windows\usr\bin\nano.exe

sim q tanto faz usar o nano ou o rnano

sim q nao gi ler sm files (criados no npp??)

inseri ts func no zettel_functions para poder abrir files digitando só `nano nomedofile`:

```

        function nano ((cifrão)File){

            (cifrão)a = ls (cifrão)File

            cd "E:\prog\cmder\vendor\git-for-windows\usr\bin\"

            .\nano.exe (cifrão)a

            cd (cifrão)zp

        }

```

mas veja só: bastaria digitar `wsl nano '.\nomedofileparaabrir.ext'`, porque temos o wsl instalado, e ele tem nano!