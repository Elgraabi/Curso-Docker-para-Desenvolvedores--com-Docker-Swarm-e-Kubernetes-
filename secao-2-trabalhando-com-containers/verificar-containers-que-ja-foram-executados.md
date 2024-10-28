# Verificando Containers que Já Foram Executados no Docker

Para listar e verificar os containers que foram executados (incluindo aqueles que já foram parados), usamos o comando `docker ps` com a opção `-a`.

## Comando Básico

```bash
docker ps -a
```

- O comando `docker ps` lista apenas os containers ativos (em execução).
- A opção `-a` lista todos os containers, inclusive os que foram parados.

## Interpretação dos Resultados

Após rodar o comando, você verá uma tabela com informações como:

- **CONTAINER ID**: ID único do container.
- **IMAGE**: Imagem utilizada para criar o container.
- **COMMAND**: Comando que foi executado no container.
- **CREATED**: Tempo desde a criação do container.
- **STATUS**: Estado atual do container, que pode ser:
  - `Up` – container ativo (em execução).
  - `Exited` – container parado.
- **PORTS**: Portas mapeadas para o container.
- **NAMES**: Nome do container.

## Exemplo de Uso

```bash
$ docker ps -a
```

### Saída Esperada

```plaintext
CONTAINER ID   IMAGE         COMMAND             CREATED         STATUS                     PORTS                    NAMES
c145c751d116   nginx         "nginx -g 'daemon…" 5 minutes ago   Exited (0) 2 minutes ago                            my_nginx
d211f485f2dd   ubuntu        "/bin/bash"         3 hours ago     Exited (0) 1 hour ago                               my_ubuntu
3a5c9d8b58b1   hello-world   "/hello"            5 hours ago     Exited (0) 5 hours ago                              hello
```

## Outros Comandos Úteis

- **Remover Containers Parados**:
  ```bash
  docker rm $(docker ps -a -q)
  ```

- **Exibir Somente IDs dos Containers**:
  ```bash
  docker ps -a -q
  ```

Esses comandos ajudam a monitorar e gerenciar o histórico de containers executados no Docker.
```

