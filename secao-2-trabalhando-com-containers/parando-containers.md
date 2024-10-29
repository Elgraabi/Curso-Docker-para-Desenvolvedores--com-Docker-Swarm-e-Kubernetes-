Para parar containers no Docker, você pode usar o comando `docker stop`, que envia um sinal para o container, permitindo que ele finalize seus processos com segurança.

### Parando um Container Específico

Para parar um container específico, execute:

```bash
docker stop <container_id>
```

- **<container_id>**: ID ou nome do container que você deseja parar. 

Você pode obter o ID do container com o comando:

```bash
docker ps
```

Esse comando lista todos os containers em execução.

### Parando Vários Containers

Para parar vários containers ao mesmo tempo, liste todos os IDs ou nomes, separados por espaços:

```bash
docker stop <container_id_1> <container_id_2> <container_id_3>
```

### Parando Todos os Containers em Execução

Para parar todos os containers de uma só vez, use:

```bash
docker stop $(docker ps -q)
```

- **docker ps -q**: Lista apenas os IDs dos containers em execução, que são passados para o comando `docker stop`.

Esses comandos ajudam a encerrar containers ativos e liberar recursos no sistema.