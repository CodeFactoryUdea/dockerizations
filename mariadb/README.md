# Maria DB

Aquí encontraras algunos archivos dockerfile o docker-compose para levantar un contenedor con Maria DB

## Explicación del Dockerfile y comandos necesarios para levantar el contenedor

### Construir la imagen a partir del Dockerfile

En el siguiente comando el punto (.) al final indica que tomara el dockerfile está en la misma ruta donde se ejecuta el comando.

Este comando de Docker construye una imagen de contenedor a partir del contexto actual (.) y le asigna el nombre my-mariadb-image con el flag -t.

En otras palabras, Docker utilizará el Dockerfile presente en el directorio actual para construir una imagen de contenedor y la etiquetará con el nombre especificado (my-mariadb-image) para que pueda ser utilizada en otros comandos, como por ejemplo docker run.

Es importante destacar que la construcción de la imagen puede tomar algún tiempo en función de la complejidad del Dockerfile y la cantidad de dependencias necesarias.

```bash
docker build -t my-mariadb-image .
```

### Ejecutar el contenedor con la imagen anteriormente construida

Este comando de Docker inicia un contenedor de la imagen my-mariadb-image con el nombre my-mariadb-image-container y lo vincula al directorio local ./mariadb_data_from_dockerfile en la ruta /var/lib/mysql dentro del contenedor.

Además, el comando mapea el puerto 3306 del contenedor al puerto 3306 del host local con el flag -p.

La opción --name se utiliza para establecer un nombre personalizado para el contenedor.

En resumen, este comando ejecuta un contenedor de MariaDB con los datos almacenados en un directorio local y con la posibilidad de acceder a la base de datos desde el host local mediante el puerto mapeado.

```bash
docker run --name -v ./mariadb_data_from_dockerfile:/var/lib/mysql my-mariadb-image-container -p 3306:3306 my-mariadb-image
```



## Explicación del docker-compose.yml

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