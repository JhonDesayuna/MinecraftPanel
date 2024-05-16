# Como instalar "MinecraftPanel" en docker con portainer (ubuntu 20.04)

## Docker:

Primero instalamos apache2 en docker

```
sudo docker run -d --name McWebPanel -e TZ=UTC -p 8081:80 -p 25565:25565 ubuntu/apache2:2.4-20.04_beta
```

Con Docker Compose
```
services:
    apache:
        container_name: apache
        volumes:
            - '/home/ubuntu/apache/data:/usr/local/apache2/htdocs'
        restart: always
        networks:
          - nginx
        environment:
            - LETSENCRYPT_EMAIL=alejandrogongon@gmail.com
            - LETSENCRYPT_HOST=mcserver-jhonfast.duckdns.org
            - VIRTUAL_HOST=mcserver-jhonfast.duckdns.org
            - VIRTUAL_PROTO=http
        image: ubuntu/apache2:2.4-20.04_beta
        ports:
            - 25565:25565

networks:
  nginx:
    external: true
```

`-p 25565:25565` Puerto de minecraft

`-p 8081:80` Puerto de apache2

Después, una vez creado el contenedor entramos y accedemos a consola.

![image](https://user-images.githubusercontent.com/25081670/146308996-553bd2b6-a9f7-4554-8a16-fca77aa1c8ab.png)

Hacemos click en CONNECT

![image](https://user-images.githubusercontent.com/25081670/146309159-7bab7285-3059-4137-b94d-fd0ff0542b25.png)

## Java 17 (OpenJDK 17)

```
apt update
```
```
apt install -y openjdk-17-jdk
```

## Panel de Minecraft Web
```
cd var/www/html/
```
```
apt install wget
```
```
wget https://github.com/JhonDesayuna/MinecraftPanel/raw/main/McWebPanel.zip
```
```
apt install unzip
```
```
unzip McWebPanel.zip
```
```
chmod -R 777 McWebPanel
```
```
apt install -y apache2 php libapache2-mod-php default-jdk screen php-mbstring php-zip php-cli php-json gawk wget zip unzip
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

Añadir delante de los comandos lo siguiente

```
docker exec -it "id contenedor"
```
Ejemplo:
```
docker exec -it "id contenedor" apt install -y openjdk-17-jdk
```

## Bibliografia:

`https://hub.docker.com/r/ubuntu/apache2`

`https://github.com/Konata400/McWebPanel`
