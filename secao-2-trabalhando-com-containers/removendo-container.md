Para remover um container no Docker, você pode usar o comando `docker rm`. Esse comando exclui o container permanentemente.

### Removendo um Container Específico

Para remover um container específico, execute:

```bash
docker rm <container_id ou nome_do_container>
```

Substitua `<container_id ou nome_do_container>` pelo ID ou nome do container que deseja remover.

### Exemplo Completo

Para remover um container chamado `meu_nginx`, use:

```bash
docker rm meu_nginx
```

### Removendo Vários Containers

Para remover múltiplos containers ao mesmo tempo, liste os IDs ou nomes separados por espaço:

```bash
docker rm <container_id_1> <container_id_2> <container_id_3>
```

### Removendo Todos os Containers Parados

Para remover todos os containers que estão parados, use o comando:

```bash
docker rm $(docker ps -a -q)
```

- **docker ps -a -q**: Retorna o ID de todos os containers, que são então passados para `docker rm`.

### Forçando a Remoção de Containers em Execução

Para forçar a remoção de um container em execução (sem parar o processo de forma adequada), adicione a opção `-f`:

```bash
docker rm -f <container_id ou nome_do_container>
```

> **Atenção**: Usar `-f` pode causar perda de dados ou corrupção de processos se o container não for interrompido corretamente antes de ser removido.