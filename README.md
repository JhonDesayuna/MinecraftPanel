# Como instalar "MinecraftPanel" en docker con portainer (ubuntu 20.04)

## Docker:

Primero instalamos apache2 en docker

docker run -d --name apache2-container -e TZ=UTC -p 8080:80 -p 25565:25565 ubuntu/apache2:2.4-20.04_beta

*`-p 25565:25565` Puerto de minecraft
*`-p 8080:80` Puerto de apache2


##Bibliografia:
