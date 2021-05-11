FROM 1and1internet/ubuntu-16-apache-php-7.2

WORKDIR /var/www/html

RUN apt-get update -y \
	&& apt-get install software-properties-common -y \
	&& apt install -y unzip \
	&& apt install net-tools -y \
	&& apt-get install nano -y

RUN add-apt-repository ppa:ondrej/php -y \
	&& add-apt-repository ppa:ondrej/apache2 -y \
	&& apt-get update -y \
	&& apt-get install php7.4 -y \
	&& apt-get install php7.4-curl php7.4-pdo-mysql php7.4-mbstring php7.4-intl php7.4-xml php7.4-zip -y

RUN a2dismod php7.2 \
	&& a2enmod php7.4

ENV DOCUMENT_ROOT ${DOCUMENT_ROOT}

COPY apache2.conf /etc/apache2/apache2.conf
COPY ports.conf /etc/apache2/ports.conf
COPY sites-available/000-default.conf /etc/apache2/sites-available/000-default.conf
COPY ssl/apache-selfsigned.crt /etc/ssl/certs/apache-selfsigned.crt
COPY ssl/apache-selfsigned.key /etc/ssl/private/apache-selfsigned.key

WORKDIR /var/www/html