
# (1.4 y 1.5) Fichero smb.conf

Antes de configurar el servidor Samba, haremos una copia de seguridad en archivo de configuración con el comando _cp /etc/samba/smb.conf /etc/samba/smb.conf.bak_

![smb.conf.bak](img/Seleccion_001.png)

Lo siguiente será dirigirse a yast y cambiar la configuración de **Samba Server**. En la pestaña _Inicio_, establecemos _Iniciar durante el arranque_ y habilitaremos el _Puerto abierto en el cortafuegos_:

![samba_server](img/Selección_003.png)

A continuación vamos a configurar los recursos compartidos de red en el servidor.

Modificaremos los siguientes parámetros: global, public, barco, y castillo con la siguiente configuración:

- **public** será un recurso compartido accesible para todos los usuarios en modo lectura.

- **barco** recurso compartido de red de lectura/escritura para todos los piratas.

- **castillo** recurso compartido de red de lectura/escritura para todos los soldados.

Podemos modificar la configuración editaremos directamente el fichero _/etc/samba/smb.conf_:

![smb.conf](img/Selección_004.png)

Para finalizar la configuración ejecutaremos los comandos _testparm_ y _more /etc/samba/smb.conf_ para verficar que todo esta correcto:

![smb.conf](img/Selección_005.png)

![smb.conf](img/Selección_006.png)

# (2.1 y 2.2) Conexión SMB desde Windows

Accedemos desde un cliente Windows con la IP del **Servidor Samba**:

![w_samba](img/Selección_007.png)

Accedemos al recurso **castillo**  con usuario **soldado** y con el comando _net use_ observaremos las conexiones abiertas:

![w_soldado](img/Selección_008.png)

Accedemos al recurso **barco**  con usuario **pirata** y con el comando _net use_ observaremos las conexiones abiertas:

![w_pirata](img/Selección_009.png)

Lo siguiente será dirigirse al **Servidor Samba** y ejecutar los comando _smbstatus_ y _lsof -i_:

![smb](img/Selección_010.png)

![smb](img/Selección_010.png)

# (3.1 y 3.2) Conexión SMB desde GNU/Linux			
# (3.3) Montaje automático			
