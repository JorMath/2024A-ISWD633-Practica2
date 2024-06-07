# Variables de Entorno
### ¿Qué son las variables de entorno
Son cadenas de texto que pueden ser accedidas con un nombre, y se utilizan para guardar configuraciones, rutas de algún programa o contraseñas

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

# docker run -d --name nginx -e username=jrmth -e role=admin ng
inx:alpine
docker exec -it nginx env
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/48ee6d32-ead4-4716-9c95-e9a08c6119c0)


### Crear un contenedor con mysql:8 , mapear todos los puertos
# docker run --name mysql8-container -P -d mysql:8

### ¿El contenedor se está ejecutando?
# No, existe un problema
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/38302dfd-e204-49de-b028-3096fb473757)

### Identificar el problema
# Al ingresar a los logs, me dice que debo tener ciertas variables de entorno configuradas, por lo que no inicia
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/92860ff4-c711-4fee-b573-3a4368f0ae83)

### Eliminar el contenedor creado con mysql:8 
# docker stop mysql8-container && docker rm mysql8-container

### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

Previo a esto es necesario crear el archivo y colocar las variables en un archivo, **.env** se ha convertido en una convención estándar, pero también es posible usar cualquier extensión como **.txt**.
```
docker run -d --name <nombre contenedor> --env-file=<nombreArchivo>.<extensión> <nombre imagen>
```
**Considerar**
Es necesario especificar la ruta absoluta del archivo si este se encuentra en una ubicación diferente a la que estás ejecutando el comando docker run.

### Crear un contenedor con mysql:8 , mapear todos los puertos y configurar las variables de entorno mediante un archivo
# docker run --name mysql8-container --env-file C:\Users\jorma\OneDrive\Escritorio/sql_variables.env -P -d mysql:8
Para las variables de entorno
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/a249e01b-b154-48d5-a1a5-b8cd31b6685f)

![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/8d2f0185-a687-49ea-8e7c-ae038f3b2682)


### ¿Qué bases de datos existen en el contenedor creado?
# docker exec -it mysql8-container bash
# mysql -u jrmth -p
![image](https://github.com/JorMath/2024A-ISWD633-Practica2/assets/94020880/57775f65-4594-490c-967b-1464c45deea8)
