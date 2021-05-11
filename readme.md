# Servidor Docker

Ambiente de desenvolvimento local baseado em Docker. Todos os ``compose`` disponíveis utilizam Ubuntu 16 contendo as seguintes opções disponíveis:

## padrão

**docker-compose.yml** (simples, apenas Apache + PHP)

- Apache
- PHP 7.4

## completo:

**docker-compose-mysql.yml** (para aplicações que necessita de banco de dados)

- Apache
- PHP 7.4
- MariaDB 10.X
- PHPMyAdmin

---

## Como Utilizar:

**1. Selecione o arquivo a ser utilizado:**

- cp docker/docker-compose.yml docker-compose.yml

**ou**

- cp docker/docker-compose-mysql.yml docker-compose.yml

**2. Copie o .env que define variáveis do ambiente:**

- cp docker/env-example .env

**3. Rode o container:**

- docker-compose up -d


**4. Use a vontade:**

- Acesse: http://localhost/ **(se a ``ApacheIncomingPort`` no .env foi mantida como 80)**

ou 

- Acesse: http://localhost:{porta}/ **(com a porta definida no ``ApacheIncomingPort`` no .env)**

---

## Observação:

A pasta raíz do Apache (documentroot) por padrão corresponde a raíz (onde o readme.md está). Você pode alterar essa configuração direcionando a pasta raíz para uma pasta da sua escolha, como: ``public`` ou ``public_html``. Para isso altere a configuração no ``.env`` em: **ApacheRootPath** para o nome da pasta, pore exemplo:

- ApacheRootPath=./public/ **(para public)**

ou

- ApacheRootPath=./public_html/ **(para public_html)**

**O padrão dessa configuração é: ``ApacheRootPath=./``**