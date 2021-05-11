# Repositório Docker, Ready To Go!

Repositório de desenvolvimento pronto para uso baseado em Docker. Ideal para aqueles que estão tendo a sua primeira experiência de uso do Docker **(dê adeus ao Xampp/Wampp!)**. Há duas opções disponíveis: uma simples (apenas com Apache + PHP 7.4) e outra completa (contendo estrutura de banco de dados), veja os exemplos abaixo.

## padrão

**docker-compose.yml** (simples, apenas Apache + PHP)

- Ubuntu 16
- Apache
- PHP 7.4

## completo:

**docker-compose-mysql.yml** (para aplicações que necessitam de banco de dados)

- Ubuntu 16
- Apache
- PHP 7.4
- MariaDB 10.X
- PHPMyAdmin

---

## Como Utilizar:

**Para utilizar, logicamente você precisa ter o Docker instalado em sua máquina. Em seguida, siga o procedimento abaixo:**

**1. Clone o repositório:**

- git clone git@github.com:ajmeireles/docker.git docker
- cd docker

**2. Selecione o arquivo a ser utilizado:**

- cp docker/docker-compose.yml docker-compose.yml

**ou**

- cp docker/docker-compose-mysql.yml docker-compose.yml

**3. Copie o .env que define variáveis do ambiente:**

- cp docker/env-example .env

**4. Rode o container:**

- docker-compose up -d


**5. Use a vontade:**

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