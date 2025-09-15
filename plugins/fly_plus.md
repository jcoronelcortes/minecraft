# Fly Plus

es un plugin que permite a los jugadores volar en servidores, ofreciendo el comando /fly y la capacidad de configurar en qué mundos el vuelo está habilitado. Funciona para versiones de Minecraft posteriores a la 1.17 y otorga el permiso fly.to a los usuarios para usar el comando, permitiendo también la personalización de mensajes y la recarga de la configuración con /fly reload.

https://www.spigotmc.org/resources/flyplus-1-17-x-1-21-x-quality-fly-plugin-for-your-server.63553/

## Instrucciones

Para volar se debe ejecutar el comando **'/fly'** y ejecutar el mismo comando para desactivarlo.

## Permisos

* **fly.toggle:** Permite asignar el permiso de volar a un jugador.
>Para asiganr el permiso de volar en un grupo usando Luck Perms se debe ejecutar el comando **''/lp group \[nombre_grupo_asignar_permiso] permission set fly.toggle'**

## config.yml

Cada vez que se realiza un cambio en el archivo de configuracion se debe ejecutar el comando **'/fly reload'** para que el servidor actualice los cambios.

* **Enabled-Worlds:** Contiene la lista de mundos en los cuales se permitira ejecutar el comando **fly** para volar.