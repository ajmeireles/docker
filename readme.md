# Servidor Docker

Ambiente de desenvolvimento local baseaedo em Docker. Todos os ``compose`` disponíveis utilizam Ubuntu 16 contendo as seguintes opções disponíveis:

## padrão

**docker-compose.yml**

- Apache
- PHP 7.4

## completo:

**docker-compose-full.yml** (para aplicações que querem banco de dados)

- Apache
- PHP 7.4
- MariaDB 10.X
- PHPMyAdmin

---

## Como Utilizar:

**1. Selecione o arquivo a ser utilizado:**

- cp docker/docker-compose.yml docker-compose.yml

**ou**

- cp docker/docker-compose-full.yml docker-compose.yml

**2. Copie o .env que define variáveis do ambiente:**

- cp docker/env-example .env

**3. Rode o container:**

- docker-compose up -d