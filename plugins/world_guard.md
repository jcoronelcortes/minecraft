# World Guard

WorldGuard es un plugin para servidores de Minecraft que permite a los administradores proteger y definir áreas específicas del mapa, llamadas "regiones", para evitar que los jugadores realicen ciertas acciones o modifiquen el terreno de forma no deseada. Se utiliza para proteger la propiedad de los jugadores, crear zonas de comercio y gestionar las funciones del servidor, como el daño por explosiones, la aparición de mobs y la interacción con cofres.

https://dev.bukkit.org/projects/worldguard

Existen varias estrategias para proteger un sector o region completa.

## Proteccion de region

Para proteger una region se deben seguir los siguientes pasos:

* Activar el vuelo
* Alejarse a una ezquina en donde se vea los limites (derecha y izquierdo por ejemplo) de la region y ejecutar el comando **'/pos1'**.
* Ir a la ezquina contraria (frente al punto en donde se ejecuto el pos1) y ejecutar **'/pos2'**.
* Luego ejecutar el comando **'/expand vert'** para que extienda la seleccion de arriba hacia abajo.
* Finalmente ejecutar **'/region define [nombre_nueva_region]'** para darle un nombre a la region protegida.

