Nagios-Core Docker Image

Este repositorio contiene un Dockerfile para construir una imagen de Docker que instala y configura Nagios Core en un contenedor basado en Ubuntu.

## Descripción

Nagios Core es una plataforma de monitoreo de infraestructura que permite a los administradores de sistemas monitorear sistemas y aplicaciones. Este Dockerfile instala Nagios Core, junto con sus dependencias, en la última versión de Ubuntu.

## Requisitos

- Docker instalado en tu sistema.

## Instrucciones de Uso

### Construcción de la Imagen

Para construir la imagen de Docker, ejecuta el siguiente comando en el directorio donde se encuentra el Dockerfile:

```sh
docker build -t nagios-core .
```

### Ejecución del Contenedor

Para ejecutar un contenedor basado en la imagen creada, usa el siguiente comando:

```sh
docker run -d -p 80:80 nagios-core
```

Este comando iniciará un contenedor en segundo plano (`-d`) y mapeará el puerto 80 del contenedor al puerto 80 de tu máquina host (`-p 80:80`).

### Acceso a la Interfaz Web de Nagios

Una vez que el contenedor esté en ejecución, puedes acceder a la interfaz web de Nagios visitando `http://localhost` en tu navegador web. Usa las siguientes credenciales para iniciar sesión:

- **Usuario**: nagiosadmin
- **Contraseña**: nagiospassword

## Detalles del Dockerfile

El Dockerfile realiza las siguientes acciones:

1. Usa la imagen base de Ubuntu última versión.
2. Configura el entorno no interactivo para `apt-get`.
3. Instala las dependencias necesarias para Nagios y Apache.
4. Crea el usuario y grupo `nagios` y `nagcmd`.
5. Descarga, descomprime e instala Nagios Core.
6. Descarga, descomprime e instala los plugins de Nagios.
7. Configura Apache para Nagios.
8. Configura un usuario y contraseña para acceder a la interfaz de Nagios.
9. Expone el puerto 80.
10. Configura Nagios y Apache para que inicien automáticamente al arrancar el contenedor y muestra los logs de Apache.

## Comandos Importantes

- **Construcción de la imagen**:
  ```sh
  docker build -t nagios-core .
  ```

- **Ejecución del contenedor**:
  ```sh
  docker run -d -p 80:80 nagios-core
  ```

## IMPORTANTE

- Asegúrate de cambiar la contraseña predeterminada `nagiospassword` por una contraseña segura en un entorno de producción.
- Puedes personalizar el Dockerfile según tus necesidades específicas.
