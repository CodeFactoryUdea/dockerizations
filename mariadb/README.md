# Maria DB

Aquí encontraras algunos archivos dockerfile o docker-compose para levantar un contenedor con Maria DB

## Explicación

Este es un archivo de configuración de Docker Compose con una definición de servicio que incluye una base de datos MariaDB. A continuación se describe cada una de las secciones:

- version: '3.1': esta es la versión de Docker Compose que se está utilizando.

- services: esta sección define los servicios que se ejecutarán.

- my_mariadb_service: este es el nombre del servicio. Aquí se está definiendo un servicio de base de datos MariaDB.

- image: mariadb: esta línea indica que se utilizará la imagen de MariaDB disponible en Docker Hub para construir el contenedor.

- restart: always: esto indica que el contenedor se reiniciará siempre que se detenga.

- volumes: esta sección especifica que la carpeta ./mariadb_data en el host se montará en la ruta /var/lib/mysql dentro del contenedor de la base de datos. Esto permite que los datos se almacenen fuera del contenedor y sean persistentes.

- environment: aquí se especifican variables de entorno que se utilizarán dentro del contenedor. En este caso, se definen las credenciales de root de la base de datos.

- ports: aquí se especifica el puerto en el host que se debe redirigir al puerto en el contenedor. En este caso, el puerto 3306 en el host se redirige al puerto 3306 en el contenedor.

Nota: la configuración puede ser basica, pero funcional. Se agregarán configuraciones más complejas para las imagenes y contenedores. 