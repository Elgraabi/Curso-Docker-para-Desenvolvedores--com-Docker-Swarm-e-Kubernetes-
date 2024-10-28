# Container vs. Imagem

### O Que é uma Imagem?

Uma **Imagem** é um pacote de software imutável que contém tudo o que é necessário para executar uma aplicação — código, bibliotecas, dependências, variáveis de ambiente e configurações. Ela é como uma fotografia instantânea de um sistema de arquivos em um determinado estado e serve como "modelo" para criar containers. As imagens são armazenadas em registries, como o Docker Hub, e podem ser compartilhadas e reutilizadas.

- **Imutabilidade**: Uma vez criada, a imagem não é alterada. Qualquer mudança resulta em uma nova imagem.
- **Camadas**: As imagens são formadas por camadas empilhadas, onde cada comando no Dockerfile (utilizado para criar a imagem) adiciona uma nova camada. Isso permite que diferentes imagens compartilhem camadas em comum, economizando espaço.

### O Que é um Container?

Um **Container** é uma instância de uma imagem em execução. É a "versão viva" de uma imagem, com seu próprio sistema de arquivos e um ambiente isolado que simula um sistema operacional. Quando executamos uma imagem, ela se transforma em um container ativo, onde a aplicação pode rodar e processar dados.

- **Isolamento**: Cada container é executado de forma isolada e independente de outros containers.
- **Estado e Persistência**: Containers são temporários por natureza. Quando paramos um container, ele mantém o estado em que estava, mas se o excluirmos, tudo dentro dele é removido. Dados podem ser persistidos usando volumes.

### Diferenças Principais

| Aspecto          | Imagem                                                                 | Container                                                        |
|------------------|------------------------------------------------------------------------|------------------------------------------------------------------|
| **Definição**    | Modelo de software imutável, pronto para ser executado.               | Instância de uma imagem em execução.                             |
| **Mutabilidade** | Imutável — as alterações criam uma nova imagem.                       | Mutável enquanto está em execução; pode gerar novos dados.       |
| **Propósito**    | Armazena o estado da aplicação e suas dependências.                   | Executa a aplicação e processa dados em tempo real.              |
| **Persistência** | Permanente; salvo no registry (como Docker Hub).                      | Temporário, a menos que salvo em um volume ou commitado.         |
| **Uso**          | Usado para criar containers.                                          | Usado para executar uma aplicação ou serviço isoladamente.       |

### Exemplo Prático

1. **Criar uma Imagem**: Escrevemos um `Dockerfile` com as instruções de como construir uma aplicação e, com isso, geramos uma imagem.
   ```bash
   docker build -t minha-imagem .
   ```

2. **Executar um Container**: Usamos a imagem criada para rodar um container:
   ```bash
   docker run minha-imagem
   ```

3. **Diferença de Comportamento**: Se fizermos modificações no container durante sua execução, essas mudanças não afetam a imagem original. Para salvar o estado do container como uma nova imagem, usamos:
   ```bash
   docker commit <container_id> nova-imagem
   ```

### Conclusão

Em resumo, uma **imagem** é o "modelo" de uma aplicação, enquanto um **container** é uma instância em execução desse modelo. Imagens são estáticas e podem ser reutilizadas, enquanto containers são dinâmicos, permitindo que uma aplicação seja executada e interaja com dados em tempo real.
```

Essa explicação diferencia bem imagem e container, destacando os usos, características e um exemplo prático para melhor compreensão.