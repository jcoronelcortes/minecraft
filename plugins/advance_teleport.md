# Advance Teleport

AdvancedTeleport es un complemento (plugin) para servidores de Minecraft que mejora las funciones de teletransportación, permitiendo funciones como el envío de solicitudes de teletransporte a otros jugadores (/tpa), la instantaneidad al teletransportar con un comando especial (/tpo), la posibilidad de bloquear solicitudes de otros jugadores (/tpblock), y el comando /back para regresar a tu última ubicación con una pequeña demora, entre otras características avanzadas.

https://www.spigotmc.org/resources/advancedteleport.64139/

## Configuracion del comando Spwan para los jugadores

Este plugin permite que los usuarios puedan usar el comando **'/spawn'** en un mundo, pero para eso se debe definir el lugar a donde los jugadores realizar el spwan ejecutando el siguiente comando en el lugar donde queremos que los jugadores aparescan:

* **/setmainspawn**

Esto permite a los jugadores ejecutar el comando '/spawn' en cualquier mundo que este para aparecer en el lugar y mundo que definimos.

## Archvios de configuracion

Cada vez que se realiza un cambio en un archivo de configuracion se debe ejecutar el siguiente comando para que el plugin tome los cambios:

* **/atp reload**

### config.yml

* **warm-up-timer-duration:** Tiempo en segundos que el jugador debe esperar para ser teletransportado.

* **cancel-warmup-on-rotation:** Si está en 'true' la teletransportacion se cancelará en caso de que el jugador mueva la camara, pero si está en 'false' no se cancelará.

* **cooldown-duration:** Tiempo en segundos que los usuarios deben esperar para poder ejecutar un nuevo comando de teletransportacion.

* **cost-amount:** Monto en dinero que se le cobrara a los jugadores por teletransportarse.

* **teleport-to-spawn-on-first-join:** Esta opcion debe estar en **'false'** que se utilice la opcion del plugin nLogin.

* **custom-warms-up:** Permite definir una lista propia de **warms-up** con su valor. Por ejemplo, se puede definir **sin-cooldown: 0**. Luego de esto, se puede asignar esta nueva configuracion como permiso a un grupo usando **'at.member.timer.\[nombre_custom]'**
>Para asignar este custom a un grupo se debe usar el plugin de Luck Perms con el comando **'lp group \[nombre_grupo] permissions set at.member.timer.\[nombre_custom]'**

### custom-messages.yml

Para definir los colores se debe usar el formato **'mini message'**. Se puede usar la siguiente herramienta para crear el formato de los mensajes:

https://webui.advntr.dev/

* **Common.prefixes:** Permite definir el prefijo o primer texto que tendra cada mensaje que se mostrara en el chat.

