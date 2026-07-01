
Isso acontece porque **`Ctrl + L` não executa exatamente o comando `clear`**. Ele usa uma função interna do shell chamada “clear screen”, que em alguns terminais do Kali só “empurra” a tela para baixo, deixando os comandos antigos visíveis no topo.

Para fazer o **`Ctrl + L` executar o `clear` de verdade**, rode este comando:

```bash
bindkey -s '^L' $'clear\n'
```

Depois disso, aperte:

```text
Ctrl + L
```

Agora ele deve executar como se você tivesse digitado:

```bash
clear
```

Para deixar isso permanente, adicione no final do arquivo `~/.zshrc`:

```bash
echo "bindkey -s '^L' \$'clear\n'" >> ~/.zshrc
source ~/.zshrc
```

Resumo:

```text
Ctrl + L normal = só limpa/rola visualmente a tela
bindkey com clear = faz Ctrl + L rodar o comando clear real
```

Também dá para usar diretamente:

```bash
clear
```

ou, para limpar até o scrollback em muitos terminais:

```bash
clear && printf '\e[3J'
```