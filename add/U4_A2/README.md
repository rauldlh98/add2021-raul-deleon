# 1. Preparativos
<<<<<<< HEAD
Comprobamos el acceso al LDAP desde el cliente:

Ir a MV cliente y comprobar que el servidor LDAP es accesible desde la MV2 cliente

    nmap -Pn 172.19.15.31 | grep -P '389|636'

    ldapsearch -H ldap://172.19.15.31:389 -W -D "cn=Directory Manager" -b "dc=ldap15,dc=curso2021" "(uid=*)*" | grep dn:

![](img/001.png)

# 2.1 Crear conexión con servidor

Vamos a configurar de la conexión del cliente con el servidor LDAP.

        Ir a la MV cliente.
        Ir a Yast -> Cliente LDAP y Kerberos.
        Configurar con los siguientes datos:
        URI: ldap://172.19.15.31:389
        BaseDN: dc=ldap15,dc=curso2021
        DN de usuario: cn=Directory Manager
        cn=Directory Manager, Contraseña: raulasir1998

![](img/002.png)

    Al final usar la opción de Probar conexión

# 2.2 Comprobar con comandos

    Vamos a la consola con usuario root, y probamos lo siguiente:

id mazinger
su -l mazinger   # Entramos con el usuario definido en LDAP

getent passwd mazinger          # Comprobamos los datos del usuario
cat /etc/passwd | grep mazinger # El usuario NO es local
=======

Comprobamos el acceso al LDAP desde el cliente:

Ir a MV cliente y ejecutar los siguientes comandos:

`nmap -Pn 172.19.15.31 | grep -P '389|636`

 Comprobamos que los usuarios del LDAP remoto son visibles en el cliente:

 `ldapsearch -H ldap://172.19.15.31:389 -W -D "cn=Directory Manager" -b "dc=ldap15,dc=curso2021" "(uid=*)" | grep dn`

![](img/001.png)

# 2. Configurar autenticación LDAP

### 2.1 Crear conexión con servidor

Nos dirigimos a la MV cliente y entramos en `yast -> Cliente LDAP y Kerberos` y Configuraremos con los siguientes datos:

![](img/002.png)

Al finalizar comprobará que funciona correctamente:

![](img/003.png)

### 2.2 Comprobar con comandos

Lo primero será iniciar un terminal con el usuario root y probamos los siguientes comandos:

```
id mazinger <- Visualizar el usuario
su -l mazinger <- Entramos con el usuario definido en LDAP

getent passwd mazinger <- Comprobamos los datos del usuario
cat /etc/passwd | grep mazinger <- El usuario no es local
```

![](img/004.png)
>>>>>>> 56dd7da2bc7f5181f9a4416549cb59d3da92d922
