# Plan: instalar "Adventure Time Adventure Map" (aaronDAYTON)

Fecha: 2026-11-07
Servidor: Paper 26.3, en modo online con lista blanca, Multiverse 5.8.2

---

## Avance al 07-nov-2026, 12:05

| Fase | Estado |
|---|---|
| 1. Descarga | **Hecha.** Enlace oficial del creador en MediaFire: `Adventure Time Adventure Map!.zip`, 46,93 MB, subido el 31-dic-2012. SHA-256 `d421f6537ec4fb612fb23e17a4845e18d22bcc23e5d57151cf50f370ade885e3`. Guardado en `~/descargas-mapas/` |
| Revisión del ZIP | **Limpio:** solo datos de mundo (67 `.mca`, `level.dat`), el paquete de texturas de 2012 (`.png`) y textos. Ningún ejecutable. El "MCPatcher" que pide el README es de 2012 y **no se instala** |
| 2. Servidor de prueba | **Funcionando** en `~/prueba-ooo`, con tu usuario (sin sudo), puerto **25566**, modo online, lista blanca de los 3 jugadores y modo aventura. Iniciar: `bash ~/prueba-ooo/iniciar-prueba.sh`. Detener: `bash ~/prueba-ooo/detener-prueba.sh` |
| Conversión | Paper 26.3 **no** tiene `--forceUpgrade`. El mundo se migró al arrancar ("WorldFolderMigration") y los chunks se convierten al cargarse. Sin errores |
| Bloques de comandos | **121 encontrados** (`hora-de-aventuras/bloques-de-comandos-mapa.json`). 64 siguen funcionando igual (`tp`, `say`, `spawnpoint`, `clear`) |
| 3. Traducción | **57 traducidos** en la copia de prueba con `hora-de-aventuras/traducir_comandos.py`: 41 `give` con IDs numéricos, 9 `xp`, 5 `tell` con selectores viejos y 2 `difficulty`. Los 38 comandos distintos resultantes son válidos en 26.3 |
| Primera conexión | **12:27:** nachitoultra entró desde el Mac (192.168.4.156) y apareció en -90, 68, 252, el inicio del mapa |
| Problemas de conexión resueltos | Desde la casa hay que usar la IP local `192.168.4.145:25566`: el router solo redirige el 25565 (`la dirección del servidor`). En el Mac, Minecraft necesitaba el permiso **Ajustes del Sistema → Privacidad y seguridad → Red local**. El firewall (ufw) está inactivo; se agregó igual la regla `allow from 192.168.4.0/22 to any port 25566`, que se puede borrar al terminar |
| Avisos del log | `Failed to read field (block_ticks=…)` y `Serialization errors`: actualizaciones pendientes de bloques de 2012 que se descartan. Inofensivos |
| Ensayos en la prueba | `mv import` funciona si antes se borra `data/paper/metadata.dat` de la copia (si no: "duplicate of another world"). `/difficulty` en 26.3 cambia **solo el mundo** donde se ejecuta, así que los 2 bloques del mapa no afectan a otros mundos |
| **4. Instalado en el servidor real (12:40)** | Mundo **"ooo"**: aventura, sin PvP, fácil, `command_blocks_work`, `keep_inventory` y sin `mob_griefing`. Spawn -100, 64, 252. Warp `ooo` y botón **Tierra de Ooo** (pastel) en el espacio 20 de `/warps`. GriefPrevention desactivado en ooo. Script: `hora-de-aventuras/instalar-mundo-ooo.sh`. Respaldo previo: `minecraft-2026-11-07_123857-…` |
| Multiverse-Inventories 5.3.6 | Instalado. Todos los mundos que ya existían siguen **compartiendo** inventario (grupo `default`), como antes. **"ooo" tiene inventario propio**: lo que den las misiones no sale del mapa, y al volver cada uno recupera sus cosas |
| No incluido | El Nether (Nightosfera) y el End del mapa, que necesitarían Multiverse-NetherPortals. El portal al Nightosfera ya fallaba en 2012-2013 |
| Español (07-nov, 13:00) | Textos traducidos: 302 carteles (288 instalables; los del Nether y End no están en el servidor), 17 mensajes de bloques de comandos y 3 libros. Traducción en `hora-de-aventuras/traduccion_es.py`, para revisar en `textos-en-espanol.md`. **Probado en el servidor de prueba.** Para el real: `sudo bash hora-de-aventuras/aplicar-espanol.sh` |
| Lecciones | La consola de Paper **no acepta `§`**: los colores se escriben como componentes (`{text:'…',color:'dark_aqua'}`). Los comandos muy largos se cortan al enviarlos por screen, así que el libro de reglas se arma página por página |
| Español en el servidor real | **Aplicado el 07-nov 13:12**: 317 cambios (288 carteles + 17 mensajes + 12 páginas) y 3 libros. Respaldo previo: `minecraft-2026-11-07_131124-…` |
| **Siguiente** | Que los niños jueguen y avisen qué misiones fallan (con coordenadas, F3). Después: documentar en GitHub. (`~/prueba-ooo` borrado el 07-nov; la regla de ufw del 25566 la quita el usuario) |

