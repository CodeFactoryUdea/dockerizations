# Dockerizations

El Dockerfile define como crear la imagen de una aplicación, en cambio el docker-compose nos permite vincular y configurar estos contenedores en conjunto para construir varios servicios. 


## Docker compose

### Instalación en linux/macos y windows

A continuación se dejan algunas URLs donde puedes leer como instalar docker compose en algunos sistemas operativos.

Una forma de obtener docker compose y docker cli, es instalando [docker desktop](https://docs.docker.com/desktop/), a continuación te dejo el link a la documentación:

https://docs.docker.com/desktop/



## Algunos comandos básicos para usar docker-compose

### Levantar los servicios de un docker-compose

```sh
docker-compose up
```

### Detener y eliminar los contenedores: 

```sh
docker-compose up
```

### Listar los contenedores en ejecución:

```sh
docker-compose ps
```

### Crea o reconstruye las imagenes de Docker según el docker-compose.yml

```sh
docker-compose build
```


NOTA: todos estos comandos deben ser ejecutados en el mismo directorio que contiene el archivo docker-compose.yml