# World Guard

WorldGuard es un plugin para servidores de Minecraft que permite a los administradores proteger y definir áreas específicas del mapa, llamadas "regiones", para evitar que los jugadores realicen ciertas acciones o modifiquen el terreno de forma no deseada. Se utiliza para proteger la propiedad de los jugadores, crear zonas de comercio y gestionar las funciones del servidor, como el daño por explosiones, la aparición de mobs y la interacción con cofres.

https://dev.bukkit.org/projects/worldguard

## Informacion de la region

Para obtener informacion de la region en la que estamos se debe ejecutar el comando:

* **/region info**
>Despliega informacion de la region y una serie de menus que permiten activar o desactivar flags de la region.

## Modificar las flags de la region

Para modificar la flag de una region se debe activar la opcion ejecutando el comando **'/region flags'**.

* **deny-message:** Permite modificar el mensaje que sale al destruir algo. Para que no salgan mensajes en el chat se puede definir el texto **'&6'**.

* **fall-damage:** Permite activa o desactivar que le personaje reciba daño al caer de altura.

* **invincible:** Permite activa o desactivar que los personajes no puedan ser dañados.


## Proteccion

Existen varias estrategias para proteger un sector o region completa.

### Proteccion de region

Para proteger una region se deben seguir los siguientes pasos:

* Activar el vuelo
* Alejarse a una ezquina en donde se vea los limites (derecha y izquierdo por ejemplo) de la region y ejecutar el comando **'/pos1'**.
* Ir a la ezquina contraria (frente al punto en donde se ejecuto el pos1) y ejecutar **'/pos2'**.
* Luego ejecutar el comando **'/expand vert'** para que extienda la seleccion de arriba hacia abajo.
* Finalmente ejecutar **'/region define [nombre_nueva_region]'** para darle un nombre a la region protegida.

### Proteccion del Mundo

Existe una region que se llama **'\__global\__'** y para ver la información de esta region se puede ejecutar el comando **'/region info \__global\__'**. esta es la region asociada a todo el mundo y se puede utilizar para proteger el mundo.

Lo recomendable es crear protecciones por region, debido a que la proteccion de mundo agrega muchas flags por defecto, pero si se quiere hacer esto, se debe ejecutar los siguientes comandos:

* **'/region flag \__global\__ block-break deny'**: Este comando permite que los jugadores no puedan romper bloques en este mundo.

* **'/region flag \__global\__ block-pace deny'**: Este comando permite que los jugadores no puedan poner bloques en este mundo.

La otra opcion es hacerlo ejecutando un solo comando de esta forma:

* **'/region flag \__global\__ build deny'**