Avisos para la Fase 4:
- **`/difficulty`:** el mapa lo usa en 2 bloques (en la sala de oleadas, cerca de -1708, 62, -531). En el servidor real, la dificultad podría cambiar **en todos los mundos**. Hay que probar si en 26.3 afecta solo al mundo donde se ejecuta y, si no, reemplazar esos 2 bloques.
- **Objetos de 64:** varios `give` entregan 64 espadas de diamante o pociones de daño (así está hecho el mapa). Con un solo inventario para todos los mundos, eso se puede llevar a supervivencia. Otra razón para Multiverse-Inventories.

---

## Lo que hay que saber antes

| Dato | Detalle |
|---|---|
| Página original | https://www.planetminecraft.com/project/adventure-time-adventure-map-1601112/ (Planet Minecraft, del propio creador) |
| Fecha | 28-dic-2012 |
| Versión para la que se hizo | **Minecraft 1.4.7** (el creador pide "1.4.7+") |
| Contenido | Tierra de Ooo (Casa del Árbol, Dulce Reino, etc.) y misiones de episodios: *They Went to the Nightosphere*, *Beautopia*, *Trouble in Lumpy Space*, y misiones secundarias |
| Cómo funciona | **Bloques de comandos** (teletransportes, entrega de objetos) y un **paquete de texturas** de Leonel ("Adventure Time Craft") |
| Problemas conocidos (comentarios del mapa) | El portal al Nightosfera dejó de funcionar en versiones nuevas; un jugador dijo que el mapa "se rompió hacia el final" |

> **No usar 9minecraft.** Muestra el mapa como "26.3", pero lo etiqueta en todas las versiones desde 1.4.7 hasta 26.3, o sea, no lo probó.
> Además ese sitio tiene publicidad engañosa. El mapa se baja **solo** del enlace "DOWNLOADABLE MAP" de la página de Planet Minecraft.

### Qué esperar en Paper 26.3
- **El mundo (las construcciones) sí debería verse bien.** Minecraft convierte solo los mundos viejos al abrirlos.
- **Muchas misiones probablemente no funcionen.** Los comandos de 2012 usan formatos que ya no existen: números en vez de nombres de bloques y objetos (`/give @p 276`), selectores y `/testfor` viejos, etc.
  Minecraft **no** actualiza el texto que está dentro de los bloques de comandos.
- **El paquete de texturas de 2012 no sirve** en 26.3, porque el formato de los paquetes cambió en 1.6 y varias veces después.

**Conclusión:** sirve como **mundo para explorar la Tierra de Ooo**. Las misiones habrá que probarlas una por una y arreglar o desactivar las que fallen.

---

## Decisión: ¿en el servidor o en el computador de los niños?

| Opción | Ventajas | Desventajas |
|---|---|---|
| **A. Un jugador, en el Minecraft de los niños** (carpeta `saves`) | Es como el creador lo pensó. Fácil. No toca el servidor | Juegan por separado, salvo que uno abra el mundo "en LAN" |
| **B. Mundo nuevo "ooo" en el servidor** | Juegan juntos y con sus amigos. Con respaldos | Más trabajo. Hay que configurar el mundo para que nadie rompa el mapa |

**Recomendación:** primero la **opción A** como prueba rápida, en el computador de los niños, para ver cuánto del mapa funciona en 26.3.
Si les gusta, pasamos a la **opción B** siguiendo este plan.

---

## Fase 0 – Preparación (opción B)
- [ ] Respaldo completo: `sudo mc-backup.sh --stop`
- [ ] Espacio en disco: hoy hay **43 GB libres (91 % usado)**. El mapa debería ocupar menos de 1 GB, pero hay que confirmarlo al descargarlo.

## Fase 1 – Descarga segura
- [ ] Descargar el ZIP **solo** desde el enlace "DOWNLOADABLE MAP" de la página de Planet Minecraft.
- [ ] Guardarlo en una carpeta aparte, por ejemplo `~/descargas-mapas/`.
- [ ] Revisar el contenido **sin ejecutar nada** (`unzip -l`). Tiene que tener solo archivos de mundo: `level.dat`, carpeta `region/`, `data/`, quizá `DIM-1`, `DIM1` y el paquete de texturas.
  Si trae `.exe`, `.jar`, `.bat`, `.sh` o similares, **no se usa**.
- [ ] Anotar el tamaño y la suma SHA-256 del ZIP.

