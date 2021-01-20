# 3.2	Comprobar			

Abrimos una nueva terminal y ejecutamos el comando `docker ps` el cual nos muestra los contenedores en ejecución:

![](img/001.png)

Una vez comprobado que el contenedor está en ejecución, nos dirigimos al navegador y ponemos la URL `localhost:32768`:

![](img/002.png)

También comprobaremos el acceso a `holamundo1.html`:

![](img/003.png)

Y por último, pararemos y eliminaremos el contenedor:

![](img/004.png)

# 3.3	Migrar la imagen a otra máquina

Exportaremos una imagen Docker a fichero tar:

`docker save -o raul15docker.tar raul/nginx1, guardamos la imagen "raul/nginx1" en un fichero tar`.

![](img/005.png)

Ahora nos llevamos el tar a otra máquina con docker instalado, y restauramos.
`docker load -i raul15docker.tar`, cargamos la imagen docker a partir del fichero tar.

`docker images`, comprobamos que la nueva imagen está disponible.

![](img/008.png)

Probaremos a crear un contenedor (`app3alumno`), a partir de la nueva imagen.

![](img/009.png)


# 4.2	Crear imagen a partir del Dockerfile

Lo primero será crear los ficheros `holamundo2.html` y `Dockerfile` con el siguiente contenido:

![](img/010.png)

![](img/011.png)

Una vez hecho, nos dirigimos a la ubicación de los ficheros y construiremos una nueva imagen a partir del `Dockerfile`:

![](img/012.png)

y comprobamos que funciona correctamente con el comando `docker images`:

![](img/013.png)

# 4.3	Crear contenedor y comprobar

A continuación vamos a crear un contenedor con el nombre app4nginx2, a partir de la imagen raul/nginx2. Probaremos con:

`docker run --name=app4nginx2 -p 8082:80 -t raul/nginx2`

Desde otro terminal:

`docker ps`, para comprobar que el contenedor está en ejecución y en escucha por el puerto deseado.

![](img/014.png)

Comprobar en el navegador:

URL `http://localhost:8082`

URL `http://localhost:8082/holamundo2.html`

![](img/015.png)

![](img/016.png)

# 4.4	Usar imagen de nginx

Crearemos el directorio `docker15b` y crearemos los ficheros `holamundo3.html` y `Dockerfile` con la siguiente información:

![](img/017.png)

Una vez hecho, construiremos la imagen `docker build -t raul/nginx3 .`

Crearemos contenedor, `docker run --name=app5nginx3 -d -p 8083:80 raul/nginx3` y comprobaremos el acceso a `"holamundo3.html"`.

![](img/018.png)

![](img/019.png)

# 5 Docker Hub - Holamundo

Crearemos el directorio `docker15c` y crearemos los ficheros `holamundo15.sh` y `Dockerfile` con la siguiente información:

![](img/20.png)

Una vez hecho, construiremos la imagen `docker build -t raul/holamundo .`

Crearemos contenedor, `docker run raul/holamundo`.

![](img/21.png)

![](img/22.png)

Ahora subiremos la imagen a Docker Hub:

Lo primero será registrarse en Docker Hub, una vez hecho ejecutaremos el comando `docker login -u raulasir15`, para abrir la conexión.

`docker tag raul/holamundo:latest raulasir15/holamundo:version1`, etiquetamos la imagen con `"version1"`.

`docker push raulasir15/holamundo:version1`, para subir la imagen `(version1)` a los repositorios de Docker.

![](img/23.png)
