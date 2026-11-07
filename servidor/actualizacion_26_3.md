# Actualizacion a Paper 26.3 (6 y 7 de noviembre de 2026)

## Resumen

* Paper **26.2 → 26.3** (build 244), Java 25.
* Plugins actualizados y ProtocolLib retirado.
* Servidor en **modo online** (solo cuentas premium) y **sin nLogin**.
* LuckPerms reinstalado y funcionando.
* Scripts de respaldo y restauracion ([Respaldos](respaldos.md)).

## Versiones de plugins

| Plugin | Antes | Ahora | Nota |
|---|---|---|---|
| ViaVersion / ViaBackwards | 5.11.0 | 5.12.2 | |
| FastAsyncWorldEdit | 2.15.5-SNAPSHOT | 2.16.2 | |
| WorldGuard | 7.0.17 | **7.0.20** | La 7.0.21 no funciona con FAWE 2.16.2 |
| Multiverse-Core | 5.7.3 | 5.8.2 | |
| TAB | 6.1.2 | 6.2.1 | |
| EconomyShopGUI | 7.1.1 | 7.3.4 | |
| zMenu | 1.1.1.6 | 1.1.2.1 | |
| MiniMOTD | 2.2.4 | 2.2.5 | Descargar desde Modrinth (en Spigot esta desactualizado) |
| ItemEdit | 3.7.10 | 4.0.0 | |
| ConditionalEvents | 4.79.2 | 4.80.3 | |
| EasyCommandBlocker | 1.18.1 | 1.19.1 | |
| PetBlocks | 9.31.0 | 9.32.0 | Descargar desde GitHub (Shynixn/PetBlocks) |
| LuckPerms | (no estaba) | 5.5.71 | |
| ProtocolLib | 5.4.0 | **retirado** | Sin version estable para 26.3 |
| nLogin | 2.0.19 | **retirado** | Ver mas abajo |
| AdvancedTeleport, XConomy, Vault, FlyPlus, VoidTeleport, WorldGuardEvents, PlaceholderAPI, SkinsRestorer | – | sin cambios | Funcionan en 26.3 |

## Problemas encontrados y como se resolvieron

### Bloque de comandos con /setmainspawn
Un bloque de comandos en modo repeticion en **world 120 88 199** ejecutaba **'setmainspawn piglinbrute'** en cada tick y fallaba siempre
(miles de errores por dia en el log). Se quito con **'/forceload add 120 199'**, **'/setblock 120 88 199 minecraft:air'** y **'/forceload remove 120 199'**.
El comando **/setmainspawn** se ejecuta a mano, una sola vez, parado en el lugar.

### WorldGuard 7.0.21
Fallaba al iniciar con FAWE 2.16.2 (**NoSuchMethodError: YAMLProcessor(Path, ...)**). Se uso la 7.0.20.

### PetBlocks
Las mascotas guardadas en 26.2 con el componente **minecraft:swing_animation** (que no existe en 26.3) no cargaban,
y PetBlocks las guardaba con la cabeza por defecto. Se quito ese componente de la base **plugins/PetBlocks/PetBlocks.sqlite**.

### LuckPerms y nLogin
Con **online-mode=true** y nLogin aceptando jugadores no premium, el ID de los jugadores cuyo nombre existe como cuenta premium cambiaba durante el ingreso.
El servidor usaba primero el ID de Mojang y despues nLogin lo cambiaba al ID offline, y LuckPerms los expulsaba con
*"Permissions data for your user was not loaded during the pre-login stage"*. Esto pasaba desde el 24-jul-2026
(el servidor habia pasado de offline a online a inicios de julio), y por eso se habia retirado LuckPerms el 23-ago.

**Solucion:** como todos los jugadores tienen cuenta oficial de Microsoft, se paso a **online-mode=true sin nLogin**. Mojang verifica a cada jugador
y el ID es el mismo en todo el ingreso.

## Cambio de ID de los jugadores

Al pasar a modo online, cada jugador usa su ID oficial de Mojang. Sus datos se migraron del ID offline al premium:

| Jugador | ID offline (antes) | ID premium (ahora) |
|---|---|---|
| nachitoultra | de2233b4-4bc6-3dbd-b491-4e394d4d202e | 55c6185b-948f-4793-9153-8422167cb6da |
| churros5235 | dfac8e27-1aee-342b-bf43-763a007cd40e | c5ace10c-77fb-45a0-987c-da3bf1985051 |
| Vicp360 | e7e1a09c-7e89-3583-978d-45862a3e02a5 | f9c23a09-96ce-487a-8eaa-e8200cba73e6 |

Datos que hay que migrar si alguna vez cambia el ID de un jugador:

* **world/players/data/\[id].dat** (inventario y posicion), **world/players/stats/\[id].json**, **world/players/advancements/\[id].json**
* **plugins/XConomy/playerdata/data.db** (dinero)
* **plugins/AdvancedTeleport/data.db** (jugadores, spawns y warps)
* **plugins/PetBlocks/PetBlocks.sqlite** (mascotas)
* **plugins/zMenu/database.db**
* **plugins/EconomyShopGUI/transactions/transactions.db** (historial de compras)
* **plugins/LuckPerms/** (rangos; se cambian con comandos **/lp user**)
* **ops.json**, **whitelist.json**

## Spawns

nLogin manejaba los spawns de entrada. Ahora los maneja **AdvancedTeleport** (ver [Advance Teleport](../plugins/advance_teleport.md)):
**teleport-to-spawn-on-first-join: true** y **teleport-to-spawn-on-every-join: true**, con el spawn **world** en 125.5, 64, 183.9.
