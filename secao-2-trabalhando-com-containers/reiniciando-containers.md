Para reiniciar containers no Docker, você pode usar o comando `docker restart`. Esse comando para o container e o inicia novamente em um único passo.

### Reiniciando um Container Específico

Para reiniciar um container específico, execute:

```bash
docker restart <container_id>
```

- **<container_id>**: ID ou nome do container que você deseja reiniciar.

Obtenha o ID do container com o comando:

```bash
docker ps -a
```

Esse comando lista todos os containers, incluindo os que estão parados.

### Reiniciando Vários Containers

Para reiniciar vários containers ao mesmo tempo, liste todos os IDs ou nomes separados por espaços:

```bash
docker restart <container_id_1> <container_id_2> <container_id_3>
```

### Reiniciando Todos os Containers

Para reiniciar todos os containers em execução, use:

```bash
docker restart $(docker ps -q)
```

- **docker ps -q**: Retorna os IDs dos containers em execução, passando-os para o comando `docker restart`. 

Esses comandos são úteis para reiniciar containers em casos de falha temporária ou de atualização.