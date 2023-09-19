
# 1.Descarga la imagen 'ubuntu y comprueba que está en tu equipo

Comando “docker run ubuntu bash” para descargar la imagen.

Comando “docker images” para comprobar que está descargada.

# 2.Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre

docker run -it ubuntu bash. Al crearlo usando “-it” se arranca al crearse.

docker ps -a. Con este comando comprobamos que está creado.

Nombre del contenedor: busy_franklin


# 3.Crea un contenedor con el nombre 'ubu1'. ¿Como puedes acceder a él?

docker run -it --name ubu1 ubuntu bash

Añadiendo -it para acceder a él


# 4.Comprueba que ip tiene y si puedes hacer un ping a google.com

Con el comando ifconfig previamente instalado con el comando “apt install net-tools”. Su ip es la 172.17.0.2

ping 8.8.8.8


# 5.Crea un contenedor con el nombre 'ubu2'. ¿Puedes hacer ping entre los contenedores?

docker run -it --name ubu2 ubuntu bash. Se le asignó la ip 172.17.0.3. Debemos usar “-it” para interactuar con el terminal y “--name” para asignarle el nombre al contenedor.

ping 172.17.0.3 en el contenedor ubu1

ping 172.17.0.2 en el contenedor ubu2

Previamente debemos instalar previamente el comando ping con el comando “apt install iputils-ping”. Si están correctamente creados harán ping entre ellos.


# 6.Sal del terminal, ¿que ocurrió con el contenedor?

Al salir del terminal el contenedor se detuvo


# 7.¿Cuanta memoria en el disco duro ocupaste? ¿Hay alguna herramienta de docker para calcularlo?

Con el comando “docker images” se puede ver lo que ocupamos con la imagen descargada. La imagen que descargamos ocupa 77,8 MB

Con el comando “docker system df” podemos averiguar el peso de todos los contenedores en total. Con el comando “docker container inspect ubu1” podemos ver detalles del contenedor ubu1. 


# 8.¿Cuanta RAM ocupan los contenedores? Crea cuantos contenedores necesites para calcularlo

Con el comando “docker container stats” podemos ver cuanta RAM están consumiendo los contenedores activos. En este caso, tanto el contenedor ubu1 como el ubu2 consumen 880 KiB cada uno.