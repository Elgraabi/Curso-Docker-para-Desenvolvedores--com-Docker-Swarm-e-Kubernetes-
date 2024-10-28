# Rodando um Container com Docker

Para executar um container no Docker, usamos o comando `docker run`, que cria uma instância de uma imagem e a executa em um ambiente isolado. Abaixo estão os passos e exemplos para rodar um container.

## Comando Básico para Rodar um Container

A sintaxe básica para rodar um container é:

```bash
docker run [opções] imagem [comando]
```

- **imagem**: Nome ou ID da imagem que queremos executar.
- **opções**: Configurações opcionais, como portas, volumes e variáveis de ambiente.
- **comando**: (Opcional) Um comando específico para executar dentro do container.

## Exemplo Simples: Rodando um Container com `hello-world`

Vamos executar um container usando a imagem `hello-world`, que exibe uma mensagem simples.

```bash
docker run hello-world
```

Se o Docker não encontrar a imagem `hello-world` localmente, ele a baixa do Docker Hub e exibe a mensagem de confirmação, indicando que o container rodou com sucesso.

## Rodando um Container em Segundo Plano (`-d`)

Usamos o parâmetro `-d` (detached mode) para executar o container em segundo plano:

```bash
docker run -d nginx
```

Esse comando inicia um container com a imagem `nginx` em segundo plano, tornando-o ideal para aplicações de longo prazo, como servidores web.

## Expondo Portas (`-p`)

Para acessar uma aplicação em um container, precisamos mapear uma porta do host para uma porta do container:

```bash
docker run -d -p 8080:80 nginx
```

- **8080:80**: Mapeia a porta 80 do container para a porta 8080 do host. Agora, a aplicação é acessível em `localhost:8080`.

## Nomeando o Container (`--name`)

Para facilitar a identificação, podemos nomear o container usando `--name`:

```bash
docker run -d --name meu_nginx -p 8080:80 nginx
```

Agora, o container pode ser identificado pelo nome `meu_nginx`.

## Verificando Containers em Execução

Para listar todos os containers em execução, use:

```bash
docker ps
```

Para listar todos os containers (inclusive os parados), use:

```bash
docker ps -a
```

## Parando e Removendo Containers

- **Parar**: Para parar um container em execução, use o comando `docker stop` seguido pelo nome ou ID do container:
  ```bash
  docker stop meu_nginx
  ```

- **Remover**: Para remover um container parado, use `docker rm`:
  ```bash
  docker rm meu_nginx
  ```

## Comando Completo com Vários Parâmetros

Um exemplo completo para rodar um container com nome, mapeamento de portas e em segundo plano:

```bash
docker run -d --name meu_app -p 8080:80 -e ENV_VAR=valor minha-imagem
```

- **-e ENV_VAR=valor**: Define uma variável de ambiente dentro do container.
- **minha-imagem**: Nome da imagem que o container vai usar.

## Conclusão

Rodar um container com Docker é simples e altamente configurável. Dependendo das necessidades do projeto, podemos escolher diferentes opções para definir portas, nomes, variáveis de ambiente, e muito mais.
```