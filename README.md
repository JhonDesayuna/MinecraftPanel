# Como instalar "MinecraftPanel" en docker con portainer (ubuntu 20.04)

## Docker:

Docker Compose
```
version: '2.0'

services:
    apache:
        container_name: apache2
        image: ubuntu/apache2:2.4-20.04_beta
        networks:
          - nginx
        volumes:
            - ./data:/usr/local/apache2/htdocs
            - ./html:/var/www/html
        restart: always
        environment:
            - LETSENCRYPT_EMAIL=alejandrogongon@gmail.com
            - LETSENCRYPT_HOST=McServer.JhonFast.hal.se
            - VIRTUAL_HOST=McServer.JhonFast.hal.se
            - VIRTUAL_PROTO=http
        ports:
            - 25565:25565

networks:
    nginx:
        external: true
```


Después, una vez creado el contenedor entramos y accedemos a consola.

![image](https://user-images.githubusercontent.com/25081670/146308996-553bd2b6-a9f7-4554-8a16-fca77aa1c8ab.png)

Hacemos click en CONNECT

![image](https://user-images.githubusercontent.com/25081670/146309159-7bab7285-3059-4137-b94d-fd0ff0542b25.png)

## Java 17 (OpenJDK 17)

```
apt update
```
```
apt install -y openjdk-21-jdk
```

## Panel de Minecraft Web

```
apt install wget
```
```
apt install unzip
```
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

![image](https://github.com/JhonDesayuna/MinecraftPanel/assets/25081670/c3ecfd98-4227-438e-a5da-7ea5a39060f7)


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
