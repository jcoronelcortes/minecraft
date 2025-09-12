# Servidor

## Archivo server.properties

* **enable-command-block**
>Permite activar (true) o desactivar (false) los bloques de comando en el servidor.

* **max-players**
>Es una configuración en el archivo server.properties (para Java Edition) que define el número máximo de jugadores que pueden entrar y jugar en un servidor al mismo tiempo. También, el comando /setmaxplayers se usa en Bedrock Edition para ajustar este límite directamente en un mundo multijugador. Un valor de max-players más alto permite más jugadores, pero requiere más recursos del servidor.

* **motd**
>Un MOTD (Message of the Day o Mensaje del Día) en Minecraft es el texto descriptivo que aparece junto al nombre y el icono de un servidor en la lista de servidores del juego. Se utiliza para describir el servidor, promocionar características, anunciar eventos, dar reglas o simplemente dar la bienvenida a los jugadores, con la posibilidad de usar texto con colores y formatos para hacerlo más atractivo.

* **online-mod**
>El online-mode en un servidor de Minecraft es un ajuste que determina si el servidor verifica la validez de las cuentas de los jugadores con los servidores de Mojang para autenticarlos. Cuando online-mode está activado (true), solo se conectarán jugadores con cuentas de Minecraft legítimas (premium), lo que mejora la seguridad y permite que las skins de los jugadores se muestren correctamente. Cuando online-mode está desactivado (false), cualquier persona puede unirse al servidor, incluyendo jugadores con copias no licenciadas de Minecraft (a veces llamadas "crackeadas"), aunque esto también puede impedir la carga de las skins y generar riesgos de seguirdad,.

* **enforce-secure-profile**
>Es una propiedad del archivo server.properties en Minecraft Java Edition que obliga a los jugadores a tener una clave pública firmada por Mojang para unirse al servidor, con el fin de habilitar el sistema de reporte de chat y firmar mensajes. Cuando está activado (true), los jugadores sin esta clave no pueden unirse, o los mensajes no se pueden reportar, mientras que si está desactivado (false), los mensajes no firmados aparecen sin la advertencia de seguridad asociada.