# Grief Prevention

GriefPrevention es un plugin que permite a cada jugador proteger su propio terreno (un "claim"). Dentro de un terreno protegido
solo el dueño, y los jugadores a los que el dueño autorice, pueden construir, romper bloques o abrir cofres.

https://modrinth.com/plugin/griefprevention

Instalado el 07-nov-2026 (version **16.18.8**). Esta **activo solo en el mundo principal (world)**, que es donde lleva el warp **naciones1**.
En el resto de los mundos esta desactivado.

## Comandos para los jugadores

* **Pala de oro**
>Clic derecho en dos esquinas opuestas para proteger el terreno entre ellas. Para agrandar un terreno, clic derecho en una esquina y luego en la nueva posicion.

* **Palo**
>Clic derecho para ver los limites de los terrenos cercanos.

* **/claim**
>Protege un cuadrado alrededor de donde esta parado el jugador.

* **/trust \[nombre_usuario]**
>Permite a otro jugador construir y romper en el terreno donde esta parado el dueño. **/untrust \[nombre_usuario]** quita el permiso.

* **/accesstrust \[nombre_usuario]** y **/containertrust \[nombre_usuario]**
>Permiten solo usar botones, puertas y camas, o solo abrir cofres, sin poder construir.

* **/claimslist**
>Muestra los terrenos del jugador y cuantos bloques de terreno le quedan.

* **/abandonclaim**
>Elimina el terreno donde esta parado el jugador y le devuelve los bloques.

Cuando un jugador pone su primer cofre, se protege automaticamente un area pequeña a su alrededor.

## Comandos de administracion

* **/adjustbonusclaimblocks \[nombre_usuario] \[cantidad]**
>Da (o quita, con un numero negativo) bloques de terreno extra a un jugador.

* **/adminclaims**
>Activa el modo de terrenos de administracion (protegidos, pero sin dueño). Util para el spawn.

* **/deleteclaim**
>Elimina el terreno donde esta parado el administrador.

* **/gpreload**
>Recarga la configuracion.

## Archivo de configuracion (plugins/GriefPreventionData/config.yml)

* **Claims.Mode:** Modo de cada mundo. **world: Survival** y todos los demas en **Disabled**.
* **InitialBlocks: 100** y **Claim Blocks Accrued Per Hour: 100:** Bloques de terreno al empezar y por cada hora jugada.
* **Expiration (ChestClaimDays, UnusedClaimDays, DaysInactive): 0:** Los terrenos **no vencen nunca** (por defecto se borraban tras 60 dias sin entrar).
* **BlockSurfaceCreeperExplosions** y **BlockSurfaceOtherExplosions: true:** Las explosiones no rompen bloques en la superficie.
* **FireSpreads** y **FireDestroys: false:** El fuego no se propaga ni destruye bloques.

## Bloques de terreno de los jugadores (07-nov-2026)

nachitoultra, churros5235 y Vicp360 recibieron **10.000 bloques extra** cada uno (alcanza para unos 100 x 100), para proteger lo que ya tenian construido.

>**IMPORTANTE:** GriefPrevention solo protege lo que esta dentro de un terreno. Lo construido fuera de un terreno se puede romper.

## Mundos nuevos

GriefPrevention reescribe su **config.yml** solo con los mundos cargados al arrancar. Si un mundo se importa con el servidor encendido (por ejemplo con **'/mv import'**), su linea en **Claims.Mode** puede desaparecer. Despues de importar un mundo:

* Agregar la linea en **Mode** (por ejemplo **'ooo_nether: Disabled'**).
* Ejecutar **'/gpreload'** (no hace falta reiniciar).

Los mundos del [mapa de Hora de Aventuras](../servidor/hora_de_aventuras.md) (ooo, ooo_nether y ooo_the_end) estan en **Disabled**.
