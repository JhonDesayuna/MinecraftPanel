# Como instalar "MinecraftPanel" en docker con portainer (ubuntu 20.04)

## Docker:

Primero instalamos apache2 en docker

`
docker run -d --name apache2-container -e TZ=UTC -p 8080:80 -p 25565:25565 ubuntu/apache2:2.4-20.04_beta
`


`-p 25565:25565` Puerto de minecraft

`-p 8080:80` Puerto de apache2

Después, una vez creado el contenedor entramos y accedemos a consola.

![image](https://user-images.githubusercontent.com/25081670/146308996-553bd2b6-a9f7-4554-8a16-fca77aa1c8ab.png)

Hacemos click en CONNECT

![image](https://user-images.githubusercontent.com/25081670/146309159-7bab7285-3059-4137-b94d-fd0ff0542b25.png)











## Bibliografia:

`https://hub.docker.com/r/ubuntu/apache2`
