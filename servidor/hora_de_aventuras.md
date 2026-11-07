# Hora de Aventuras en el servidor

Contenido de la serie **Hora de Aventuras** (Adventure Time) instalado el 07-nov-2026 para que jueguen los niños.
Los scripts usados estan en el computador en **'~/Escritorio/projecto-minecraft/hora-de-aventuras'** (archivo **LEEME.md**).

## 1. Mascotas (PetBlocks)

En el juego: **'/mascotas'** → **Apariencia** → boton **Hora de Aventuras** (cabeza de BMO).

Hay 10 personajes: Finn, Jake, BMO, Marceline, Dulce Princesa, Fionna, Cake, Rey Helado, Princesa Grumosa y Princesa Flama. Al hacer click, la mascota toma la apariencia del personaje.

* Menu: **'plugins/PetBlocks/gui/petblocks_skins_ooo_menu.yml'**. El boton se agrego al final de **'petblocks_skins_menu.yml'**.
* Permiso: **'petblocks.gui.petblocks_skins_ooo_menu'** en el grupo **vip+** (constructor lo hereda).
* Las texturas de las cabezas son de la base de datos de cabezas de CraftMC.
* Despues de cambiar el menu: **'petblocksgui reload'**.
>**NOTA:** **'petblocks reload'** falla al recargar los menus por un error interno de PetBlocks.

## 2. Skins (SkinsRestorer)

Cualquier jugador puede ser Finn, Jake, etc.:

* **/skins:** menu con skins sugeridas.
* **/skin set \[nombre_jugador]:** copia la skin de otra cuenta.
* **/skin url \[enlace_imagen_png]:** usa una skin descargada de una pagina de skins.
* **/skin clear:** vuelve a la skin propia.

Hay que esperar 30 segundos entre cambios. Los comandos estan permitidos en [Easy Command Blocker](../plugins/easy_command_bloquer.md).

## 3. Objetos tematicos

Con los jugadores **conectados**, desde el computador:

* **'sudo bash ~/Escritorio/projecto-minecraft/hora-de-aventuras/dar-objetos-ooo.sh'** (sin argumentos se entregan a nachitoultra y churros5235; tambien se puede indicar otro jugador).

Entrega: Espada de Finn, Gorro de Finn, Hacha-Bajo de Marceline, Corona del Rey Helado, Cabeza de BMO y Peluche de Jake. Las armas y armaduras son irrompibles.

Los jugadores del grupo constructor tambien pueden crear sus objetos con [Item Edit](../plugins/item_edit.md) sosteniendo un objeto en la mano:

* **/ie rename &6Espada de Finn**
* **/ie lore add &bEs hora de aventuras!**

## 4. Mapa "Adventure Time Adventure Map" (mundo **ooo**)

Mapa de aventura creado por **aaronDAYTON** en 2012 para Minecraft 1.4.7, publicado en Planet Minecraft (descarga en MediaFire).
SHA-256 del zip descargado: **'d421f6537ec4fb612fb23e17a4845e18d22bcc23e5d57151cf50f370ade885e3'**.

Se entra desde el menu **/warps** → boton **Tierra de Ooo** (cabeza de pastel), o con **'/warp ooo'**.

### Mundos del mapa

| Mundo | Que es | Tipo |
|---|---|---|
| **ooo** | Tierra de Ooo (mundo principal del mapa) | normal |
| **ooo_nether** | Nocheosfera (la carcel de Marceline) | nether |
| **ooo_the_end** | Espacio Grumoso | the_end |

Los 3 mundos:

* Modo **aventura**, sin PvP, dificultad **facil**.
* gamerules: **keep_inventory true**, **mob_griefing false**, **command_blocks_work true**.
* GriefPrevention **desactivado** (el mapa usa bloques de comandos y no se debe construir en el).
* Comparten su propio inventario (grupo **ooo** de [Multiverse-Inventories](../plugins/multiverse_inventories.md)): lo que se gana en el mapa no se mezcla con la supervivencia.
* Los portales se enlazan solos con [Multiverse-NetherPortals](../plugins/multiverse_netherportals.md) por los sufijos **_nether** y **_the_end**.

### Portales

* **Nocheosfera:** portal del Nether en la Casa del Arbol (ooo, x -1217..-1216, y 64..66, z -4847).
* **Espacio Grumoso:** portal del End secreto (ooo, -1122, 62, -4526).
* En el Espacio Grumoso **no hay dragon**: se marco como derrotado en **'ender_dragon_fight.dat'** (dragon_killed=1, previously_killed=1, needs_state_scanning=0).

### Instalacion y actualizacion de comandos

El mapa es de una version muy antigua, por lo que se tradujeron **57 comandos** de los bloques de comandos a la sintaxis de Paper 26.3:

