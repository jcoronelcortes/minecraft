# Plan: agregar el Nether (Nocheósfera) y el End (Espacio Grumoso) al mapa de Hora de Aventuras

Fecha: 2026-11-07 · Servidor: Paper 26.3, Multiverse-Core 5.8.2, Multiverse-Inventories 5.3.6 · Mundo actual: `ooo`

---

## 1. Qué encontré

### El Nether y el End son parte de la historia principal
El mapa no se puede terminar sin ellos. El recorrido completo es:

1. Casa del Árbol → Reino Dulce → laboratorio de la Dulce Princesa (nota del Rey Helado) → mazmorra de la Princesa Grumosa.
2. **Portal secreto al Espacio Grumoso** (portal del End en el mundo normal) → **Espacio Grumoso** (el End) → trampa del Rey Helado → **Reino de los Duendes** (mundo normal).
3. Marceline: "¡tenemos un portal en nuestra casa!" → **portal del Nether de la Casa del Árbol** → **Nocheósfera** (el Nether) → trampa → **cárcel y arena** (mundo normal) → créditos ("CONTINUARÁ").

### Portales del mapa original
| Dónde | Qué | Coordenadas |
|---|---|---|
| Mundo normal, Casa del Árbol | Portal del Nether (6 bloques) | x -1217..-1216, y 64..66, z -4847 |
| Nether (Nocheósfera) | Portal de vuelta (6 bloques) | x -151..-150, y 70..72, z -609 (es -1217/8, -4847/8: la escala normal del Nether) |
| Mundo normal, "Portal secreto al Espacio Grumoso" | Portal del End (1 bloque) | -1122, 62, -4526 |
| End (Espacio Grumoso) | Plataforma de llegada | alrededor de 100, 49, 0 (el cartel "¡Estamos en el Espacio Grumoso!" está en 97, 49, 1) |
| End | Portal de salida (1 bloque) | 200, 48, 200 |

### El truco del creador, que en 26.3 ya no funciona
En 2012 **el punto de reaparición siempre quedaba en el mundo normal**. El creador lo usaba para cambiar de mundo: un bloque de comandos en el Nether o el End fijaba la reaparición en el mundo normal, el jugador caía en una trampa y **reaparecía en la siguiente parte de la historia**.

| Bloque de comandos | Comando original | Para qué servía |
|---|---|---|
| Nether -144, 69, -590 | `/spawnpoint @a -1732 65 -537` | Al "morir" en la Nocheósfera se reaparece en la **cárcel** |
| End 97, 46, 0 | `/spawnpoint @p -1121 65 -4522` | Si se cae al vacío al llegar, se vuelve al portal secreto |
| End 30, 68, 27 | `/spawnpoint @p -1662 64 -4639` | Trampa del Rey Helado → se reaparece en el **Reino de los Duendes** |
| End 32, 68, 27 | `/tp @p -14 71 28` | Teletransporte dentro del End (sigue funcionando) |

En 26.3, `/spawnpoint` guarda **el mundo donde se ejecuta**, así que estas reapariciones caen dentro del Nether o el End y no en el mundo normal.
Esto explica los comentarios de 2013: "el portal del Nightosfera se rompió".

### Riesgo actual (antes de este plan)
El mundo `ooo` no tiene Nether ni End propios. Si tus hijos cruzan alguno de los dos portales, **probablemente terminen en el Nether o el End de supervivencia** del servidor, en modo supervivencia y quizá con el dragón.

---

## 2. Solución

1. Crear dos mundos nuevos a partir del mapa original: **`ooo_nether`** (Nocheósfera) y **`ooo_the_end`** (Espacio Grumoso).
2. Instalar **Multiverse-NetherPortals 5.1.0** (compatible con 26.3). Conecta los portales de `ooo` con `ooo_nether` y `ooo_the_end`, con la escala normal del Nether, así que se llega a los mismos puntos que en 2012.
3. **Arreglar los 3 bloques de reaparición** para que fijen la reaparición en `ooo`:
   - Nether: `execute in minecraft:ooo run spawnpoint @a -1732 65 -537`
   - End: `execute as @p in minecraft:ooo run spawnpoint @s -1121 65 -4522` y lo mismo con -1662 64 -4639
   - (`execute as @p` elige al jugador **antes** de cambiar de mundo; si no, `@p` no encuentra a nadie.)