## Fase 2 – Prueba en un servidor aparte (sin tocar el real)
Abrir un mundo de 2012 con 26.3 lo convierte de forma permanente, así que primero se prueba en una copia.
- [ ] Crear un servidor de prueba mínimo en `/home/papermc/prueba-ooo`, con el mismo `paper-26.3` jar, sin plugins, en el puerto **25566**, con `online-mode=true` y lista blanca solo con los niños.
- [ ] Usar el mapa como mundo principal de ese servidor y arrancarlo una vez con `--forceUpgrade`, para convertir todo el mundo de una vez y no por partes mientras se juega.
- [ ] Revisar el log por errores de conversión.
- [ ] Entrar con un niño y recorrer:
  - [ ] el punto de inicio y la primera misión;
  - [ ] la Casa del Árbol y el Dulce Reino;
  - [ ] el portal del Nightosfera (problema conocido);
  - [ ] lo que entregan los bloques de comandos (objetos, teletransportes).
- [ ] Anotar qué funciona y qué no, en una tabla misión por misión.

## Fase 3 – Arreglar lo que falle (opcional, según la Fase 2)
- [ ] Buscar los bloques de comandos del mapa con un script que lea los archivos de región, igual que se hizo con el bloque de `/setmainspawn`, y listar sus comandos.
- [ ] Traducir los comandos viejos al formato nuevo. Por ejemplo, `give @p 276 1` pasa a `give @p minecraft:diamond_sword 1`, y `tp @p x y z` en general sigue funcionando.
- [ ] Aplicar los cambios en la copia de prueba y volver a probar.
- [ ] Si una misión no tiene arreglo razonable, dejarla como "solo para explorar".

## Fase 4 – Instalar en el servidor real
- [ ] Respaldo: `sudo mc-backup.sh --stop --no-start`
- [ ] Copiar el mundo convertido y probado como mundo nuevo **"ooo"** con Multiverse (`mv import`).
  Hay que confirmar en la prueba cómo importa Multiverse 5 un mundo en 26.3, porque los mundos ahora viven en `world/dimensions/`.
- [ ] Configurar el mundo con Multiverse:
  - `gamemode adventure`: en modo aventura no se pueden romper bloques, así el mapa no se destruye.
  - `pvp false`, `difficulty easy` (o la que pida el mapa) y `hunger` según el mapa.
- [ ] Reglas solo para ese mundo:
  - `execute in minecraft:ooo run gamerule command_blocks_work true`: en 26.3 los bloques de comandos se activan mundo por mundo.
  - `keep_inventory true`, para que no pierdan los objetos de las misiones.
  - `mob_griefing false`.
- [ ] GriefPrevention: dejarlo **desactivado** en "ooo" (`ooo: Disabled`), porque el modo aventura ya protege el mapa.
- [ ] WorldGuard (opcional): región global de "ooo" con `build deny`, como protección extra.
- [ ] Warp "ooo" y botón **"Tierra de Ooo"** en el menú `/warps` (zMenu), igual que se hizo con el mundo creativo.
- [ ] EasyCommandBlocker: confirmar que lo que usa el mapa funcione con `use_commands_as_whitelist`. Los bloques de comandos los ejecuta el servidor, así que en principio no les afecta, pero hay que probarlo.
- [ ] Inventario: el mapa entrega objetos de misión que se podrían llevar a otros mundos. Si molesta, instalar Multiverse-Inventories, previa revisión de que tenga versión para 26.3.

## Fase 5 – Texturas (opcional)
- [ ] Buscar una versión actualizada del paquete "Adventure Time Craft" o de otro paquete de Hora de Aventuras para Java 26.x en Planet Minecraft.
- [ ] El paquete del servidor (`resource-pack` en `server.properties`) se aplica a **todos** los mundos, no solo a "ooo".
  Lo más simple es que cada niño lo instale en su Minecraft y lo active cuando juegue el mapa.

## Fase 6 – Pruebas con los niños
- [ ] Entran por el menú `/warps`, botón Tierra de Ooo.
- [ ] Juegan las misiones que funcionaron en la Fase 2.
- [ ] No pueden romper el mapa (modo aventura).
- [ ] Al volver a otros mundos, el modo de juego cambia solo (Multiverse `enforce-gamemode`).
- [ ] Si algo sale mal: `sudo mc-restore.sh ultimo` o borrar solo el mundo "ooo".

## Fase 7 – Documentar
- [ ] Agregar `plugins/multiverse_core.md` y una página nueva `servidor/mundo_ooo.md` en el repositorio de GitHub, con qué funciona y qué no del mapa.

---

## Estimación
| Fase | Tiempo aproximado |
|---|---|
| Opción A (prueba en el Minecraft de los niños) | 15 minutos |
| Fases 0 a 2 (descarga y prueba en servidor aparte) | 1 hora |
| Fase 3 (arreglar comandos) | Depende de cuántos fallen: de 1 a varias horas |
| Fases 4 a 7 | 1 hora |

## Fuentes
- Página original del mapa: https://www.planetminecraft.com/project/adventure-time-adventure-map-1601112/
- PC Gamer, lista de mejores mapas (indica versión 1.4.7 y enlaza a Planet Minecraft): https://www.pcgamer.com/the-25-best-minecraft-custom-maps/
