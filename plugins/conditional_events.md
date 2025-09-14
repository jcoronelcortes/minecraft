# Conditional Events

n Minecraft, los eventos condicionales son una característica de los plugins de servidor, como el plugin ConditionalEvents, que permite ejecutar acciones específicas solo si se cumplen ciertas condiciones. Estos plugins reaccionan a eventos del juego (como un jugador entrando al servidor o rompiendo un bloque) y, en lugar de ejecutar una acción fija, verifican si se cumplen criterios definidos (como la posición del jugador o si tiene un ítem en particular) antes de realizar la acción deseada.

https://www.spigotmc.org/resources/conditionalevents-custom-actions-for-specific-events-1-8-1-21-8.82271/

## Instalacion inicial

Una vez instalado el plugin, se deben eliminar los siguientes archivos y carpetas por defecto:

* Eliminar todos los archivos yml dentro de la carpeta **'events'**.
* Dentro del archivo **config.yml**, dejar una lista vacia ([]) en la opcion **'register_commands'** y elminar todos los eventos por defecto (eliminar todo el contenido bajo el campo **Events**).

## Creacion de un comando