4. **Inventario compartido** entre `ooo`, `ooo_nether` y `ooo_the_end` (grupo "ooo" de Multiverse-Inventories). Si no, al cruzar un portal el inventario cambiaría.
5. Mismas reglas que `ooo` en los dos mundos nuevos: aventura, sin PvP, fácil, bloques de comandos activos, `keep_inventory`, sin `mob_griefing` y GriefPrevention desactivado.
6. **Poner en español** los 14 carteles del Nether y del End. La traducción ya está hecha en `hora-de-aventuras/traduccion_es.py`.

---

## 3. Fases

### Fase 0 – Protección inmediata: HECHA el 07-nov 13:44
- Script: `hora-de-aventuras/proteger-portales-ooo.sh`. Respaldo previo: `minecraft-2026-11-07_134355-…`
- Se confirmó que los 2 portales existían, se quitaron y se verificó que no quedan. El chunk de la Casa del Árbol, guardado a las 13:44:21, no tiene ningún bloque de portal.
- **Para restaurarlos en la Fase 4** (el marco de obsidiana y el marco del End siguen ahí):
  - Nether: encender el portal poniendo fuego dentro del marco: `execute in minecraft:ooo run setblock -1217 64 -4847 minecraft:fire`.
    Si no se enciende: `execute in minecraft:ooo run fill -1217 64 -4847 -1216 66 -4847 minecraft:nether_portal[axis=x]`.
  - End: `execute in minecraft:ooo run setblock -1122 62 -4526 minecraft:end_portal`

Pasos originales de la Fase 0:
Para que nadie termine en el Nether o End de supervivencia mientras tanto:
- [ ] Respaldo: `sudo mc-backup.sh`
- [ ] Quitar temporalmente los 2 portales de `ooo`. Se restauran en la Fase 4.
  - `execute in minecraft:ooo run fill -1217 64 -4847 -1216 66 -4847 air replace minecraft:nether_portal`
  - `execute in minecraft:ooo run setblock -1122 62 -4526 air`
- [ ] Opcional: un cartel "Próximamente" junto a cada portal.

### Avance de las Fases 1 a 3 (07-nov, 13:55), en el servidor de prueba `~/prueba-ooo` (puerto 25566)
- Plugins: Multiverse-Core 5.8.2, Multiverse-Inventories 5.3.6, **Multiverse-NetherPortals 5.1.0** (descargado y verificado en `~/descargas-26.3/plugins/`) y AdvancedTeleport con su config real.
- Mundos: `ooo` (del respaldo real de las 13:43, ya en español y **con** sus portales), y `ooo_nether` y `ooo_the_end` (del mapa original convertido, sin `metadata.dat`).
- **Portales:** NetherPortals los conecta solo, por el nombre (`portal-auto-link-when`: sufijos `_nether` y `_the_end`). El comando `mvnp` de versiones viejas ya no existe.
- **Dragón:** el `ender_dragon_fight.dat` del End traía `dragon_killed: 0` y `needs_state_scanning: 1`, así que al cargarlo habría aparecido el dragón y se habría creado el portal de salida en 0,0, encima de las construcciones.
  Se cambió a `dragon_killed: 1`, `previously_killed: 1` y `needs_state_scanning: 0` **antes** de cargar el mundo. Se cargó el centro: **sin dragón y sin portal de salida**. Copia del original en `ender_dragon_fight.dat.original`.
- **Inventario:** grupo `ooo` con los 3 mundos, compartiendo todo, incluido `bed_spawn` (la reaparición).
- **Reapariciones arregladas** (`hora-de-aventuras/arreglar-reapariciones.txt`):
  - Nether -144, 69, -590: `execute as @a[distance=..100] in minecraft:ooo run spawnpoint @s -1732 65 -537`
  - End 97, 46, 0 y 30, 68, 27: `execute as @p in minecraft:ooo run spawnpoint @s …`
  - **Problema extra encontrado:** 2 bloques de `ooo` (-1335, 63, -4668 y -1730, 60, -542) usaban `spawnpoint @a`, que en un servidor con varios mundos **cambia la reaparición de todos los jugadores del servidor**, incluso de quien esté en supervivencia. Se limitaron a `@a[distance=..100]`. **Este arreglo también hace falta en el servidor real ya.**
- **Carteles:** los 14 del Nether y el End, en español (`comandos-espanol-nether-end.txt`).
- ~~Pendiente: recorrido con un jugador~~ → **hecho el 07-nov, 14:00–14:38, con nachitoultra.** Resultados abajo.

