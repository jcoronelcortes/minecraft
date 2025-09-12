# Multiverse Core

Es un plugin para servidores de Minecraft que permite a los administradores crear y gestionar múltiples mundos (normal, Nether, End, etc.) dentro de un mismo servidor, además de poder teletransportarse entre ellos, importar mapas existentes, y configurar propiedades únicas para cada mundo, como el modo de juego o las reglas.

https://dev.bukkit.org/projects/multiverse-core

MV es la abreviatura de Multiverse,. El plugin permite a los administradores crear, gestionar y acceder a múltiples mundos dentro de un mismo servidor

* **/mv info**
>Se usa para visualizar información detallada sobre un mundo específico en el servidor, como su configuración y estado.

* **/mv tp [nombre_mundo]**
>Permite teletransportarse entre diferentes mundos dentro de un servidor. Una vez realizado el comando se debe ejecutar **'/mv confirm'** para confirmar la accion.


## Importar un nuevo mundo al servidor.

La carpeta con el nuevo mundo se debe dejar dentro de la carepta del servidor. Una vez completada la importancion de la carpeta se debe ejecutar el comando import.

* **/mv import [nombre_carpeta_mundo] normal**
>Se utiliza para integrar una carpeta de mundo existente (que ya tienes en tu sistema de archivos) a tu servidor Paper, permitiéndote tener múltiples mundos disponibles para los jugadores en tu servidor. Este comando requiere especificar su tipo (como "normal", "nether" o "end").


## Definir el Spawn del mundo

Para definir el lugar donde seimpre aparecera el jugador al ser teletransportado al mundo, se debe posicionar al persona en el lugar deseado y ejecuatr los siguientes comandos:

* **/mv setspawn**
>Establece el punto de aparición global para el mundo actual al que se están uniendo los jugadores o del que se han teletransportado.

* **/setworldspawn**
>Permite establecer la ubicación donde los jugadores aparecerán por primera vez o al morir en un mundo. Si se ejecuta sin coordenadas, establece el punto de generación en la posición actual del jugador; de lo contrario, usa las coordenadas x y z especificadas.


## Crear un nuevo mundo

* **/mv create [nombre_nuevo_mundo] normal**
>Permite crear un nuevo mundo en tu servidor. Este comando requiere especificar un nombre para el mundo y su tipo (como "normal", "nether" o "end").