* IDs numericos de bloques e items → nombres (por ejemplo **'minecraft:diamond_sword'**).
* **'xp 5l'** → **'xp add @p 5 levels'**.
* Selectores **'[lm=]'** y **'[l=]'** → **'level='**.
* **'difficulty 0/1'** → **'difficulty peaceful/easy'**.
* En multimundo se usa **'@a[distance=..100]'** o **'execute in minecraft:ooo'**, para no afectar a jugadores en otros mundos.

### Traduccion al español

Todo el mapa quedo en español:

* 302 carteles.
* 17 mensajes de bloques de comandos.
* 3 libros.

Los textos estan en **'traduccion_es.py'** y se aplican con **'aplicar-espanol.sh'**.

### Reapariciones y puntos de control (opcion A)

El mapa original de 2012 cambiaba al jugador de lugar con **/spawnpoint** y luego lo hacia morir. En Paper con Multiverse y AdvancedTeleport eso no funcionaba, por lo que se cambio a:

* Teletransportes directos donde el mapa usaba **/spawnpoint + muerte** (por ejemplo, la trampa del Rey Helado en el Espacio Grumoso ahora lleva directo al Reino de los Duendes).
* **14 spawns** de [AdvancedTeleport](../plugins/advance_teleport.md) en los puntos de control del mapa. Al morir en ooo se reaparece en el **mas cercano**.
* Al morir en la **Nocheosfera** se reaparece en la carcel (warp **ooo_carcel**).
* Al morir en el **Espacio Grumoso** se reaparece en el portal secreto (warp **ooo_portal_secreto**).

| Punto de control | x, y, z (mundo ooo) |
|---|---|
| ooo_inicio | -100.5, 64, 252.5 |
| ooo_mazmorra_grumosa | -817.5, 102, -4320.5 |
| ooo_casa_arbol | -1216.5, 64, -4843.5 |
| ooo_taberna | -1394.5, 58, -4731.5 |
| ooo_casa_marceline | -1480.5, 42, -4708.5 |
| ooo_sotano_castillo | -1349.5, 52, -4688.5 |
| ooo_laboratorio | -1366.5, 80, -4688.5 |
| ooo_casa_vecino | -1333.5, 66, -4668.5 |
| ooo_reino_duendes | -1661.5, 64, -4638.5 |
| ooo_duendes_camino | -1739.5, 51, -4661.5 |
| ooo_duendes_bodega | -1733.5, 41, -4625.5 |
| ooo_portal_secreto | -1120.5, 65, -4521.5 |
| ooo_carcel | -1731.5, 65, -536.5 |
| ooo_carcel_pasillo | -1707.5, 65, -555.5 |

## 5. Scripts (en '~/Escritorio/projecto-minecraft/hora-de-aventuras')

| Script | Que hace |
|---|---|
| instalar-mundo-ooo.sh | Instala el mundo ooo, el warp y el boton en /warps |
| traducir_comandos.py | Traduce los comandos antiguos del mapa |
| traduccion_es.py / generar_espanol.py / aplicar-espanol.sh | Traduccion al español de carteles, mensajes y libros |
| proteger-portales-ooo.sh | Quita los portales de ooo (se uso antes de instalar el Nether y End) |
| instalar-nether-end-ooo.sh | Instala la Nocheosfera y el Espacio Grumoso |
| puntos_control_ooo.py | Crea los 14 spawns, los 2 warps y el death-management de AdvancedTeleport |
| arreglar-reapariciones.txt | Comandos que corrigen los bloques de comandos de reaparicion |
| dar-objetos-ooo.sh | Entrega los objetos tematicos |

Todos los scripts hacen un respaldo antes de cambiar algo. Para volver atras: **'sudo mc-restore.sh ultimo'** (ver [Respaldos](respaldos.md)).

## 6. Lecciones aprendidas

* La consola de Paper **no acepta el simbolo §** para colores: hay que usar componentes de texto, por ejemplo **{text:'Hola',color:'dark_aqua'}**.
* **screen** interpreta las barras invertidas: un salto de linea se escribe **'\\\\n'**, y los comandos muy largos se cortan (hay que dividirlos).
* Para copiar un mundo (dimension) de otro servidor se debe borrar **'data/paper/metadata.dat'** antes de **'mv import'**.
* Multiverse con **enforce-respawn-at-world-spawn: true** ignora el **/spawnpoint**; debe quedar en **false**.
* AdvancedTeleport reemplaza las reapariciones y los jugadores necesitan permiso a los spawns (**at.member.spawn.\***).
* En Paper 26.3 las gamerules se escriben en snake_case (**keep_inventory**) y son por mundo: **'execute in minecraft:ooo run gamerule ...'**.
* En macOS, Minecraft necesita el permiso de **Red local** (Ajustes del Sistema → Privacidad y seguridad) para conectarse a un servidor de la casa.
