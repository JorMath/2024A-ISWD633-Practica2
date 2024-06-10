## Esquema para el ejercicio
![Imagen](imagenes/esquema-ejercicio5.PNG)

### Crear la red
# docker network create net-wp -d bridge

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# docker run --name contenedor-mysql --network net-wp --env-file C:\Users\jorma\OneDrive\Escritorio/sql_variables.env -P -d mysql:8
Las variables de entorno son las mismas que la parte 2-variables-de-entorno

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# docker run --name wordpress --network net-wp -p 9300:80 -d wordpress

De acuerdo con el trabajo realizado, en la el esquema de ejercicio el puerto a es **(9300)**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/e989c8f1-97c8-4882-887a-b89e2572f4c4)


Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.

### Eliminar el contenedor wordpress
# COMPLETAR

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# COMPLETAR





