---
{"dg-publish":true,"permalink":"/pipes-no-i-term2/","dg-note-properties":{}}
---


Sim, é perfeitamente possível. O `pipes.sh` é um script em Bash e ele aceita **flags** (argumentos) para customizar quase tudo, desde a velocidade até o tipo de caractere usado para as linhas.

Para o **iTerm2**, onde a renderização é muito nítida, uma velocidade menor cria aquele efeito hipnótico de "construção de circuitos" que combina muito com a estética cyberpunk.

## 🐢 Como reduzir a velocidade

O comando padrão que você rodou via `curl` não permite passar argumentos facilmente. O ideal é baixar o script ou rodá-lo passando a flag `-f` (frame delay).

Tente este comando (ajuste o número após o `-f` para mais lentidão):

Bash

```
# O padrão é 0.05. Tente 0.2 ou 0.5 para algo bem calmo.
bash <(curl -sSL https://raw.githubusercontent.com/pipeseroni/pipes.sh/master/pipes.sh) -f 0.2
```

## 🎛️ Outras customizações para o iTerm2

Já que você quer a estética de "terminais antigos", aqui estão as melhores combinações de flags para o `pipes.sh`:

|**Flag**|**Função**|**Sugestão para o iTerm**|
|---|---|---|
|`-p`|Número de canos|`-p 1` (Fica mais solitário e minimalista)|
|`-t`|Tipo de cano|`-t 1` (Usa caracteres de caixa fina, muito retrô)|
|`-c`|Cores|`-c 2` (Verde Matrix) ou `-c 0` (Branco puro)|
|`-R`|Modo Randômico|`-R` (Muda as cores e estilos conforme desenha)|

**Exemplo de um "Screensaver Minimalista Hacker":**

Bash

```
# 1 cano, verde, lento, usando linhas finas clássicas
bash <(curl -sSL https://raw.githubusercontent.com/pipeseroni/pipes.sh/master/pipes.sh) -p 1 -c 2 -t 1 -f 0.3
```

---

## 💡 Dica de "Poder do iTerm": Transparência

Para esse efeito de "linhas flutuando" ficar perfeito:

1. Pressione `Cmd + i` no iTerm2.
    
2. Vá em **Appearance**.
    
3. Aumente um pouco a **Transparency** e coloque um pouco de **Blur**.
    

Isso fará com que as linhas do `pipes` pareçam projetadas em um vidro, especialmente se você estiver usando cores neon contra o fundo escuro.

**Gostaria que eu criasse um atalho (alias) no seu sistema para que você só precise digitar `matrix` ou `pipes` para abrir essa versão lenta e personalizada?**