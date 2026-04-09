---
{"dg-publish":true,"permalink":"/231102a-obsidian-como-ativei-sincronizacao-no-ipad-via-dropbox/","dg-note-properties":{}}
---

akin: [[Projeto-Zetteltex-AKA-OZ-index\|Projeto-Zetteltex-AKA-OZ-index]]; 
akin: [[Historia deste Zettelkasten e suas sucessivas versoes\|Historia deste Zettelkasten e suas sucessivas versoes]]
akin: [[Ajuda-do-Zetteltex-aka-OZ\|Ajuda-do-Zetteltex-aka-OZ]]
parent: [[231011a Obsidian - ajuda caput\|231011a Obsidian - ajuda caput]]
tags: #ajuda #obsidian #internas #tech #custom 

### update 25/9/24

veja [[240925d Impactos do IPhone no OZ Obsidian Zettelkasten\|240925d Impactos do IPhone no OZ Obsidian Zettelkasten]]

### uma sugestão meio doida do Reddit (que não testei)

GitHub/GitLabs/Git/BitBucket via Working Copy on iOS. The dev is amazing. Private repos are perfectly secure. GitHub employees can’t see private repos. Plus, GitHub works as a 3rd party backup which is highly recommended you have for your vault. I also backup separately directly on my iPad but GitHub also works for that. With shortcuts you can automate it so when you open/close/both Obsidian, it syncs via GitHub/GitLabs/Git/BitBucket.

(...) 

Obsidian can only access vaults in its own sandboxed area on iOS. It cannot open a vault that resides on Dropbox or OneDrive for example. Search here for syncing, and you will find many suggestions to sync between other cloud services and iCloud on iOS. Syncthing (sp?) is supposed to be good, reliable and free although I personally have not tried it.

https://www.reddit.com/r/ObsidianMD/comments/12z4def/ipad_obsidian_dropbox/

### o que realmente acabei fazendo

==There is a community plugin which supports syncing over DropBox **called Remotely Save**==. Instalei esse plugin, autorizei (no Ipad) ele a acessar o dropbox de a99275800@gmail.com (porque o Oz está nele). Daí ele cria um folder: `(...)Dropbox\Aplicativos\remotely-save\Bostoca` (**Bostoca** é o nome do Vault novo que tive de criar no Obsidian do Ipad). *Colei nessa pasta* (`(...)Dropbox\Aplicativos\remotely-save\Bostoca`) o conteúdo todo de Oz. Para atualizar / manter atualizado no Ipad, tem de rodar o terminal no PC, e ali rodar o script `bkIpad.ps1`, e no Ipad tem de abrir o Obsidian e abrir o menu lateral esquerdo e ali achar o botão de update (talvez atualize automaticamente; mas depende de na pasta acima estar a coleção atualizada de zettels)

É uma solução meia boca. Poderia mudar todos os scripts e rotinas para sediar o Oz em definitivo na pasta Bostoca, mas daí teria de dar um jeito de consertar o DropSync no celular para dar certo lá também...

Acho que por ora vou deixar assim, e usar a Bostoca e o Ipad só como cópia morta para consulta, não editar nada lá. V. também [[231102b Obsidian rolo das contas do Dropbox causado no Ipad pelo\|231102b Obsidian rolo das contas do Dropbox causado no Ipad pelo]]
