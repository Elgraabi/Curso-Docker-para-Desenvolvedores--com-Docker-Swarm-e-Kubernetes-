# O que é Docker?

O **Docker** é uma plataforma de código aberto que permite automatizar o processo de empacotamento, distribuição e execução de aplicações em containers. Ele facilita o desenvolvimento, a distribuição e a execução de software de maneira isolada, garantindo que o código funcione de forma consistente em qualquer ambiente.

## Por que usar Docker?

- **Portabilidade:** Com o Docker, as aplicações podem ser executadas de forma consistente em qualquer lugar, seja no ambiente de desenvolvimento local ou em servidores de produção.
- **Isolamento:** Cada container tem seu próprio ambiente isolado, incluindo bibliotecas, dependências e configurações, sem interferir com outros containers.
- **Eficiência:** Containers são mais leves que máquinas virtuais, pois compartilham o mesmo kernel do sistema operacional, economizando recursos de hardware.
- **Velocidade:** Docker permite iniciar e parar containers rapidamente, facilitando testes e iteração no desenvolvimento de software.

## Como funciona o Docker?

Docker utiliza a tecnologia de **containers**, que são como pequenas máquinas virtuais leves. Cada container é uma instância isolada de uma aplicação, rodando com todas as dependências necessárias, mas compartilhando o kernel do sistema operacional.

A principal unidade de trabalho no Docker é a **imagem**, que é um pacote com o código da aplicação e todos os recursos que ela precisa. Os containers são instâncias executáveis dessas imagens.

### Principais componentes do Docker:
- **Imagens:** São pacotes prontos para rodar uma aplicação. Elas contêm o sistema de arquivos, dependências e bibliotecas da aplicação.
- **Containers:** São instâncias em execução das imagens. Cada container é isolado e executa o código da aplicação com suas dependências.
- **Docker Hub:** Um repositório público de imagens, onde desenvolvedores podem publicar e compartilhar suas imagens Docker.

## Exemplo de uso

Aqui está um exemplo básico de como usar Docker para rodar uma aplicação Java:

1. Baixar uma imagem base do OpenJDK:
   ```bash
   docker pull openjdk:17
   ```

2. Criar e executar um container baseado nessa imagem:
   ```bash
   docker run -it openjdk:17 java -version
   ```

Este comando roda um container com o OpenJDK e imprime a versão do Java, mostrando como o Docker facilita a execução de aplicações em ambientes isolados.

```
