# (2.4) Comprobar contenido del DS LDAP 			

    ldapsearch -b "dc=ldapXX,dc=curso2021" -x | grep dn, muestra el contenido de nuestra base de datos LDAP. "dn" significa nombre distiguido, es un identificador que tiene cada nodo dentro del árbol LDAP.


    ![1](img/1.png)

    ![grep_dn](img/1.png)

    ldapsearch -H ldap://localhost -b "dc=ldapXX,dc=curso2021" -W -D "cn=Directory Manager" | grep dn, en este caso hacemos la consulta usando usuario/clave.

# (3.3) Comprobar nuevo usuario 			

Estamos usando la clase posixAccount, para almacenar usuarios dentro de un directorio LDAP. Dicha clase posee el atributo uid. Por tanto, para listar los usuarios de un directorio, podemos filtrar por "(uid=*)".ldapsearch -W -D "cn=Directory Manager" -b "dc=ldapXX,dc=curso2021" "(uid=*)", para comprobar si se ha creado el usuario correctamente en el LDAP.

# (4.3) Comprobar los usuarios creados


    Ir a la MV cliente LDAP.
    nmap -Pn IP-LDAP-SERVER, comprobar que el puerto LDAP del servidor está abierto.
    Ejecutar comando ldpasearch -H ldap:///IP-LDAP-SERVER -W -D "cn=Directory Manager" -b "dc=ldapXX,dc=curso2021" "(uid=*)" | grep dn para consultar los usuarios LDAP que tenemos en el servicio de directorio remoto.
