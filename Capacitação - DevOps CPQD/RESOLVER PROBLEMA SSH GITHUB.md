
## Para resolver usando SSH

Faça nessa ordem:

### 1. Ver se você já tem chave SSH

```
ls -al ~/.ssh
```

Se aparecer algo como:

```
id_ed25519id_ed25519.pub
```

você já tem chave.

Se **não aparecer**, crie uma:

```
ssh-keygen -t ed25519 -C "seu-email-do-github"
```

Pode apertar **Enter** em tudo.