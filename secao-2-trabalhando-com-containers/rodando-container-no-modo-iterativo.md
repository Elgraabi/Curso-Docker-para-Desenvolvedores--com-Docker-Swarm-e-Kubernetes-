# Rodando um Container no Modo Interativo com Docker

## Comando

Para rodar um container no modo interativo, use o seguinte comando:

```bash
docker run -it <nome_da_imagem> /bin/bash
```

- **-i**: Modo interativo (mantém o STDIN aberto).
- **-t**: Aloca um terminal TTY.

Exemplo com a imagem `ubuntu`:

```bash
docker run -it ubuntu /bin/bash
```

Esse comando iniciará um container com o sistema Ubuntu e abrirá um terminal para você interagir dentro do container.

## Exemplo de Uso

1. Execute o comando:

   ```bash
   docker run -it ubuntu /bin/bash
   ```

2. Agora você estará dentro do terminal do container Ubuntu. A partir daqui, é possível executar comandos normalmente, como:

   ```bash
   root@container_id:/# ls
   root@container_id:/# apt update
   ```

3. Para sair do terminal interativo e encerrar o container, digite `exit`.

## Observação

No exemplo acima, substitua `<nome_da_imagem>` pelo nome da imagem Docker que deseja usar e `/bin/bash` pelo comando desejado, caso queira um shell diferente ou executar scripts específicos.
```