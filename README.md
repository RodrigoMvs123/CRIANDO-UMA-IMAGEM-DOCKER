# CRIANDO-UMA-IMAGEM-DOCKER

## CRIANDO UMA IMAGEM DOCKER

- https://www.youtube.com/watch?v=qIGxp9k3b1w&list=PLwlq4XZ8aTmcfGervqxCU56DSiAqdIYnS
- https://www.php.net/
- https://raw.githubusercontent.com/RodrigoMvs123/CRIANDO-UMA-IMAGEM-DOCKER/main/README.md
- https://github.com/RodrigoMvs123/CRIANDO-UMA-IMAGEM-DOCKER/blame/main/README.md

---

## Docker Commands

    FROM ubuntu: 18.04
    ADD ./entrypoint /home/ubuntu
    COPY ./entrypoint /home/ubuntu
    RUN apt-get update && apt-get upgrade && apt-get install apache2 && apt-get clean
    CMD ["sh", "-c", "echo", "Hello Word" ]
    LABEL CREATOR="João Vitor"
    ENTRYPOINT [ "usr/bin/apache2clt", "-D", "FOREGROUND" ]
    ENV environment= "development" 
    USER ubuntu 
    WORKDIR /home/ubuntu/

---

## Dockerfile

    from ubuntu 
    LABEL MAINTAINER = "João Vitor"
    RUN ln -s /user/share/zoneinfo/America/São_Paulo/etc/localtime 

    RUN apt-get update && apt-get upgrade -y && apt-get install - apache2 php libapache2-mod-php && apt-get clean

    RUN apt-get install -y php-soap php-xml php-curl php-opcache php-gd php-sqlite3 php-mbstring 

    COPY ./website/index.php var/www/html 
    EXPOSE 8080:80
    WORKDIR /var/www/html
    ENTRYPOINT ["/user/sbin/apache2ctl", "-D", "FOREGROUND"]
