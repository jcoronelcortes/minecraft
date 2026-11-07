# Archivo server.properties

* **enable-command-block**
>Permite activar (true) o desactivar (false) los bloques de comando en el servidor.

* **max-players**
>Es una configuración en el archivo server.properties (para Java Edition) que define el número máximo de jugadores que pueden entrar y jugar en un servidor al mismo tiempo. También, el comando /setmaxplayers se usa en Bedrock Edition para ajustar este límite directamente en un mundo multijugador. Un valor de max-players más alto permite más jugadores, pero requiere más recursos del servidor.

* **motd**
>Un MOTD (Message of the Day o Mensaje del Día) en Minecraft es el texto descriptivo que aparece junto al nombre y el icono de un servidor en la lista de servidores del juego. Se utiliza para describir el servidor, promocionar características, anunciar eventos, dar reglas o simplemente dar la bienvenida a los jugadores, con la posibilidad de usar texto con colores y formatos para hacerlo más atractivo.

* **online-mod**
>El online-mode en un servidor de Minecraft es un ajuste que determina si el servidor verifica la validez de las cuentas de los jugadores con los servidores de Mojang para autenticarlos. Cuando online-mode está activado (true), solo se conectarán jugadores con cuentas de Minecraft legítimas (premium), lo que mejora la seguridad y permite que las skins de los jugadores se muestren correctamente. Cuando online-mode está desactivado (false), cualquier persona puede unirse al servidor, incluyendo jugadores con copias no licenciadas de Minecraft (a veces llamadas "crackeadas"), aunque esto también puede impedir la carga de las skins y generar riesgos de seguirdad,.
>
>**Valor actual: true** (desde el 07-nov-2026). Solo entran cuentas premium y cada jugador usa su ID oficial de Mojang.
>Antes de cambiar este valor hay que migrar los datos de los jugadores: en modo offline el ID se calcula a partir del nombre,
>y en modo online es el de Mojang, asi que al cambiar de modo cada jugador queda con otro ID y "pierde" inventario, dinero,
>rangos, mascotas, etc. Ver [Actualizacion a Paper 26.3](actualizacion_26_3.md).

* **enforce-secure-profile**
>Es una propiedad del archivo server.properties en Minecraft Java Edition que obliga a los jugadores a tener una clave pública firmada por Mojang para unirse al servidor, con el fin de habilitar el sistema de reporte de chat y firmar mensajes. Cuando está activado (true), los jugadores sin esta clave no pueden unirse, o los mensajes no se pueden reportar, mientras que si está desactivado (false), los mensajes no firmados aparecen sin la advertencia de seguridad asociada.
>
>**Valor actual: true.** Debe ir junto con **online-mode=true**; en modo offline se debe poner en false.

* **spawn-protection**
>Es una función en servidores multijugador (exclusiva de Java Edition) que crea un área cuadrada alrededor del punto de aparición de los jugadores donde no se pueden colocar ni destruir bloques, evitando así daños accidentales al aparecer. Esta protección se puede configurar en el archivo server.properties, y su radio se define según el valor asignado, siendo 0 el valor por defecto en algunos servidores que solo protege el bloque de aparición.

* **logs-ip**
>Cuando se establece en true, las direcciones IP de los jugadores se mostrarán en la consola del servidor al conectarse. Si se establece en false, las IPs se ocultan, lo que ayuda a la privacidad de los jugadores.
