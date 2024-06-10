### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:11.21-alpine3.17
# docker run --name Postgres -d postgres:11.21-alpine3.17

### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4

# COMPLETAR

La figura presenta el esquema creado en donde los puertos son:
- a: (80)
- b: (80)
- c: (5432)

![Imagen](imagenes/esquema-ejercicio3.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/fbdc91f9-e729-4ad7-ac5d-c48b6efef366)

### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.
Para realizar la conexión a la base de datos se tuvo que poner la ip
Intenté poner el hostname pero no lo reconocía, solo lo reconocía por IP, para arreglar esto había que poner en hostname el nombre del contenedor, no de la máquina
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/8bc5b750-ccae-46cc-b824-0d8fca994e5f)
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/53f98925-be8e-4c3c-9bd5-5e6ba552e49a)

## Desde el servidor postgresl
### Acceder al servidor
docker exec -it Postgres psql -U postgres -h localhost
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/7ff00680-34a5-450c-aa1c-fe448bff599e)

### Conectarse a la base de datos info
\c info;
### Realizar un select *from personas
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/78ce419c-6480-4c3b-86e6-bba4b6bae78e)