### Resultado de las pruebas con jugador (07-nov)
| Prueba | Resultado |
|---|---|
| Portal secreto → Espacio Grumoso | ✅ Llega a 100, 49, 0, sin dragón, con carteles en español |
| Morir con `/spawnpoint` del mapa | ❌ Siempre en la sala de inicio. **Dos causas:** |
| — Causa 1: Multiverse-Core | `enforce-respawn-at-world-spawn: true` obliga al spawn del mundo. **Con `false` funciona** (probado sin AdvancedTeleport) |
| — Causa 2: AdvancedTeleport | Ignora `/spawnpoint` y manda al spawn del mundo aunque se cambie a `bed`, a un valor desconocido o a `use-spawn: false`. No se puede apagar esa parte |
| **Solución elegida: opción A** | Transiciones con **teletransporte directo** y **puntos de control de AdvancedTeleport** (`puntos_control_ooo.py`) |
| Morir en ooo → punto más cercano | ✅ Con `teleport-to-nearest-spawnpoint: true` y `ooo: spawn`. **Requiere permiso a los spawns** (sin permiso manda al spawn principal); en la prueba se usó OP, en el real va `at.member.spawn.*` con LuckPerms |
| Trampa del Rey Helado (End 30, 68, 27) | ✅ Ahora `execute as @p in minecraft:ooo run tp @s -1661.5 64 -4638.5` |
| Morir en el End → portal secreto | ✅ `ooo_the_end: warp:ooo_portal_secreto` |
| Portal de la Casa del Árbol → Nocheósfera | ✅ Llega a -150, 70, -608.5 (portal del mapa) |
| Morir en la Nocheósfera → cárcel | ✅ `ooo_nether: warp:ooo_carcel` |

### Fase 4: INSTALADA en el servidor real el 07-nov, 14:42
- Script `hora-de-aventuras/instalar-nether-end-ooo.sh`. Respaldo previo: `minecraft-2026-11-07_144140-…`
- Verificado: los 14 mundos cargados, incluidos `ooo_nether` y `ooo_the_end`; grupo de inventario `ooo` con los 3; portales del Nether y del End encendidos en `ooo`; **sin dragón**; trampa del Rey Helado como teletransporte; los 2 bloques `@a` de `ooo` corregidos; LuckPerms `at.member.spawn.*` y `at.member.warp.*` en default; ningún plugin falló.
- **Pendiente:** que los niños jueguen la historia completa en el servidor real; documentar en GitHub; borrar `~/prueba-ooo`.

### Cambios necesarios en el servidor real (Fase 4)
1. Respaldo con el servidor apagado.
2. Copiar `ooo_nether` y `ooo_the_end` desde la prueba (End con el `ender_dragon_fight.dat` ya corregido; los 14 carteles en español).
3. Instalar `multiverse-netherportals-5.1.0.jar`.
4. **Multiverse-Core:** `enforce-respawn-at-world-spawn: false` (en la prueba no cambió nada en los otros mundos; AdvancedTeleport sigue manejando sus reapariciones con `bed;spawn`).
5. **AdvancedTeleport:** ejecutar `puntos_control_ooo.py`: 14 spawns, 2 warps, `death-management` de los 3 mundos y `teleport-to-nearest-spawnpoint: true`.
   - Efecto en el resto del servidor: `/spawn` y la entrada al servidor llevan al spawn más cercano **del mismo mundo**. Los otros mundos tienen un solo spawn, así que no cambia nada; en `ooo`, `/spawn` lleva al punto de control más cercano.
   - Los 2 warps nuevos (`ooo_carcel` y `ooo_portal_secreto`) aparecen en la lista de `/warps`, pero no en el menú de botones.
6. **LuckPerms:** `lp group default permission set at.member.spawn.* true` (permiso para reaparecer en los puntos de control).
7. Importar los mundos, configurarlos (aventura, PvP, dificultad, reglas) y crear el grupo de inventario `ooo` con los 3 mundos.
8. Bloques de comandos: los 5 de `arreglar-reapariciones.txt` y la trampa del Rey Helado como teletransporte.
9. Restaurar los 2 portales de `ooo` (Fase 0).

### Fase 1 – Servidor de prueba (sin tocar el real)
- [ ] Volver a armar `~/prueba-ooo`, igual que la vez anterior: con tu usuario, sin sudo, puerto 25566.
- [ ] Usar el mapa original de `~/descargas-mapas/` para obtener el Nether y el End convertidos.
- [ ] Copiar el mundo `ooo` **del servidor real**, que ya tiene los comandos traducidos y el español.
- [ ] Instalar Multiverse-Core, Multiverse-Inventories y **Multiverse-NetherPortals 5.1.0**.

