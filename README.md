# CLASE 1 
# NMAP
# VENTAJAS Y LIMITACIONES
## VENTAJAS
* Gratuito y de Código Abierto: Cualquiera puede usarlo y modificarlo.
* Extensible: Gracias al NSE, se pueden agregar funcionalidades personalizadas.
* Multiplataforma: Funciona en la mayoría de los sistemas operativos.
* Documentación Completa: Cuenta con una amplia documentación y soporte comunitario.

##  LIMITACIONES

* Curva de Aprendiza Eje: Puede ser complejo para usuarios principiantes.
* Falsos Positivos: En algunos casos, puede generar resultados incorrectos.
* Impacto en la Red: Escaneos intensivos pueden afectar el rendimiento de la red.

# FUENTES

[Hackertarget](https://hackertarget.com/nmap-cheatsheet-a-quick-reference-guide/) 
[Book](https://nmap.org/book/)
[Nmap](https://nmap.org/book/man-examples.html)
[NMAP](https://www.udemy.com/courses/search/?src=ukwq=curso+de+Nmap)
[Security](https://securitytrails.com/blog/nmap-commands)

***
# SQL-INJECTION
## All labs
## Mystery lab challenge
Try solving a random lab with the title and description hidden. As you'll have no prior knowledge of the type of vulnerability that you need to find and exploit, this is great for practicing recon and analysis.
Take me to the mystery lab challenge
# SQL injection
## LAB
## APPRENTICESQL injection vulnerability in WHERE clause allowing retrieval of hidden data
Not solved
## LAB 3
PRACTITIONERSQL injection attack, querying the database type and version on MySQL and Microsoft

***

Para realizar el Reto De SQL-INYECTION primero abrimos el Burp Suite Community Edition, luego desde el Burp lanzamos el navegador e ingresamos a https://portswigger.net/web-security/all-labs y escogemos el reto. 

# SQL- INYECCIÓN
## Todos los laboratorios
## Desafío de laboratorio misterioso
Intenta resolver un laboratorio aleatorio con el título y la descripción ocultos. Como no tendrás conocimientos previos sobre el tipo de vulnerabilidad que necesitas encontrar y explotar, esto es ideal para practicar el reconocimiento y el análisis.
Llévame al desafío del laboratorio misterioso

# Inyección SQL

# LABORATORIO Nº 3
## FACULTATIVO Ataque de inyección SQL, consultando el tipo y la versión de la base de datos en Oracle
## LABORATORIO Resuelto
Este laboratorio presenta una vulnerabilidad de inyección SQL en el filtro de categorías de productos. Se puede usar un ataque UNION para recuperar los resultados de una consulta inyectada.
Para resolver el laboratorio, muestre la cadena de versión de la base de datos.
Ingresamos al portal y damos click en IR AL LABORATORIO, donde se nos despliega la página donde vamos a trabajar, procedemos a escoger la categoría Gifts con el objetivo de que el BURN capture el tráfico que esta página genera.


 
Una vez capturado el tráfico procedemos a ingresar la solución que el mismo reto nos da:  
1.	Utilice Burp Suite para interceptar y modificar la solicitud que establece el filtro de categoría de producto.
2.	Determine el número de columnas que devuelve la consulta y cuáles contienen datos de texto. Verifique que la consulta devuelva dos columnas, ambas con texto, utilizando una carga útil como la siguiente en el *_category_* parámetro: *_'+UNION+SELECT+'abc','def'+FROM+dual--_*
3.	Utilice la siguiente carga útil para mostrar la versión de la base de datos:
*_'+UNION+SELECT+BANNER,+NULL+FROM+v$version--_*

Para poder trabajar con las dos sentenciar primero en el área de REQUEST colocamos el cursor en algún lugar de este sitio y damos click derecho y escogemos la opción que die: SEND TO REPEATER y se nos abre una ventana RESPONSE, nos dirigimos al menú a la opción REPEATER.
 
 
Una vez dentro de la opción REPETEAR vamos al código e ingresamos la solución:
## Solución 1
 
Procedemos a dar clcik en SEND para que se actualice los registros
## Solución 2
 
Procedemos a dar clcik en SEND para que se actualice los registros
Terminado el ingreso de la solución verificamos que surta efecto.
