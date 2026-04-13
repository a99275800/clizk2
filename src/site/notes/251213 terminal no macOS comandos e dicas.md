---
{"dg-publish":true,"permalink":"/251213-terminal-no-mac-os-comandos-e-dicas/","dg-note-properties":{}}
---

> q.v. [[ghosttypdicas-truques-terminal-macOS\|ghosttypdicas-truques-terminal-macOS]]
## Lista Completa dos Comandos Mencionados e Suas Funções

Abaixo está a lista dos comandos e suas funcionalidades, com o respectivo tempo no vídeo:

### Comandos de Produtividade e Sistema

|Comando|Descrição|Timestamp|
|---|---|---|
|`say [texto]`|Faz o Mac ler em voz alta o texto digitado.|[[00:15](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=15)]|
|`security find-generic-password -wa [nome da rede Wi-Fi]`|Revela a senha de uma rede Wi-Fi armazenada.|[[00:28](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=28)]|
|`|pbcopy`|Copia a saída de qualquer comando para a área de transferência.|
|`caffeinate`|Mantém o Mac ativo e impede que entre em modo de repouso.|[[01:12](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=72)]|
|`defaults write com.apple.screencapture name "[novo_nome]"`|Altera o nome padrão de todos os arquivos de captura de tela.|[[01:59](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=119)]|
|`defaults write com.apple.screencapture type [formato]`|Altera o formato de arquivo padrão das capturas de tela (ex: `jpeg`).|[[02:12](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=132)]|
|`defaults write com.apple.screencapture location [caminho]`|Altera o local padrão onde as capturas de tela são salvas.|[[02:17](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=137)]|
|`passwd`|Permite alterar a senha do usuário.|[[02:42](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=162)]|
|`shutdown -h now`|Desliga o computador imediatamente.|[[10:21](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=621)]|
|`shutdown -r now`|Reinicia o computador imediatamente.|[[10:25](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=625)]|
|**Habilitar Touch ID para `sudo`**|Edita o arquivo `/etc/pam.d/sudo` (adicionando `auth sufficient pam_tid.so`) para permitir o uso do Touch ID para comandos que exigem `sudo`.|[[10:31](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=631)]|

### Comandos de Navegação e Arquivos (Comuns no Unix/Linux)

|Comando|Descrição|Timestamp|
|---|---|---|
|`cd [diretório]`|Muda para o diretório de trabalho especificado.|[[04:11](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=251)]|
|`cd` (com espaço)|Volta para o diretório "home" (raiz) do usuário.|[[04:14](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=254)]|
|`ls`|Lista os arquivos e pastas no diretório atual.|[[04:16](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=256)]|
|`pwd`|Exibe o caminho completo do diretório de trabalho atual (print working directory).|[[04:21](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=261)]|
|`whoami`|Exibe o nome do usuário logado.|[[04:25](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=265)]|
|`mv [arquivo] [destino]`|Move arquivos.|[[04:31](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=271)]|
|`cp [arquivo] [destino]`|Copia arquivos.|[[04:36](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=276)]|
|`ditto [arquivo] [destino]`|Versão macOS do comando de cópia, mais robusto.|[[04:40](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=280)]|
|`df -h`|Exibe o espaço disponível no disco rígido em formato legível por humanos.|[[04:47](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=287)]|
|`nano [arquivo]`|Abre um editor de texto simples (Nano) para editar o arquivo no terminal.|[[04:52](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=292)]|
|`man [comando]`|Exibe o manual e a documentação detalhada de qualquer comando.|[[05:00](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=300)]|
|`open [arquivo]`|Abre um arquivo usando o aplicativo padrão do macOS.|[[05:08](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=308)]|
|`diff [arquivo1] [arquivo2]`|Compara as diferenças entre dois arquivos.|[[07:22](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=442)]|
|`curl [URL] > [destino]`|Baixa um arquivo da internet (URL) e o salva no caminho de destino.|[[07:28](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=448)]|

### Comandos de Rede e Processos

