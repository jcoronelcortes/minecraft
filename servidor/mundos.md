# Mundos del servidor

Los mundos se gestionan con [Multiverse-Core](../plugins/multiverse_core.md). En Paper 26.3 estan en **'world/dimensions/minecraft/\[nombre_mundo]'**.

| Mundo | Uso | GriefPrevention | Inventario |
|---|---|---|---|
| world (+ nether y end) | Mundo principal (supervivencia) | Activo | default |
| compadres (+ nether y end) | Supervivencia | Desactivado | default |
| naciones | Construcciones | Desactivado | default |
| CropCircle, LuckySkyWars, ParkourHelix | Mini juegos | Desactivado | default |
| creativo | Mundo plano para construir en creativo | Activo | default |
| ooo, ooo_nether, ooo_the_end | [Mapa de Hora de Aventuras](hora_de_aventuras.md) | Desactivado | ooo |

## Reglas para los niños (todos los mundos)

Para que nada desaparezca:

* **keep_inventory true:** al morir no se pierde el inventario.
* **mob_griefing false:** los creepers y otros mobs no rompen bloques.

En Paper 26.3 las gamerules se escriben en snake_case y se cambian por mundo:

* **'execute in minecraft:\[nombre_mundo] run gamerule keep_inventory true'**

## Mundo creativo

* Plano, modo **creativo**, dificultad **pacifica**, sin PvP, sin hambre, sin lluvia y sin monstruos.
* Se entra con **'/warp creativo'** o desde el menu **/warps** (boton de pasto).
* GriefPrevention activo: cada uno protege lo que construye.

## Inventarios por grupo

[Multiverse-Inventories](../plugins/multiverse_inventories.md) define que mundos comparten inventario:

* **default:** todos los mundos excepto los del mapa de Hora de Aventuras.
* **ooo:** ooo, ooo_nether y ooo_the_end.
