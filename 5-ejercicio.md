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
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/9b16f344-4127-4b32-9832-80287a8bac74)
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/b6da3951-8485-4cad-86a6-dcf5fb8d7136)



Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/bf3651e3-4986-44d3-9fef-c16dbfa353b9)
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/4ca03ca4-7a33-465e-a639-a01bdb023222)

# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/968c27b7-0bfc-499f-88db-3d846a4d800c)

### Eliminar el contenedor wordpress
docker rm wordpress

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
Se han quedado guardadas algunas configuraciones de wordpress
Incluso la página y el tema anterior se han guardado





