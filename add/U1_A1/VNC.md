# VNC - WINDOWS

  Ejecutamos el comando nmap -Pn 172.19.15.11, desde la máquina real GNU/Linux para comprobar que los servicios son visibles desde fuera de la máquina VNC-SERVER.

  ![comprobamos con el comando nmap en una maquina linux](imagenes/imagen1.png)



2.1 Comprobaciones finales


    Conectamos desde Window Master hacia el Windows Slave.

![nos conectamos a la maquina master](imagenes/imagen2.png)

    Conectamos desde GNU/Linux Master hacia el Windows Slave.

![nos conectamos mediante una maquina linux](imagenes/imagen3.png)

    Ejecutamos el comando netstat -n para ver las conexiones VNC con el cliente.

![comprobamos que nos hemos conectado](imagenes/imagen4.png)
