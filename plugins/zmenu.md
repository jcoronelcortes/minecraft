# zMenu

Zmenu es un plugin para servidores de Minecraft que permite a los administradores crear menús y tiendas personalizadas utilizando un sistema de inventarios interactivos. Con Zmenu, puedes diseñar tus propios inventarios con ítems, texto y comandos, que los jugadores pueden abrir para interactuar con el servidor, como comprar objetos, acceder a funciones o teletransportarse. La administración se facilita a través de una herramienta web llamada Minecraft Inventory Builder, que permite diseñar menús visualmente y subirlos directamente al servidor.

https://www.spigotmc.org/resources/zmenu-ultra-complete-menu-plugin.110402/

El plugin trae muchas archivos por defecto, por lo cual inicialmente se debe hacer la siguiente limpieza:

* Dentro de la carpeta **'commnands'**, eliminar la carpeta **'punish'** y eliminar todos los comandos por defecto dentro del archivo **'commands.yml'** dejando un alista vacia ([]).
* Dentro de la carpeta **'inventories'**, eliminar todos los archivos yml.
* Dentro de la carpeta **'patterns'**, eliminar todos los archivos yml.

## Herramienta para crear el inventario

La recomendacion para crear el inventario es utilizar la herramienta web Inventory Builder:

https://minecraft-inventory-builder.com/builder

Una vez creado el inventario, la herramienta web genera un archivo yml que debe ser descargado al computador.

El archivo descargado, debe ser ubicado dentro de la carpeta **'inventories'** del plugin y ejecutar **'/zmenu reload'** para cargar el nuevo inventario.



## Configuracion

Cada vez que se realiza un cambio a los archivos de configuracion, se debe ejecutar el siguiente comando para que el servidor tome los cambios:

* **/zmenu reload**

### config.json

* **generateDefaultFile:** Activa (true) o desactiva (false) la generacion de los archivos por defecto.