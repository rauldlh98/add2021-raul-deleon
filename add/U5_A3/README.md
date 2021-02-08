3.4 	Comprobar la conectividad

Desde el Máster comprobamos:

1. Conectividad hacia los Minions.

```
# salt '*' test.ping
minion15g:
    True
```

2. Versión de Salt instalada en los Minions

```
# salt '*' test.version
minion15g:
    3000
```

![](img/1.png)

4.5 	Aplicar estado (apache) 			
5.1 	Aplicar estado (users) 			
5.2 	Aplicar estado (files) 			
6.2 	Aplicar estado al minion15w
