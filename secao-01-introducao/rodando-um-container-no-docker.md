# Rodando um Container no Docker

Este guia mostra como rodar um container básico usando o Docker.

## Pré-requisitos

Antes de começar, verifique se você tem o Docker instalado. Você pode verificar executando o seguinte comando no terminal:

```bash
docker --version
```

## Passo 1: Abrir o Terminal

Abra o terminal (Prompt de Comando ou PowerShell no Windows, Terminal no macOS ou Linux).

## Passo 2: Executar um Container

Para rodar um container básico, utilizaremos a imagem `hello-world`, que é uma imagem de teste do Docker. Execute o seguinte comando:

```bash
docker run hello-world
```

### O que Este Comando Faz

- **`docker run`**: Este comando é usado para iniciar um novo container.
- **`hello-world`**: Este é o nome da imagem que o Docker irá baixar do Docker Hub, se não estiver disponível localmente.

## Passo 3: Verificando a Saída

Após executar o comando, você deve ver uma saída similar a esta:

```
Hello from Docker!
This message shows that your installation appears to be working correctly.
```

### O que Fazer a Seguir

Se você viu essa mensagem, significa que o Docker foi instalado corretamente e o container foi executado com sucesso!

## Passo 4: Listar Containers em Execução

Para verificar quais containers estão em execução, use o seguinte comando:

```bash
docker ps
```

## Passo 5: Listar Todos os Containers (Ativos e Parados)

Se você deseja ver todos os containers, incluindo os que estão parados, use:

```bash
docker ps -a
```

## Passo 6: Parar um Container

Para parar um container que está em execução, use:

```bash
docker stop <CONTAINER_ID>
```

Substitua `<CONTAINER_ID>` pelo ID do container que você deseja parar, que pode ser encontrado na saída do comando `docker ps`.

## Passo 7: Remover um Container

Para remover um container parado, use:

```bash
docker rm <CONTAINER_ID>
```

## Conclusão

Neste guia, você aprendeu a rodar um container básico no Docker usando a imagem `hello-world`. Você também aprendeu a listar, parar e remover containers. Continue explorando outras imagens disponíveis no Docker Hub para experimentar mais com o Docker!
```

### Como Usar este Documento

- Você pode copiar e colar este texto em um arquivo `.md` e salvá-lo, por exemplo, como `docker-rodando-container.md`.
- Para visualizar o arquivo, você pode usar um editor de Markdown ou um visualizador de texto que suporte a formatação Markdown.
