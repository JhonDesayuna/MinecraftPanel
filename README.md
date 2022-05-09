# Como instalar "MinecraftPanel" en docker con portainer (ubuntu 20.04)

## Docker:

Primero instalamos apache2 en docker

```
sudo docker run -d --name McWebPanel -e TZ=UTC -p 8081:80 -p 25565:25565 ubuntu/apache2:2.4-20.04_beta
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
wget https://github.com/ergonsale14/MinecraftPanel/raw/main/MinecraftPanel.zip
```
```
apt install unzip
```
```
unzip MinecraftPanel.zip
```
```
chmod -R 777 MinecraftPanel
```
```
apt install -y apache2 php libapache2-mod-php default-jdk screen php-mbstring php-zip php-cli php-json gawk wget zip unzip
```



## Bibliografia:

`https://hub.docker.com/r/ubuntu/apache2`

`https://github.com/Konata400/McWebPanel`