### Fase 2 – Armar y conectar los mundos (en la prueba)
- [ ] Copiar `the_nether` y `the_end` convertidos como `ooo_nether` y `ooo_the_end`, sin su `data/paper/metadata.dat`, como se aprendió con `ooo`.
- [ ] `mv import ooo_nether nether` y `mv import ooo_the_end the_end`.
- [ ] Conectar los portales (si NetherPortals no los conecta solo por el nombre):
  `mvnp link nether ooo ooo_nether`, `mvnp link end ooo ooo_the_end` y los enlaces de vuelta.
- [ ] Configurar los mundos (aventura, PvP, dificultad, reglas) e inventario compartido:
  `mvinv create-group ooo` y `mvinv add-worlds ooo ooo,ooo_nether,ooo_the_end`.
- [ ] **Revisar el dragón:** el End de 2012 no tiene registrada la pelea del dragón. Hay que confirmar que en 26.3 no aparezca un dragón en el Espacio Grumoso y, si aparece, desactivarlo antes de seguir.

### Fase 3 – Arreglar las transiciones y probar (en la prueba)
- [ ] Cambiar los 3 bloques de reaparición (sección 2.3).
- [ ] Aplicar los 14 carteles en español del Nether y del End, apuntando a `ooo_nether` y `ooo_the_end`.
- [ ] Revisar que **Multiverse** y **AdvancedTeleport** (`death-management: bed;spawn`) respeten la reaparición fijada con `/spawnpoint` y no manden al spawn del mundo. Si no la respetan, reemplazar la "muerte" por un teletransporte directo: `execute as @p in minecraft:ooo run tp @s x y z`.
- [ ] Recorrido de prueba, con coordenadas:
  1. Entrar al portal secreto → llegar a la plataforma del Espacio Grumoso en modo aventura.
  2. Caer en la trampa → reaparecer en el Reino de los Duendes (-1662, 64, -4639).
  3. Entrar al portal de la Casa del Árbol → llegar a la Nocheósfera (-150, 70, -606).
  4. Pisar el cable trampa → reaparecer en la cárcel (-1732, 65, -537).
  5. Volver por el portal del Nether → llegar a la Casa del Árbol.
  6. Revisar que el inventario sea el mismo en los tres mundos y distinto del resto del servidor.

### Fase 4 – Instalar en el servidor real
- [ ] Respaldo con el servidor apagado: `sudo mc-backup.sh --stop --no-start`
- [ ] Copiar `ooo_nether` y `ooo_the_end` probados al servidor e instalar Multiverse-NetherPortals.
- [ ] Encender, importar, conectar y configurar, igual que en la prueba, con un solo script como `instalar-mundo-ooo.sh`.
- [ ] Restaurar los 2 portales de `ooo` quitados en la Fase 0.
- [ ] Aplicar los 3 arreglos de reaparición en los mundos reales.
- [ ] Verificar con `mv list`, `mvnp show` (o equivalente) y `mvinv info ooo`.

### Fase 5 – Con los niños
- [ ] Que jueguen la historia completa y avisen dónde se traban, con coordenadas (F3).

### Fase 6 – Documentar y limpiar
- [ ] Actualizar `servidor/actualizacion_26_3.md` y agregar la página del mundo `ooo` en GitHub.
- [ ] Borrar `~/prueba-ooo` otra vez.

---

## 4. Riesgos

| Riesgo | Qué hacer |
|---|---|
| Aparece el dragón en el Espacio Grumoso | Detectarlo en la Fase 2 y desactivar la pelea antes de instalar |
| Multiverse o AdvancedTeleport ignoran el `/spawnpoint` al reaparecer | Cambiar la "muerte" por un teletransporte directo (Fase 3) |
| NetherPortals conecta `ooo` con otro Nether | Fijar los enlaces a mano con `mvnp link` y probar los dos sentidos |
| Inventarios distintos al cruzar portales | Grupo "ooo" de Multiverse-Inventories con los 3 mundos |
| Algo sale mal en el servidor real | `sudo mc-restore.sh ultimo` |

## 5. Tiempo estimado
| Fase | Tiempo |
|---|---|
| 0 | 5 minutos (una contraseña) |
| 1 y 2 | 1 hora |
| 3 | 1 a 2 horas, según cuánto cueste el dragón y las reapariciones |
| 4 | 30 minutos (una contraseña) |
| 5 y 6 | Lo que tarden en jugar, más 20 minutos |
