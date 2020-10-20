
# SSH

### 1.1 Servidor SSH
Comprobamos que la maquina virtual se ha configurado correctamente con los siguientes comandos:

- ip a               
- ip route           
- ping 8.8.4.4 -i 2  
- host www.nba.com   
- ping clientXXg     
- ping clientXXw     
- lsblk              
- blkid              

![Imagen_1](imagenes/1conexiones.png)
![Imagen_2](imagenes/2conexiones.png)

### 2.2 Primera conexión SSH GNU/Linux
Añadimos al archivo _/etc/hosts_ los equipos server15g y cliente15w.
Una vez añadidos comprobamos que ambos tienen conexion entre si:

![Imagen_3](imagenes/3conexiones.png)

Una vez verificado que tenemos conexion con el servidor, nos conectaremos por SSH desde la maquina cliente hasta el servidor con el comando _ssh deleon1@server15g_:

![imagen_4](imagenes/4ssh.png)

### 3.2 Comprobar cambio clave servidor SSH
Ahora si intentamos conectarnos desde el cliente hasta el servidor nos aparecera un error:

![imagen_6](imagenes/6errorlinux.png)

Si generamos nuevas keygen podremos acceder al servidor:

![imagen_8](imagenes/8keygenn.png)

Deberia pasar lo mismo con Windows, pero en este caso ha ocurrido un fallo y nos ha dejado acceder con un nuevo ssh-rsa:

![imagen_7](imagenes/7errorwindows.png)

### 5 Autenticación mediante clave pública

Lo primero será iniciar sesión con nuestro el usuario raul de la máquina cliente15g y generar un nuevo para del claves con el comando _ssh-keygen -t rsa_ en la siguiente ubicacion:

- /home/raul/.ssh/id_rsa
- /home/raul/.ssh/id_rsa.pub

![imagen_9](imagenes/9keygen.png)

Ahora vamos a copiar la clave pública (id_rsa.pub), al fichero "authorized_keys" del usuario remoto deleon4 que está en el servidor.
Hay varias formas de hacerlo.
Para ello usaremos el comando _ssh-copy-id deleon4@server15g_:

![imagen_10](imagenes/10keygendeleon4.png)

Y si ahora accedemos del desde el usuario _raul_ desde el cliente hasta el usuario _deleon4_ del servidor, no nos pedirá la contraseña de acceso:

![imagen_11](imagenes/11nopasswd.png)

Para comprobar que esta condicion solo se ha establecido en el usuario _raul_ del cliente, intentamos acceder desde el usuario _raul_ de _Windows_:

![imagen_11](imagenes/12userwindows.png)

Como podemos observar, nos pide la contraseña de acceso.


(6 ) Uso de SSH como túnel para X			
(8.1) Restricción sobre un usuario
(9) Servidor SSH en Windows
