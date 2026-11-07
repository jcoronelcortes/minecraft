# Minecraft
Guia de comandos de Minecraft

## Introduccion

### UUID

Un UUID (Identificador Único Universal) es un código alfanumérico permanente que distingue de forma única a un jugador, un mundo, o una entidad del juego, incluso si cambias tu nombre de usuario. A diferencia de los nombres de usuario, que pueden ser modificados, el UUID es inmutable y se utiliza en servidores para gestionar datos, permisos e inventarios de los jugadores de manera persistente.


## Servidor

El servidor utilizado es Paper y esta instalado en **'/home/papermc/minecraft'**

* **Version:** Paper 26.3 (build 244), con Java 25.
* **Modo:** online (**solo cuentas premium de Microsoft**). Desde el 07-nov-2026 no se usa nLogin: Mojang verifica a cada jugador.
* El servidor corre como servicio de systemd: **'sudo systemctl start|stop|restart minecraftserver'**.

* [server.properties](servidor/server_properties.md)
* [spigot.yml](servidor/spigot_yml.md)
* [Jugadores: lista blanca y como agregar nuevos](servidor/jugadores.md)
* [Respaldos y restauracion](servidor/respaldos.md)
* [Actualizacion a Paper 26.3 (nov-2026)](servidor/actualizacion_26_3.md)
* [Mundos del servidor](servidor/mundos.md)

## Hora de Aventuras

* [Mascotas, skins, objetos y el mapa Tierra de Ooo (nov-2026)](servidor/hora_de_aventuras.md)

## Icono del servidor

* [Configuracion del icono del servidor](servidor/icono_servidor.md)

## Comandos basicos de Minecraft
* [Comandos basicos](basico/basico.md)

## Herramientas

* [Colores RGB con gradientes y hexadecimal](https://www.birdflop.com/resources/rgb/)

## Instrucciones para crear y configurar un mundo nuevo

* [Instalacion de un mundo nuevo](basico/configuracion_mundo_nuevo.md)

## Plugins

Para confirmar que los plugins instalados funcionan correctamente, se debe ejecutar el comando **'/plugins'**.

1. [Multiverse-Core](plugins/multiverse_core.md)
2. [Skins Restorer](plugins/skins_restorer.md)
3. [Via Version](plugins/via_version.md)
4. [Via Backwards](plugins/via_bacwards.md)
5. [Fast Async World Edir](plugins/fast_async_world_edit.md)
6. [World Guard](plugins/world_guard.md)
7. [Void Teleport](plugins/void_teleport.md)
8. RETIRADO [nLogin](plugins/nlogin.md)
9. RETIRADO [Protocol Lib](plugins/protocol_lib.md)
10. [Advance Teleport](plugins/advance_teleport.md)
11. [zMenu](plugins/zmenu.md)
12. [Conditional Events](plugins/conditional_events.md)
13. [World Guard Events](plugins/world_guard_events.md)
14. [Luck Perms](plugins/luck_perms.md)
15. [Fly Plus](plugins/fly_plus.md)
16. [Placeholders API](plugins/placeholder_api.md)
17. [Mini MOTD](plugins/mini_motd.md)
18. [Easy Command Blocker](plugins/easy_command_bloquer.md)
19. [XConomy](plugins/xconomy.md)
20. [Vault](plugins/vault.md)
21. [Economy Shop GUI](plugins/economy_shop_gui.md)
22. [TAB](plugins/tab.md)
23. [Item Edit](plugins/item_edit.md)
24. [Pet Blocks](plugins/pet_blocks.md)
25. [Grief Prevention](plugins/grief_prevention.md)
26. [Multiverse Inventories](plugins/multiverse_inventories.md)
27. [Multiverse NetherPortals](plugins/multiverse_netherportals.md)


# Creacion de armaduras propias

[Creacion de armaduras](instrucciones/armaduras_propias.md)

# Utiles

Para poder activar el scroll en el **screen** del servior se debe presionar **'Ctrl + A'**, luego **'Esc'** y finalmente moverse con las flechas. Para salir se  debe presionar **'Q'** o **'Esc'**. 