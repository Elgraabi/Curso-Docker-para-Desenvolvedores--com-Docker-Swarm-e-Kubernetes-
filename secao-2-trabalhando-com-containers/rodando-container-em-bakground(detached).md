Para rodar um container no modo "detached" (em segundo plano), você pode usar o comando `docker run` com a opção `-d`. Isso permite que o container seja executado em segundo plano, sem ocupar o terminal.

### Exemplo de Comando

```bash
docker run -d <nome_da_imagem>
```

- **-d**: Inicia o container em modo "detached" (background), mantendo-o executando no plano de fundo.

### Exemplo Completo

Para rodar um container da imagem `nginx` no modo "detached":

```bash
docker run -d nginx
```

Este comando executa o Nginx como um serviço em segundo plano, permitindo que você continue usando o terminal para outros comandos.

### Verificando Containers em Execução

Depois de rodar o container, você pode verificar se ele está ativo com o comando:

```bash
docker ps
```

Esse comando lista todos os containers ativos, mostrando o ID, nome da imagem, status, e tempo de execução.

### Parando o Container

Para parar o container, use o comando:

```bash
docker stop <container_id>
```

Substitua `<container_id>` pelo ID ou nome do container que você quer parar.