|Comando|Descrição|Timestamp|
|---|---|---|
|`ping [website]`|Testa a conectividade com um website/servidor e mede o tempo de resposta.|[[05:17](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=317)]|
|`ifconfig`|Exibe as configurações de rede, incluindo o endereço IP do computador.|[[05:25](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=325)]|
|`|grep [filtro]`|Filtra o resultado de um comando para mostrar apenas as linhas que contêm o filtro.|
|`|awk [expressão]`|Ferramenta avançada para processar e manipular dados em texto (usada para extrair IPs).|
|`traceroute [website]`|Mostra o caminho (todos os "saltos" de roteadores) percorrido até um website.|[[05:52](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=352)]|
|`dig [website]`|Faz uma consulta direta ao DNS de um website.|[[06:05](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=365)]|
|`ps -ax`|Lista todos os processos em execução no sistema.|[[06:17](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=377)]|
|`top`|Exibe os processos em tempo real, ordenados pelo uso da CPU.|[[06:21](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=381)]|
|`top -o rsize`|Exibe os processos em tempo real, ordenados pelo uso da memória.|[[06:26](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=386)]|
|`kill -9 [Process ID]`|Encerra forçadamente um processo em execução.|[[06:32](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=392)]|
|`uptime`|Mostra há quanto tempo o sistema está ligado.|[[07:05](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=425)]|
|**Comandos de Flush DNS**|Sequência de comandos `sudo dscacheutil -flushcache` e `sudo killall -HUP mDNSResponder` para limpar o cache DNS.|[[07:11](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=431)]|

### Comandos de Shell e Outros

|Comando|Descrição|Timestamp|
|---|---|---|
|`which (cifrão)SHELL`|Mostra qual Shell (intérprete de comandos, ex: Zsh ou Bash) está sendo usado.|[[06:48](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=408)]|
|`bash`|Alterna o Shell para Bash.|[[06:55](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=415)]|
|`zsh`|Alterna o Shell para Zsh.|[[07:01](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=421)]|
|`qlmanage -p [arquivo]`|Exibe uma pré-visualização rápida de um arquivo (Quick Look).|[[07:16](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=436)]|
|`curl wttr.in/[local]`|Exibe a previsão do tempo no terminal.|[[07:38](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=458)]|
|`leave [hora]`|Define um alarme que notifica o usuário na hora definida para "sair" do terminal.|[[07:43](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=463)]|
|`history`|Exibe o histórico de todos os comandos digitados.|[[07:53](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=473)]|
|`sudo spctl --master-disable`|Desativa o Gatekeeper (recurso de segurança do macOS que impede a execução de software não verificado).|[[07:59](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=479)]|
|`python3 -m http.server`|Inicia um pequeno servidor web local na porta 8000 (para compartilhamento de arquivos).|[[09:55](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=595)]|

### Comandos com Homebrew (`brew`)

(É necessário instalar o Homebrew antes de usar estes comandos)

| Comando                 | Descrição                                                                                    | Timestamp                                                   |
| ----------------------- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| `brew install [pacote]` | Instala um pacote/aplicativo usando o gerenciador de pacotes Homebrew.                       | [[08:47](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=527)] |
| `cmatrix`               | Executa a animação "Matrix" no terminal (requer `brew install cmatrix`).                     | [[08:52](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=532)] |
| `ascii-aquarium`        | Executa um aquário animado em arte ASCII no terminal (requer `brew install ascii-aquarium`). | [[09:04](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=544)] |
| `toilet [texto]`        | Transforma texto em arte ASCII estilizada (requer `brew install toilet`).                    | [[09:12](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=552)] |
| `tetris`                | Permite jogar Tetris no terminal (requer `brew install samtay-tui-tetris`).                  | [[09:37](http://www.youtube.com/watch?v=qOrlYzqXPa8&t=577)] |

O vídeo completo está disponível em: [http://www.youtube.com/watch?v=qOrlYzqXPa8](http://www.youtube.com/watch?v=qOrlYzqXPa8)


![|0x0](https://www.gstatic.com/images/branding/productlogos/youtube/v9/192px.svg)
#mac #tech #vídeos 