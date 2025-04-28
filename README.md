# Desafio 03 Toshiro Shibakita

Este repositório contém a solução para o desafio proposto no Bootcamp **Santander - Linux para Iniciantes**. O objetivo do desafio é aplicar conceitos de microsserviços utilizando o **Docker** para criar e gerenciar contêineres, além de integrar o uso do MySQL como banco de dados.

## Descrição

O projeto demonstra como estruturar e configurar um ambiente de microsserviços utilizando o Docker. O foco está no provisionamento e gerenciamento de contêineres que executam serviços desenvolvidos em PHP e na configuração de um banco de dados MySQL para armazenar e gerenciar informações.

## Funcionalidades

- Configuração de contêineres Docker para serviços baseados em PHP.
- Configuração de um contêiner MySQL para o banco de dados.
- Integração entre o serviço PHP e o banco de dados MySQL.
- Estrutura de microsserviços modular e escalável.
- Scripts para criar, inicializar e gerenciar contêineres.

## Tecnologias Utilizadas

- **PHP**: Linguagem de programação usada nos serviços.
- **MySQL**: Banco de dados utilizado para persistência de dados.
- **Docker**: Plataforma para criar e gerenciar contêineres.
- **Docker Compose** (se aplicável): Ferramenta para orquestração de múltiplos contêineres.

## Requisitos

- **Docker** instalado na máquina host.
- **Docker Compose** (opcional, dependendo da configuração do projeto).
- Ambiente Linux ou compatível.

## Como Usar

### 1. Clone o Repositório

```bash
git clone https://github.com/brun0car1oso/desafio-dio-toshiro-shibakita
```

### 2. Acesse o Diretório do Projeto

```bash
cd desafio-dio-toshiro-shibakita
```

### 3. Configure o Banco de Dados

Certifique-se de que as credenciais do banco de dados MySQL estão configuradas corretamente no arquivo de ambiente (por exemplo: `.env`) ou no arquivo `docker-compose.yml`, caso esteja presente.

Exemplo de variáveis de ambiente para o MySQL:

```env
MYSQL_ROOT_PASSWORD=senha_root
MYSQL_DATABASE=nome_do_banco
MYSQL_USER=usuario
MYSQL_PASSWORD=senha_usuario
```

### 4. Construa e Inicialize os Contêineres

Caso o projeto inclua um arquivo `docker-compose.yml`:

```bash
docker-compose up -d
```

Se o arquivo `docker-compose.yml` não estiver presente, os contêineres podem ser construídos e iniciados manualmente:

1. Para o serviço PHP:
   ```bash
   docker build -t nome-do-servico .
   docker run -d -p 8080:80 nome-do-servico
   ```

2. Para o contêiner MySQL:
   ```bash
   docker run -d -p 3306:3306 --name mysql-container -e MYSQL_ROOT_PASSWORD=senha_root mysql:latest
   ```

### 5. Acesse o Serviço

Após inicializar os contêineres, o serviço estará disponível em `http://localhost:8080` (ou na porta configurada no Docker).

## Estrutura do Projeto

- **`Dockerfile`**: Arquivo com as instruções para criar a imagem Docker do serviço PHP.
- **Arquivos PHP**: Código fonte dos serviços desenvolvidos.
- **`docker-compose.yml`** (se presente): Orquestração dos contêineres.
- **Banco de Dados MySQL**: Configurado para persistência de dados.

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests com melhorias ou correções.

## Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
