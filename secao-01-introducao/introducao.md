# Curso de Modelagem de Domínio com UML e Java: Seção Docker

## 1. Conceitos Básicos de Containers e Docker

- **Containers:** Um container é um ambiente isolado que inclui tudo o que uma aplicação precisa para rodar (bibliotecas, dependências, etc.), garantindo consistência em qualquer sistema operacional que suporte Docker.
- **Docker:** Docker é uma plataforma que facilita a criação, o gerenciamento e a execução de containers, permitindo que os desenvolvedores empacotem suas aplicações de forma consistente e eficiente.

### Diferenças entre Containers e Máquinas Virtuais:
- **Containers:** São leves e compartilham o kernel do sistema operacional, mas possuem processos, rede e sistema de arquivos isolados.
- **Máquinas Virtuais (VMs):** São mais pesadas, pois emulam um sistema operacional completo, incluindo o kernel, e cada VM tem sua própria cópia do sistema operacional.

**Vantagens de usar Docker:**
- Portabilidade entre diferentes ambientes (desenvolvimento, teste e produção).
- Uso eficiente de recursos do sistema.
- Facilidade de gerenciamento e distribuição de aplicações.

---

## 2. Instalação do Docker

- Para instalar o Docker, siga os passos específicos para o seu sistema operacional:
  - **Linux:** Execute os comandos de instalação via terminal.
  - **Windows:** Utilize o Docker Desktop.
  - **Mac:** Baixe e instale o Docker Desktop.

Após a instalação, verifique se o Docker está funcionando corretamente executando o comando:

```bash
docker --version
```

Este comando deve retornar a versão instalada do Docker.

---

## 3. Criação de um Container Docker

Para criar e rodar um container, siga os passos abaixo:

1. **Buscar uma imagem no Docker Hub:**
   O Docker Hub é um repositório de imagens públicas de containers.

   Exemplo:
   ```bash
   docker pull openjdk:17
   ```

2. **Rodar um container a partir de uma imagem:**
   ```bash
   docker run -d --name meu-container -p 8080:8080 openjdk:17
   ```

   - `-d`: roda o container em modo "desanexado" (em segundo plano).
   - `--name`: define um nome para o container.
   - `-p`: mapeia a porta do container para a porta do host.

3. **Comandos úteis para gerenciamento de containers:**
   - `docker ps`: lista os containers em execução.
   - `docker stop [nome ou ID do container]`: para a execução de um container.
   - `docker rm [nome ou ID do container]`: remove um container.

---

## 4. Trabalhando com Dockerfile

O **Dockerfile** é um arquivo de texto simples que contém instruções para a criação de uma imagem Docker personalizada.

Exemplo de um Dockerfile básico para uma aplicação Java:

```Dockerfile
# Usa uma imagem base do OpenJDK
FROM openjdk:17

# Define o diretório de trabalho dentro do container
WORKDIR /app

# Copia todos os arquivos do diretório atual para o diretório de trabalho
COPY . .

# Compila o projeto
RUN ./mvnw clean install

# Define o comando que será executado quando o container iniciar
CMD ["java", "-jar", "target/app.jar"]
```

Comandos para construir e rodar uma imagem customizada:
1. **Construir a imagem:**
   ```bash
   docker build -t minha-app .
   ```

2. **Rodar a imagem:**
   ```bash
   docker run -d -p 8080:8080 minha-app
   ```

---

## 5. Docker Compose

O **Docker Compose** é uma ferramenta para definir e gerenciar múltiplos containers de forma simples, utilizando um arquivo `docker-compose.yml`.

Exemplo de um arquivo Docker Compose para uma aplicação Java e PostgreSQL:

```yaml
version: '3'
services:
  app:
    image: minha-app:latest
    ports:
      - "8080:8080"
    depends_on:
      - db
  db:
    image: postgres:latest
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
      POSTGRES_DB: meu_banco
```

- **services:** Define os serviços que serão gerenciados pelo Docker Compose.
- **app:** Serviço da aplicação Java.
- **db:** Serviço do banco de dados PostgreSQL.

Comando para iniciar todos os containers definidos no arquivo `docker-compose.yml`:
```bash
docker-compose up -d
```

---

## 6. Volumes e Persistência de Dados

Os **volumes** permitem que os dados persistam mesmo que o container seja removido ou reiniciado.

1. **Criar um volume:**
   ```bash
   docker volume create meu-volume
   ```

2. **Usar um volume em um container:**
   ```bash
   docker run -d -p 8080:8080 -v meu-volume:/data minha-app
   ```

Neste exemplo, o volume `meu-volume` será montado no diretório `/data` dentro do container, garantindo que os dados armazenados ali persistam entre execuções do container.

3. **Verificar os volumes:**
   ```bash
   docker volume ls
   ```

---

## 7. Exemplo Prático com Docker

Durante o curso, você implementará uma aplicação Java com Spring Boot e PostgreSQL, utilizando Docker para containerizar os serviços.

### Etapas:
1. **Criar o Dockerfile para a aplicação Java.**
2. **Configurar o Docker Compose para a aplicação e o banco de dados.**
3. **Executar a aplicação localmente usando Docker.**

```yaml
version: '3'
services:
  app:
    build: .
    ports:
      - "8080:8080"
    depends_on:
      - db
  db:
    image: postgres:15
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
      POSTGRES_DB: app_db
    volumes:
      - db-data:/var/lib/postgresql/data
volumes:
  db-data:
```

Esses passos ajudam a consolidar o conhecimento sobre a utilização de Docker no desenvolvimento de aplicações modernas.
```

Esse markdown cobre todos os tópicos da seção sobre Docker no curso. Se precisar de mais detalhes ou ajustes, é só avisar!
