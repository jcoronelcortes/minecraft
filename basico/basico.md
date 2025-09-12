# Comandos basicos de Minecraft

## Administracion

* **/op [nombre usuario]**
>Para dar acceso de administrador o "OP" en Minecraft, abre la consola del servidor o la ventana de chat en el juego y escribe '/op [nombre de usuario]' reemplazando [nombre de usuario] con el nombre exacto del jugador. Este comando otorga todos los privilegios de operador a ese jugador, permitiéndole ejecutar todos los comandos administrativos del servidor. 

* **/deop [nombre usuario]**
>Revoca el estado de operador (o OP) a un jugador específico en el servidor o mundo. Al usarlo, se le quitan al jugador los permisos administrativos y la capacidad de usar comandos especiales que solo los operadores tienen, permitiendo así gestionar o moderar a otros jugadores de forma más segura.

* **/stop**
>El comando /stop en Minecraft sirve para detener el servidor, guardando todos los cambios y expulsando a los jugadores. Se utiliza en servidores y requiere permisos de nivel 4 para poder ser ejecutado.

* **/whitelist add [usuario]**
>Agrega un jugador a la lista de jugadores permitidos. Una vez agregado un nuevo jugador, se debe ejecutar el comando **'whitelist on'** para activar la nueva lista en el servidor.

* **/whitelist remove [usuario]**
>Remueve un jugador a la lista de jugadores permitidos. Una vez removido un nuevo jugador, se debe ejecutar el comando **'whitelist on'** para activar la nueva lista en el servidor.

* **/gamemode creative**
>El modo Creativo en Minecraft es un modo de juego que libera al jugador de las restricciones de supervivencia, permitiéndole volar, acceder a recursos ilimitados de todos los bloques y objetos, y ser invencible. Este modo es ideal para centrarse en la construcción libre y la experimentación, ya que elimina la necesidad de alimentarse, la presencia de enemigos hostiles y el peligro de la muerte.

* **/gamemode spectator**
>Es un modo de juego que permite al jugador volar sin interactuar con el mundo, atravesar bloques y observar a otros jugadores y entidades desde cualquier punto de vista.

* **/tp [nombre_jugador_a_teletransportar] [nombre_jugador_donde_se_teletarnsportara]**
>Permite teletransportar instantáneamente a un jugador, a ti mismo, o a otra entidad (como un mob o un objeto) de un lugar a otro dentro del juego.

## Tiempo

El comando **'/time set [valor]'** permite cambair el tiempo para hacer de dia o noche.

* **Valores numéricos:** Se puede usar números del 0 al 24000, donde 0 representa el amanecer (6 a. m.). Por ejemplo, /time set 0 es el amanecer. 
* **Palabras clave:** Se puede usar palabras como day (día), noon (mediodía), o night (noche) para establecer la hora a un punto del ciclo diurno.

* **/time set  [valor]**
>Se utiliza para cambiar la hora del día en tu mundo de juego, estableciéndola a un valor específico o predefinido como "day" (día) o "night" (noche).


## Reglas (Game rules)

* **/gamerule doMobSpawning [true o false]**
>Controla si las criaturas (mobs) se generan de forma natural en el mundo del jugador. Al establecerla en false con el comando **'/gamerule doMobSpawning false'**, se impide que aparezcan mobs hostiles, pacíficos y neutrales de forma automática, y al establecerla en true, se permite que vuelvan a aparecer.

* **/gamerule doDaylightCycle [true o false]**
>Controla si el ciclo de día y noche está activo o no. Si está establecida en true (verdadero), el sol y la luna se moverán normalmente, y el ciclo día-noche transcurrirá. Si se establece en false (falso), el sol se detendrá en una posición fija, manteniendo una hora constante y evitando la aparición de la mayoría de los mobs hostiles.