# Curso de Entornos de Desarrollo y Deployment para WordPress

## Cómo habilitar phpMyAdmin para acceso remoto en XAMPP

    <Directory "/opt/lampp/phpmyadmin">
        ...
        Require all granted
        ...

Para habilitar el acceso remoto a phpMyAdmin utilizando XAMPP se debe modificar el archivo `/opt/lampp/etc/extra/httpd-xampp.conf` de esta manera.

Luego se deben reiniciar los servicios.

## Comando para otorgar permisos a XAMPP para manipular la carpeta de contenidos de WordPress y al archivo .htaccess

    sudo chmod 0777 -R ./tu-ruta/wp-content
    sudo chmod 0777 -R ./tu-ruta/.htaccess

El comando `chmod` permite modificar los permisos de los archivos a los que se les aplique el comando.

Los permisos `0777` le otorgan a todos los usuarios la capacidad de leer, escribir y ejecuar dichos archivos.

La bandera `-R` es para que aplique dichos permisos recursivamente a todos los directorios y archivos desde la raíz.

El último parámetro es la carpeta `wp-content` en donde WordPress almacena todo lo relacionado con el contenido del sitio.

## Definición necesario para habilitar la instalación de plugins y carga de archivos en XAMPP

    define('FS_METHOD', 'direct');

Esta definición se debe incorporar en el archivo `wp-config.php` dentro de la carpeta raíz de la instalación de WordPress.

## Comando para instalar wp-env

    npm -g i @wordpress/env

Este comando instala de forma global el paquete para poder generar servidores para WordPress en todo el entorno.

Recordar que es necesario instalar **Docker** previamente para que funcione ([Windows](https://docs.docker.com/docker-for-windows/install/), [Mac](https://docs.docker.com/docker-for-mac/install/), [Linux](https://docs.docker.com/v17.12/install/linux/docker-ce/ubuntu/#install-using-the-convenience-script)).

Podés ver la documentación completa del paquete [aquí](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-env/).


