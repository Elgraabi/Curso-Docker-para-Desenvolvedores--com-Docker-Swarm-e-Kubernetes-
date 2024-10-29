Para expor uma porta de um container e permitir que ele seja acessado externamente, você pode usar a opção `-p` no comando `docker run`. Essa opção mapeia uma porta do seu host para uma porta do container.

### Exemplo de Comando

```bash
docker run -d -p <porta_host>:<porta_container> <nome_da_imagem>
```

- **-d**: Roda o container no modo "detached" (em segundo plano).
- **-p**: Define o mapeamento de portas no formato `porta_host:porta_container`.

### Exemplo Completo

Para rodar um container do Nginx, expondo a porta 80 do container na porta 8080 do host, você usaria:

```bash
docker run -d -p 8080:80 nginx
```

Isso significa que você pode acessar o serviço Nginx no navegador, digitando `http://localhost:8080`. O Docker redirecionará automaticamente o tráfego da porta 8080 do host para a porta 80 do container, onde o Nginx está ouvindo.

### Verificando o Mapeamento de Portas

Para confirmar que a porta está exposta, use o comando:

```bash
docker ps
```

Isso mostrará as portas mapeadas do container na coluna **PORTS**.

### Parando o Container

Para parar o container, use:

```bash
docker stop <container_id>
```

Esse comando para o container, liberando a porta no host para outros serviços.