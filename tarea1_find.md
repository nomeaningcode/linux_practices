Utiliza el comando find para buscar los siguientes ficheros dentro de Linux.
Preguntas de esta tarea

Busca la ruta donde se encuentra el comando externo ls utilizando find. Asegúrate de eliminar los mensajes de acceso denegado que produzca el comando.

```sh
find / -name ls 2> /dev/null
```

Busca directorios de configuración del programa firefox que viene instalado por defecto en Ubuntu. El nombre de los directorios debe ser firefox (igual que el programa).

```sh
find / -name firefox -type d 2> /dev/null
```

Busca el usuario propietario del fichero shadow que se encuentra en algún lugar del sistema de ficheros de Linux excluyendo aquellos ficheros shadow que se encuentren dentro de la ruta /snap.

```sh
find / -name shadow -not -path '*/snap/*' 2> /dev/null
find / -path /snap -prune -o -name shadow -exec ls -l {} \; 2>/dev/null
```