# Como instalar "MinecraftPanel" en docker con portainer (ubuntu 20.04)

## Docker:

Docker Compose
```
version: '3.0'

services:
    apache:
        container_name: apache2
        image: ubuntu/apache2:2.4-20.04_beta
        networks:
          - nginx
        volumes:
            - ./data:/usr/local/apache2/htdocs
            - ./html:/var/www/html
            - ./php:/etc/php
        restart: always
        environment:
            - LETSENCRYPT_EMAIL=youremail@gmail.com
            - LETSENCRYPT_HOST=yourpage.com
            - VIRTUAL_HOST=yourpage.com
            - VIRTUAL_PROTO=http
        ports:
            - 25565:25565

networks:
    nginx:
        external: true

volumes:
    php:
        external: true
```


Después, una vez creado el contenedor entramos y accedemos a consola.

![image](https://user-images.githubusercontent.com/25081670/146308996-553bd2b6-a9f7-4554-8a16-fca77aa1c8ab.png)

Hacemos click en CONNECT

![image](https://user-images.githubusercontent.com/25081670/146309159-7bab7285-3059-4137-b94d-fd0ff0542b25.png)

## Java 21 (OpenJDK 21)

```
apt update
```
```
apt upgrade
```
```
apt install -y openjdk-21-jdk
```


Entrar en el contenedor y usar la consola desde dentro

```
docker-compose exec "nombre del contenedor" bash
```
```
docker-compose exec apache bash
```

## Panel de Minecraft Web

```
apt install wget
```
```
apt install unzip
```
nuevo
```
apt install apache2 php libapache2-mod-php default-jdk screen vim php-cli php-json gawk wget tar gzip git zip unzip pigz

```
antiguo
```
apt install -y apache2 php libapache2-mod-php default-jdk screen php-mbstring php-zip php-cli php-json gawk wget zip unzip
```
```
wget https://github.com/JhonDesayuna/MinecraftPanel/raw/main/McWebPanel.zip
```
```
unzip McWebPanel.zip
```
```
chmod -R 775 McWebPanel
```


## Cambiar Limite de Subida
```
/etc/php/7.0/apache2/php.ini
```
```
post_max_size = 1024M
```
```
upload_max_filesize = 1024M
```

## Mediante la Terminal

Crear dentro de "apache2" en el servidor, las siguientes carpetas

![image](https://github.com/JhonDesayuna/MinecraftPanel/assets/25081670/9537ecd5-d362-4c22-bf71-c8a1832506d6)



Añadir delante de los comandos lo siguiente

```
docker exec -it "id contenedor"
```
```
docker exec -it "id contenedor" apt install -y openjdk-17-jdk
```

## Bibliografia:

`https://hub.docker.com/r/ubuntu/apache2`

`https://github.com/Konata400/McWebPanel`
