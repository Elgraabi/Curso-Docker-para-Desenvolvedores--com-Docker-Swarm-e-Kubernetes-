Para definir um nome personalizado para um container, você pode usar a opção `--name` no comando `docker run`. Isso torna mais fácil identificar e gerenciar o container pelo nome, em vez de depender do ID gerado automaticamente.

### Exemplo de Comando

```bash
docker run -d --name <nome_do_container> <nome_da_imagem>
```

- **-d**: Roda o container no modo "detached" (em segundo plano).
- **--name**: Define um nome específico para o container.
- **<nome_da_imagem>**: Nome da imagem Docker que você quer usar para iniciar o container.

### Exemplo Completo

Para rodar um container do Nginx com o nome personalizado `meu_nginx`, use:

```bash
docker run -d --name meu_nginx nginx
```

### Verificando o Nome do Container

Depois de executar o comando, você pode listar todos os containers e ver o nome especificado com:

```bash
docker ps -a
```

A coluna **NAMES** mostrará o nome `meu_nginx` para o container Nginx que você acabou de criar. 

### Gerenciando Containers com Nome

- **Parar o container**:

  ```bash
  docker stop meu_nginx
  ```

- **Reiniciar o container**:

  ```bash
  docker restart meu_nginx
  ```

- **Remover o container**:

  ```bash
  docker rm meu_nginx
  ```

Usar um nome personalizado facilita o gerenciamento e a organização dos containers em projetos com múltiplos serviços.