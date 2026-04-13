---
{"dg-publish":true,"permalink":"/nosso-servidor-domestico-de-midia-emby-esta-no-ar/","dg-note-properties":{}}
---

## update sobre isto em janeiro 2025:

**Novo servidor caseiro (que roda no meu velho PC de mesa) no ar**  

13 de dezembro de 2025: único endereço que funcionou no Mac: #mac 
http://192.168.15.31:8096/web/index.html#!/home
daqui para baixo pode estar obsoleto (ao menos no Mac não funciona)

Endereço ip é [192.168.15.31](https://192.168.15.31/ "https://192.168.15.31/")  
  
Como o antigo, os serviços web são acessados com o ip e mais um número de porta  
  
8096 para o servidor de mídia (U `manajerk` S `1312`)  
8069 para o cliente de bittorrent (U `admin` S `131211`)  
8384 para o Syncthing (que permite sincronizar coisas do PC ou Celular para o servidor, pendente instalar um programa no seu PC ou Celular, se isso for relevante a seus interesses) (U `admin` S `1312`)  
  
O diretório home está exposto à rede, com todos os seus oito terabytes, podendo ser acessado em `\\192.168.15.31\mediaserver` (U `dragon` S `1312`)  
  
O diretório 'embyvids' dentro desse home é onde arquivos de vídeo para o servidor de mídia devem ser postos (está vazio nesse momento). Respeitando a mesma divisão de tv/animação/filmes como subdiretórios.  
  
Há algumas configurações faltando  
Mas já dá pra começar a usar.  
  
O servidor antigo continua online no endereço de sempre.16:24

Interface de busca parece estar habilitada > Quando estiver fazendo o download lembre de apontar ele pra /home/dragon/embyvids — De preferência na subpasta já certa  


## como acessar isto fora da rede de casa

usar app [tailscale](https://login.tailscale.com)
acesso à minha conta no tailscale usa login do google de a99275800@gmail.com
precisa acessar isto no app do tailscale (é o endereço da rede)
`100.80.57.44`
se usar tailscale no navegador, apaga o www que vai ter antes desses números e no fim põe `:8096`
teoricamente só acessar minha conta emby que tem nome `dad` e aparentemente não tem senha (se der alguma zebra, o acesso do vitor é com user admin e senha 1312)
teoricamente isso é feito uma vez, e daí por diante n o app do emby fica salva a conta do tailscale (a rede carregada através dele) como uma rede a mais; 


---
## coisas de 2024:

**sobre o servidor velho que roda no notebook branco**

**novo** 29/5/24: parece que agora o endereço é este: http://192.168.15.105:8096/web/index.html#!/home

> Vitor Germano:  Embora não tenha nada além de três coisas para teste nele.  
  
Queria que você testasse do lado daí também > Alberto Santos PR: manda o link > Vitor Germano:

[http://192.168.18.170:8096/](http://192.168.18.170:8096/) é a interface de Streaming. Só tem um perfil criado ("manajerk") e a senha dele é 1418  
  
[http://192.168.18.170:8069/](http://192.168.18.170:8069/) é a interface do qbittorrent, e dá pra mandar ele baixar mais coisas remotamente. As credenciais dessa são "admin"<->141814 > 

**tem de salvar os filmes em `home/emby-server-local/movies`**
ou `tv` ou `animation`

Alberto Santos PR: 1ª parte, positivo, funciona > Alberto Santos PR: dá para acessar no celular e projetar na TV da sala, pelo jeito > Vitor Germano: Dá.  
Tem que instalar o app do Emby no celular > Vitor Germano: Mas é bem simples > Vitor Germano: E no celular ele autodetecta servidores na mesma rede local > Vitor Germano: Então não tem que memorizar o IP > Alberto Santos PR: qualquer coisa que baixar nessa interface do torrent cai no servidor, certo? > Alberto Santos PR: e os arquivos que já tenho, dá para transferir para o HD do servidor manualmente?

  
Outra coisa, uma atualização do nosso servidor de mídia:  
Por razões de "eu cometi um erro durante a configuração inicial", a pasta onde os arquivos devem ser baixados quando você estiver torrent-ando coisas para o servidor não é mais `/opt/emby-server-local` mas `/home/emby-server-local`  
  
**_Adicionalmente_** eu configurei o servidor para ter sua estrutura de arquivos acessível através da rede. Ou seja, você pode mover arquivos para ele direto do seu notebook usando a LAN.  
  
Em um computador windows se você for em `Este Computador` (no meu tempo chamava 'meu computador' :P) e clicar com o botão direito no vazio, deve aparecer uma opção de `Adicionar Drive de Rede`  
  
Quando pedir o endereço ele é `\\192.168.18.170\emby-server-home` e as credenciais são `pillow` `1312`

#tech #vídeos #links piratex