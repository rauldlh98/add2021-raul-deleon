# VNC - WINDOWS

  *Ejecutamos el comando nmap -Pn 172.19.15.11, desde la máquina real GNU/Linux para comprobar que los servicios son visibles desde fuera de la máquina VNC-SERVER.*

  ![comprobamos con el comando nmap en una maquina linux](images/imagen1.png)



2.1 Comprobaciones finales


    Conectar desde Window Master hacia el Windows Slave.

    ![nos conectamos a la maquina master](imagenes/imagen2.png)

    Conectar desde GNU/Linux Master hacia el Windows Slave.

    ![nos conectamos mediante una maquina linux](imagenes/imagen3.png)

    Ir al servidor VNC y usar el comando netstat -n para ver las conexiones VNC con el cliente.

    ![comprobamos que nos hemos conectado](imagenes/imagen4.png)
