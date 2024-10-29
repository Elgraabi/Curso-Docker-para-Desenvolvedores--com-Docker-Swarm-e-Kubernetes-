Para acessar os logs de um container no Docker, você pode usar o comando `docker logs`, que exibe as saídas geradas pelo container em execução.

### Exemplo de Comando

```bash
docker logs <container_id ou nome_do_container>
```

### Principais Opções

- **-f**: Segue (continua exibindo) os logs em tempo real, útil para monitorar o container à medida que ele gera novas saídas.

  ```bash
  docker logs -f <container_id ou nome_do_container>
  ```

- **--tail**: Limita a quantidade de linhas exibidas, mostrando apenas as mais recentes. Exemplo para exibir as últimas 50 linhas:

  ```bash
  docker logs --tail 50 <container_id ou nome_do_container>
  ```

- **-t**: Exibe os logs com carimbos de data e hora, indicando quando cada linha de log foi gerada.

  ```bash
  docker logs -t <container_id ou nome_do_container>
  ```

### Exemplo Completo

Para acessar os logs de um container chamado `meu_nginx`, com as últimas 100 linhas em tempo real e com timestamps:

```bash
docker logs -f --tail 100 -t meu_nginx
```

Essas opções são úteis para monitorar o comportamento de containers e diagnosticar problemas.